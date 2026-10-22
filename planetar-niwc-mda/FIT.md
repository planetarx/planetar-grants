# FIT — NIWC Pacific MDA CSO (`N66001-26-S-C036`): go/no-go + requirement map

- **Verdict (2026-10-06):** **Both fit screens pass, and the call's two "minimum technical data"
  items (source identification, methodology description) are what planetar already does best.
  A brief sent today would still be thin**, for three reasons: there is no measured detection
  performance to put under Technical Merit, two "must" delivery modes are unbuilt (S3, bulk
  download), and the commercial rights to the training data and input feeds are unchecked.
- **Honest lanes:** **(A)** send a truthful Prototype-OT brief now; **(B)** close the top gaps
  and send before the 2027-01-07 deadline; **(C)** team under a data-owning prime as the
  provenance and fusion layer. Recommended: **(B)**, with the two cheap actions that do not
  wait (start SAM.gov registration; e-mail the contact the questions in "Open risks").
- **Decision owner:** Steven Ness. **Not yet decided** (see `## Status` in [`README.md`](README.md)).
- **Deadline:** 2027-01-07 16:00 Pacific (93 days from this note).

Requirement numbers R1–R11 are defined in [`CHALLENGE.md`](CHALLENGE.md).

---

## The two-screen fit filter

| Screen | Test | Result |
|---|---|---|
| **#1 — Honest TRL** | The notice sets **no TRL gate**. Its soft equivalents are the CSO's "commercial product or service" basis, the Step-1 item "your success in the market", and the availability question (§4.1). | ⚠️ **PASS with a caveat.** A Prototype OT explicitly covers "a proof of concept" and "a pilot or novel application of commercial technologies" (§1.4), which is an honest lane for a TRL-4 substrate (verified 2026-06-22, [`../planetar-diana/FIT.md`](../planetar-diana/FIT.md)). Market success is a founder fact this note cannot assert. |
| **#2 — Software-essential deliverable** | Are the must-pass items software, AI or data? | ✅ **PASS, cleanly.** The buy is data and analytics delivered machine-to-machine. No hardware. Caveat: the notice's examples lean on *data collection*, and planetar owns no sensors — every input today is a public or open feed. |

## Requirement → planetar asset map

Repo state verified **2026-10-06** unless a different date is given. "Verified" means the file was
read or the command was run today; dated citations are earlier records, not re-checked.

