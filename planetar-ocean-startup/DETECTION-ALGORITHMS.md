# How planetar finds vessels in imagery — the exact algorithms

Written 2026-08-17 (interview-prep companion to [`INTERVIEW.md`](INTERVIEW.md)). Every
claim below was verified against the actual source files on 2026-08-17 — paths are given
inline. Civilian framing throughout, per the per-funder identity doctrine (D3).

## The honest one-paragraph answer (say this, not more)

> "The satellite radar pipeline that runs today uses a **classical statistical detector
> called CFAR — constant false alarm rate — not machine learning**; it's the standard
> baseline for ship detection in radar imagery. The machine learning in the live stack is
> on the **camera side, where a YOLO neural network detects vessels** in harbour-webcam
> frames. The next build, already designed, **replaces the radar CFAR with a learned
> neural detector benchmarked on xView3** — the public Sentinel-1 dark-vessel dataset —
> and then trains a contrastive model that matches radar detections to AIS tracks, which
> is the core R&D thesis."

That distinction — CFAR is *adaptive statistics*, not ML — is a credibility asset, not a
weakness: it shows you know exactly which parts of the stack are learned and which
aren't. Never let "AI finds the boats in the satellite images" go uncorrected.

---

## 1. The SAR pipeline as built (`planetar-sat` — no ML)

Pipeline: **fetch → CFAR detect → geocode → land-mask → track → publish to bus.**

### 1.1 The input, and why it forces a statistical approach

Sentinel-1 IW GRD scenes from Copernicus (CDSE), VV-polarization amplitude at 10 m/px
(`src/planetar_sat/detect/chip.py`, `fetch/copernicus.py`). SAR is *coherent* radar
imaging, so the sea surface doesn't image as smooth water — it images as **speckle**,
a granular multiplicative noise whose local brightness depends on sea state, wind, and
incidence angle across the scene. A single global brightness threshold therefore cannot
work: a level that finds ships in calm water drowns in false alarms in wind-roughened
water. Metal ships, though, are **corner-reflector-like** — hull/deck/superstructure
angles bounce energy straight back — so a ship is reliably *much brighter than its own
local neighbourhood*. That's the property CFAR exploits.

### 1.2 CA-CFAR — the detector (`src/planetar_sat/detect/cfar.py`)

**Cell-Averaging Constant False Alarm Rate.** For every pixel (the *test cell*):

1. Ignore a **guard band** around it — half-width 4 px, i.e. a 9×9 box — so a ship's own
   pixels never leak into its background estimate.
2. Average the **training ring** outside the guard — half-width 12 px beyond it, i.e. a
   33×33 outer box minus the 9×9 guard = **1,008 training cells** — to get the local
   clutter mean `μ`.
3. Declare a detection where `pixel > pfa_factor × μ`, with `pfa_factor = 3.0`. Because
   the threshold *floats with the local clutter*, the false-alarm rate stays roughly
   constant across calm and rough water — hence the name. (Under a fixed clutter model,
   e.g. lognormal, the multiplier maps to a nominal probability of false alarm; 3.0 here
   is an empirically chosen operating point, not a formally calibrated PFA.)
4. **Connected-component labeling** (scipy, 4-connectivity) groups adjacent
   above-threshold pixels into blobs; blobs under **3 px** are discarded as speckle
   flicker. Each surviving blob becomes one detection: its brightest pixel is the
   location, and `SNR = peak / μ` is the confidence score.

Implementation note worth being able to say out loud: the per-pixel window sums are
computed with a **summed-area table** (integral image), so the whole scene is detected
in **O(H·W) regardless of window size** — a full ~29k×24k GRD scene is practical on a
laptop, no GPU.

### 1.3 Geocoding and land masking (`detect/geocode.py`, `detect/landmask.py`)

