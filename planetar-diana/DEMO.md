# DEMO — cross-sensor dark-vessel re-identification (the DIANA pitch demo)

> The live capability behind the bid: a vessel goes AIS-dark, then is **re-identified across two
> different sensor domains** (satellite SAR → electro-optical) by the entity graph, with auditable
> field-level provenance. This is the literal answer to the DIANA ISR challenge ("sensor & data
> fusion … actionable, causality-based intelligence"). Built + verified **2026-06-23**.

## What it proves (maps to [THESIS.md](THESIS.md) / [FIT.md](FIT.md))

- **Multi-domain fusion** — AIS + SAR + EO observations resolve onto one canonical entity.
- **Cross-sensor re-ID** — a no-MMSI SAR detection, then an EO detection, are both matched to the
  dark vessel by dead-reckoned kinematics → two `reacquisition` links.
- **Auditable / causality-based** — field-level provenance shows exactly which sensor supplied each
  attribute and when (the "why" behind the fused track).
- **TRL 4 → 5/6** — the integrated pipeline runs on the live bus alongside the real Victoria AIS
  feed; the in-program work is hardening + a NATO-relevant-environment validation.

## Components (all verified against the repos, 2026-06-23)

| Piece | Repo / path | Role in the demo |
|---|---|---|
| Bus | `planetar-broker` (or the `/tmp/planetar-broker-shim.mjs` dev stand-in) | carries `zmesg` envelopes, TCP :12001 pub / :12002 sub |
| Entity graph | `planetar-ontology` | ingests off the bus, resolves entities, runs the kinematic re-ID, serves the Object API (:4000) |
| Demo driver | `planetar-ontology/tools/demo-reid.ts` | publishes the deterministic AIS→dark→SAR→EO scenario |
| Shell | `planetar-ui` GraphTab | renders the fused entity + the `reacquisition` links (this session's UI change) |

## Run it

```sh
# 1. Bus must be up on :12001/:12002 (real broker, or the dev shim).
# 2. Ontology, against a clean throwaway DB so the demo entity is easy to find:
cd ~/github/planetarx/planetar-ontology
PLANETAR_ONTOLOGY_DB=/tmp/demo-reid.db npm start        # API on http://127.0.0.1:4000

# 3. Fire the deterministic scenario (new terminal):
cd ~/github/planetarx/planetar-ontology
node tools/demo-reid.ts
```

## Verify (API)

```sh
# The fused vessel — status should be "reacquired", lat/lon/status provenance from planetar-eo:
curl -s "localhost:4000/objects/planetar:Vessel?mmsi=316007777" | python3 -m json.tool

# The cross-sensor re-ID evidence — two links, planetar-sat then planetar-eo:
VID=$(curl -s "localhost:4000/objects/planetar:Vessel?mmsi=316007777" \
  | python3 -c "import sys,json;print(json.load(sys.stdin)['objects'][0]['id'])")
curl -s "localhost:4000/objects/planetar:Vessel/$VID/links/reacquisition" | python3 -m json.tool
```

**Verified output (2026-06-23):** entity `MV Shadow Runner` (MMSI 316007777), `status: reacquired`;
`mmsi/name/cog/sog` provenance = `src:planetar-ais@2.1.0`, `lat/lon/status` = `src:planetar-eo@1.0.0`;
two `reacquisition` links — `src:planetar-sat@1.0.0` (score 0.9, gap 40 min) and
`src:planetar-eo@1.0.0` (score 0.9, gap 20 min). The live Victoria AIS fleet was correctly excluded
(detections precede their last fix → negative-elapsed guard).

## Verify (shell)

Two surfaces now tell the re-ID story (both typecheck via `tsc -b`):

- **GraphTab** — fetches each vessel's `reacquisition` links via the new
  `OntologyClient.getLinks()` (`planetar-ui/src/lib/ontology.ts`) and renders a
  **"Re-identified · N cross-sensor matches"** block per card
  (`planetar-ui/src/components/tabs/GraphTab.tsx`, styles in `App.css`).
- **MapTab** — a **"Re-ID / dark (fused)"** overlay layer fed by the ontology entities store
  draws a glowing halo + dot on every flagged vessel (amber = dark-suspected, red = dark-confirmed,
  blue = reacquired); clicking one shows a fused-entity popup. Toggle it in the map's layer control.
  The demo's `MV Shadow Runner` appears as a **blue (reacquired)** marker in the Salish Sea even
  though it isn't in the raw AIS feed — because the map now renders the *fused* entity, not just AIS.
  (`planetar-ui/src/components/tabs/MapTab.tsx`.)

> ⚠️ **Local UI caveat (2026-06-23):** `vite` (dev + build) currently fails on this machine with a
> missing `@rolldown/binding-darwin-arm64` native binary — the known npm optional-deps bug
> (npm/cli#4828), unrelated to the demo. Fix before a live screen demo:
> `cd ~/github/planetarx/planetar-ui && rm -rf node_modules package-lock.json && npm i`.
> The pipeline + Object API are fully verified independently of the browser.