| # | Requirement | planetar today | Gap |
|---|---|---|---|
| R1 | Detect, locate, identify, track; incl. dark targets | AIS tracks: `planetar-ais` (aisstream.io live source + mock; operating areas `victoria` and `hormuz`, per its README). SAR: `planetar-sat` Sentinel-1 GRD → CFAR + land mask → greedy nearest-neighbour geo tracker. Dark re-identification: `planetar-ontology/src/resolve/kinematics.ts` dead-reckons every known vessel forward from its last kinematic state and scores proximity to an MMSI-less SAR/EO detection. A scripted AIS→dark→SAR→EO scenario was verified end-to-end on the live bus on 2026-06-23 ([`../planetar-diana/FIT.md`](../planetar-diana/FIT.md)). | **No measured detection performance** (no probability of detection, false-alarm rate, or benchmark score). The detector is classical CFAR. Coverage is two areas. The re-ID evidence is a deterministic scenario, not a detection of a real dark vessel. |
| R2 | Feed SeaVision; not a COP | The offer would be the feed. `planetar-ui` and the platform shell are out of scope for this buyer by the notice's own words. | SeaVision's ingest interface is unknown to us (not in the notice). |
| R3 | S3, REST, or TCP stream | REST: `planetar-ontology` Object API — `GET /objects/:type`, `/objects/:type/:id`, `/objects/:type/:id/links/:linkType`, `/trace/:id` (`src/api/server.ts`). TCP stream: `planetar-broker` subscriber port, `zmesg` envelopes (open Apache-2.0 header). WebSocket: `/subscribe`. | **No S3 delivery** (no S3 client in any service). **No authentication** on the API (no principals, keys or tokens anywhere in `planetar-ontology/src`). API documentation is one README block. |
| R4 | Bulk download **and** real-time streaming | Streaming: yes (bus, WebSocket). | **No bulk export.** `GET /objects/:type` pages by `limit`/`offset` (max 1000) with field-equality filters only; no time-range parameter. |
| R5 | Position, type, predicted track | Position: AIS, and SAR detections with `lat`, `lon`, `snr`, `bbox_px` (`planetar-sat/src/planetar_sat/detect/chip.py`). Predicted position exists inside the re-ID rule (`predictedDistanceNm`, `gapMinutes`). | Vessel **type** is not produced: `planetar-eo` filters the COCO "boat" class, and the acoustic classifier ships a mock model (inventory, 2026-05-21). A predicted **track** is not published as a product. |
| R6 | **Source identification** per result | Per-field provenance on every entity (`GET /objects/:type/:id`, "one entity, with provenance"); causal lineage of any envelope (`GET /trace/:id`); every SAR detection carries `scene_id` and `acquired_at_ns`; every envelope carries a source id and correlation/causation ids. `npm test` in `planetar-ontology`: 48/48 pass. | Not checked today: that one call resolves a fused result all the way back to the upstream product name (the Sentinel-1 product, the AIS feed). Worth a demo script. |
| R7 | **Methodology description**; source not required | Exceeds the ask: the full source is public under GPLv3. Written method notes exist ([`../planetar-ocean-startup/DETECTION-ALGORITHMS.md`](../planetar-ocean-startup/DETECTION-ALGORITHMS.md), the kinematic-rule header comment, `planetar-fusion/docs/DESIGN.md`). | No single buyer-facing methodology document with validation results ("assess effectiveness during operational use"). |
| R8 | Example sources | AIS, SAR (Sentinel-1), EO (public webcams), acoustic (hydrophone). | RF, IR, hyperspectral, coastal radar, uncrewed vehicles, registry: none. `planetar-vaults` is synthetic by its own governance rules and cannot be offered as registry data. |
| R9 | Example analytics | Dark-target re-identification (rule-based kinematic). | Classification, fingerprinting, spoofing geolocation, ship-to-ship alerting, route prediction, pattern-of-life: not built (pattern-of-life is "designed" in the parity matrix). |
| R10 | Attributes | **Open formats** and **shareability**: open-source code over open data means no licence barrier to sharing results between agencies or partner nations. **Classification levels**: the mechanism exists in `planetar-platform/spine/governance.ts` (`npm run governance` 8/8 today). | **Latency** from collection to delivery is unmeasured and dominated by upstream publication; the bus benchmark (`../../planetar/docs/benchmark-2026-04-27.md`) is not a delivery-latency claim. **Archive** is shallow: retention defaults are 200,000 envelopes and 500,000 observations. **Classification levels** are absent from the live service, and the platform core has known bypasses (search ignores markings; `spine/flows.ts:142` writes outside the action gate). **Support and training**: one person. |
| R11 | Merit and relevance over price | Relevance is high: the challenge statement is the CH13 problem. | Merit needs numbers (R1). |

**Read:** R6 and R7 map to built, tested code. R1 and R3 map to working code with real gaps.
R4, R5, R9 and most of R10 are gaps.

## Where the platform parity matrix applies, and where it does not

R2 rules out the analyst shell and the "platform" pitch, so most of
`../../planetar-platform/20-PARITY-MATRIX/` is irrelevant to this buyer. The rows that do apply:

| Notice item | Parity-matrix row (slice) | Matrix status | Note |
|---|---|---|---|
| R6 source identification | Field-level / per-field provenance (foundry-governance) | built | |
| R3 REST, R4 streaming | Object API (REST); Object API live feed (WebSocket) (foundry-semantic) | built | |
| R3 S3, R4 bulk | Batch file/object connector (foundry-data); Scheduled reports / exports (foundry-semantic) | designed | |
| R1 dark targets | Dark-vessel kinematic re-ID (foundry-data) | built | |
| R9 pattern-of-life | Track / pattern-of-life analysis (gotham) | designed | |
| R8 RF | RF / SIGINT connector lane (foundry-data) | planned | |
| R10 classification levels | Markings; Propagating security; Restricted views (foundry-governance) | designed | Matrix is dated 2026-06-09; the core was built the next day and passes today. Still not in the live service. |

The platform-class benchmark (reports, dashboards, catalogue, column permissions) is the EMSA
tender, mapped in
[`../planetar-brainstorm/09-platform-benchmark-emsa-bdw.md`](../planetar-brainstorm/09-platform-benchmark-emsa-bdw.md).

## Lanes

**(A) Brief now.** A five-page Prototype-OT pitch: an open, auditable dark-vessel candidate feed
built on open data, with per-result source identification and published method.
- Cost: days. Risk: Technical Merit rests on a scripted scenario and a classical detector; the
  first impression is spent on the weakest version of the offer.