Pixel (row, col) → lat/lon via the raster's CRS + affine transform when present, else
via the **Sentinel-1 annotation XML geolocation grid** (the usual case for a raw GRD
measurement tiff). Then, because CFAR is a ship-vs-*water* detector, anything that
geocodes onto land is dropped — buildings and terrain relief return strongly in SAR
(one 4096×4096 land window produced **~1,600 spurious detections** in testing). The
current mask is `global_land_mask` at 1-arcmin (~1.8 km) resolution — documented in the
code as a baseline, to be swapped for full-res GSHHG/OSM coastline for fine coastal work.

### 1.4 Tracking (`src/planetar_sat/track/tracker.py`)

**Greedy nearest-neighbour association in geographic space** (not IoU, and not a Kalman
filter — the code is explicit that this is the intentionally simple v0): each new
detection matches the closest existing track within a **2,000 m haversine gate**; a
match updates position and derives **speed (knots) and course** from displacement over
the time gap; unmatched detections spawn new tracks; tracks unseen for **6 h** age out
(~the Sentinel-1 revisit scale). *(Note: the workspace `CLAUDE.md` table says "IoU
track" — the code is geo nearest-neighbour.)*

### 1.5 Known limits (why the learned upgrade exists)

- The 3-px minimum footprint + VV-only input trades away the smallest vessels.
- CFAR says "bright anomaly," not "vessel": azimuth ambiguities, breaking waves, and
  fixed infrastructure (buoys, aquaculture, wind farms) can pass it.
- No attributes — no length estimate, no vessel/non-vessel or fishing/non-fishing
  classification, which is exactly what dark-vessel work needs.

---

## 2. The learned SAR detector — designed 2026-07-26, **not yet built**

(`../planetar-fusion/docs/DESIGN.md` + `docs/plans/2026-07-26-stage1-xview3-detector.md`;
the repo currently contains design docs only — say "designed," never "built.")

### 2.1 Stage 1 — CenterNet-style heatmap detector on xView3-SAR

- **Why a heatmap and not boxes:** at 10 m/px most vessels are a handful of pixels —
  effectively *points*. So instead of anchor-box regression (the YOLO/Faster-RCNN
  family), the model outputs a per-pixel **objectness heatmap**: training "splats" a
  small Gaussian at each labelled vessel centre and the network learns to reproduce
  those peaks. Inference = find local maxima.
- **Input:** scenes tiled into 800 px patches (stride 704, ~10% overlap), **5 channels**
  — VH dB, VV dB, bathymetry, land/ice mask, wind speed — per-channel normalized. (Both
  polarizations plus physical context, vs. CFAR's single VV band.)
- **Architecture:** small FPN/U-Net encoder-decoder backbone → the heatmap head plus
  per-object heads for **length regression** (smooth-L1 in log-space), **is_vessel** and
  **is_fishing** (binary cross-entropy). Heatmap trains with **penalty-reduced focal
  loss** (standard CenterNet recipe — focal handles the extreme empty-ocean/vessel pixel
  imbalance).
- **Inference:** tile the full scene → peak extraction per tile → **NMS across tile
  boundaries** → detections with attributes.
- **Benchmark:** the public **xView3-SAR** dataset (DIU + Global Fishing Watch, NeurIPS
  2022): 991 Sentinel-1 scenes, 243,018 labelled objects, 220k+ *dark* instances; scored
  with the official aggregate `MR` metric via the reference scorer, honestly reported
  against the published leaderboard. Single-GPU scale (challenge baseline was one V100).
- **"Dark" is not a model output.** Deliberately: darkness = (detections) − (live AIS
  feed) at deployment, never a SAR-only classifier.
- Integration: ships as a `--detector learned` backend of `planetar-sat`, emitting the
  same bus messages CFAR does today.

### 2.2 Stage 2 — the learned SAR↔AIS association (the actual thesis)

During AIS-on, a broadcasting vessel **labels its own concurrent SAR detection for
free** (space-time proximity). On those free pairs, train:

- a **SAR chip encoder** (reusing the Stage-1 backbone) → embedding of the detection;
- an **AIS encoder** (small MLP) over the candidate's kinematics — position
  *dead-reckoned to the SAR acquisition instant*, speed, course, length, type,
  time-since-ping;
- projected into a **shared embedding space** with an **InfoNCE contrastive loss**
  (positive = the true pair; negatives = the other vessels in the same scene).

Inference: spatial-gate each SAR detection to nearby AIS candidates → score in the
embedding → best-above-threshold = associated; no good match = **dark**, and the dark
chip's embedding is matched against a gallery of known vessel signatures (the on-ramp to
re-identification). Evaluated against a nearest-neighbour proximity baseline, plus
AIS-blinding tests (hide a known vessel's AIS; is it flagged dark rather than
mis-matched?). This is where "learned, adaptive association" beats plain proximity: AIS
pings lag the acquisition, vessels move, and several can be close together.

### 2.3 Licensing guard-rail (do not trip this in the interview)

Per `DESIGN.md` (license corrected 2026-07-26 from the actual download page): xView3 is
**CC BY-NC-SA** — so the xView3-trained Stage-1 weights are a **research/benchmark/demo
artifact only** and can never ship as part of the GPLv3 open-source model. The
*released* detector retrains on commercially-clean data: Copernicus Sentinel-1 +
Marine Cadastre public-domain AIS (the Stage-2 pipeline). If asked "is the AI open
source too?" the answer is: the code and released weights yes (GPLv3); the
xView3-benchmark weights are encumbered by the dataset's non-commercial licence and stay
a benchmark artifact. *(Known internal inconsistency: the Stage-1 plan doc's
"Global Constraints" still carries the older "commercial-usable" reading — `DESIGN.md`
is authoritative.)*

---

## 3. The imagery ML that IS live: camera-side YOLO (`planetar-eo`)

(`src/planetar_eo/detect/yolo.py`.) Harbour-webcam frames → **Ultralytics YOLO11-nano**
(`yolo11n.pt`, COCO-pretrained), filtered to COCO class 8 (*boat*), confidence ≥ 0.25,
NMS IoU 0.45, 640 px input; optional per-detection JPEG crops onto the bus. YOLO is a
one-stage convolutional detector: one forward pass predicts boxes + class scores over a
grid, then non-maximum suppression keeps the best box per object. Off-the-shelf
pretrained weights, honestly described as such — a fine-tuned marine checkpoint is a
drop-in (`model=<path>`).

For completeness, the acoustic path (`planetar-acoustic`,
`src/planetar_acoustic/classify/sai_cnn.py`): hydrophone audio → stabilized auditory
image (SAI, a 2-D cochlear-model representation) → an ImageNet-pretrained CNN backbone
over the SAI-as-image, with cargo/passenger/tanker/tug/fishing/background classes.
Torch/ONNX backends exist, but the default shipping backend is an explicitly-labelled
**mock** — the intended training corpus (DeepShip + ShipsEar) has not been trained in.
Claim the architecture, not a trained model.

---

## 4. Provenance table

| Claim | Source (verified 2026-08-17) |
|---|---|
| CA-CFAR, guard 4 / train 12 / factor 3.0 / min 3 px, O(H·W) SAT | `../../planetar-sat/src/planetar_sat/detect/cfar.py` |
| Geocoding fallback via S1 annotation XML | `.../detect/chip.py`, `.../detect/geocode.py` |
| Land mask 1-arcmin; ~1,600 false alarms on a land window | `.../detect/landmask.py` docstring |
| Greedy geo NN tracker, 2 km gate, 6 h age-out, speed/course | `.../track/tracker.py` |
| Learned detector design (CenterNet heatmap, 5-ch, focal+L1+BCE, xView3 `MR`) | `../../planetar-fusion/docs/DESIGN.md`, `docs/plans/2026-07-26-stage1-xview3-detector.md` |
| planetar-fusion has no code yet | repo contains `docs/`, `README.md`, `LICENSE` only |
| YOLO11n, class 8, conf 0.25, IoU 0.45, 640 px | `../../planetar-eo/src/planetar_eo/detect/yolo.py` |
| Acoustic SAI→CNN, mock default, corpus not yet trained | `../../planetar-acoustic/src/planetar_acoustic/classify/sai_cnn.py` |