**(B) Close the top gaps, then brief (recommended).** In priority order:
1. A measured result for R1. `planetar-fusion` Stage 1 is coded and unit-tested (2026-10-01) but
   untrained; its xView3 score would be the first public-benchmark number. **Rights caveat
   below** — the benchmark is evidence of method, not a deliverable model.
2. R4 bulk export and R3 S3 delivery, plus API keys. All three are small builds on the Object API.
3. A buyer-facing methodology document (R7) and a one-call source-identification demo (R6).
4. R10 classification levels in the live service — this is the governance workstream already
   under way in `planetar-platform`.
- Risk: the window is open until 2027-01-07 but awards may already be flowing; budget remaining
  is unknown (ask).

**(C) Team under a data-owning prime.** The notice encourages teaming (§6.5) and a
"best-of-breed ecosystem" (§5.3). Vendors with proprietary collection lack what R6 and R7 ask
for; planetar's provenance and fusion layer is the complement, and GPLv3 lets them adopt it
without a negotiation.
- Risk: no prime identified; needs outreach.

(A) forecloses nothing formally, but (B) and (C) are compatible and stronger.

## Open risks

1. **Training-data rights.** xView3 is CC BY-NC-SA 4.0, so a model trained on it is
   non-commercial and ShareAlike-encumbered (`../../planetar-fusion/docs/DESIGN.md`, licence note
   corrected 2026-07-26). It can back a benchmark claim; it **cannot be the model sold to a
   paying customer**. A deliverable model needs commercially usable training data (Stage 2's
   self-collected Sentinel-1 + AIS pairs).
2. **Input-feed rights.** Not verified: whether aisstream.io, the public webcams and the
   hydrophone sources permit commercial redistribution of derived products. Sentinel-1 is the
   only input whose open licence this note is confident about; confirm the rest before pricing.
3. **Registration lead time.** SAM.gov registration is needed before award (§6.1). The DIANA
   window was lost to a registration blocker (2026-07-13); start this one first.
4. **No proprietary data.** Competitors in this space own constellations. The honest
   differentiator is auditability and openness, not collection.
5. **Viability and capacity.** One person; the brief asks for market success, support and
   training.
6. **Cross-bid hygiene.** CH13 (learned fusion) and CH14 (provenance substrate) are under
   evaluation. Do not offer NIWC the deliverables those bids fund, and check whether delivering
   to a US defence customer touches their terms, export controls or the Controlled Goods
   Program (all unverified).
7. **GPLv3 and "limits on how we can use that IP"** (§4.1 item 6). The buyer would receive
   data and analytics, not software, so copyleft should not bind them; if they want the code,
   GPLv3 lets them run and modify it. This is the author's reading, not legal advice.

## Before committing to a lane

- [ ] Founder decision recorded in [`README.md`](README.md) `## Status`.
- [ ] E-mail the §6.11 contact: SeaVision ingest formats; whether briefs are still being
      evaluated and funded; whether a pre-revenue foreign company can receive a Prototype OT.
- [ ] Start SAM.gov registration for Zax Analytics; confirm the identifier steps for a Canadian
      entity on sam.gov.
- [ ] Verify the input-feed licences (risk 2).
- [ ] Re-verify the substrate TRL against the repos (the 2026-06-22 note is the last full pass).
- [ ] If (B): open the work as issues in the code repos, not here; log R&D contemporaneously.
- [ ] `[TODO]` founder facts for the brief: CAGE code, rough-order-of-magnitude price, market
      traction, point of contact.

## Sources

- Notice text and requirement numbering: [`CHALLENGE.md`](CHALLENGE.md), [`idea.md`](idea.md)
- Substrate TRL and the re-ID scenario: [`../planetar-diana/FIT.md`](../planetar-diana/FIT.md) (2026-06-22, 2026-06-23)
- Built inventory: `../../planetar/docs/built-services-inventory.md` (2026-05-21)
- Repos read 2026-10-06: `planetar-ontology` (`src/api/server.ts`, `src/resolve/kinematics.ts`, `README.md`, `npm test`), `planetar-sat` (`detect/chip.py`, `track/tracker.py`), `planetar-eo` (`detect/yolo.py`), `planetar-ais` (`README.md`), `planetar-fusion` (`README.md`, `docs/DESIGN.md`), `planetar-platform` (`spine/governance.ts`, `spine/flows.ts`, `adapters/sqlite/object-index.ts`, `npm run governance`)
