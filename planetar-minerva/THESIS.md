# THESIS — planetar for UAS Deconfliction (single source of truth, DRAFT 2026-09-29)

> Every Deconfliction narrative — capability sheet for a prime (lane A), design doc for the build
> (lane B), any future ISC/IDEaS submission — must match this file. **One thesis per bid** (per
> [`../CLAUDE.md`](../CLAUDE.md)): do not import CH13's learned-fusion model or CH14's compliance
> engine as the hero. Defence face (D3). Decision basis: [`FIT.md`](FIT.md) + the notice text in
> [`CHALLENGE.md`](CHALLENGE.md). **Draft status:** the framing was approved 2026-09-23 as a hybrid
> (live picture + planned missions) when the call was still "upcoming"; the published Essentials
> (2026-09-23) make **planning the must-pass core** and the live picture the differentiator, so
> the emphasis below follows the notice, not the earlier guess.

## The one line

> **An open, provenance-native 4D airspace deconfliction engine for Army UAS: plan every flight
> against every other plan, no-fly zone, and spectrum request; hand each aircraft a deconflicted
> 4D box; then watch the live picture to prove it stays inside — with an auditable record of
> every conflict found, every priority applied, and every human decision.**

## Why this framing

The notice's seven Essential outcomes describe a **planning system** (author, store, integrate,
route, check, resolve, box). Its two scored Additional outcomes describe the **live system**
(prevent collisions in real time; verify conformance in real time). LCol Lemay's own words —
hundreds or thousands of drones sharing air with tactical helicopters, integration with air
defence and counter-UAS to avoid friendly fire — are the live problem. So the hero must satisfy
the planning Essentials, and the differentiator is that the same engine keeps working after
take-off. One data model, two time horizons: a plan is a future track; a track is a plan being
executed. Conflict detection is the same computation on both.

## The three claims it rests on

1. **A plan and a track are the same object.** A 4D trajectory (3D + time) with a spectrum
   requirement is one typed record whether it was authored or observed. Store both in one
   repository, and Essential 6 (check requests against plans and constraints) and Additional 2
   (check live position against the approved trajectory) are one query with different inputs.
   This is what lets a small team cover both horizons.
2. **Ordering and provenance are the safety case.** When many operators submit plans and many
   feeds report positions, "who was first" and "which report was this decision based on" are the
   hard questions in an incident review. planetar already carries UUIDv7 ids, nanosecond
   timestamps, source, and correlation/causation ids on every message, journals them in an
   append-only CRC32 WAL, and has an HLC-sequenced ring design for causal ordering across feeds
   (`../../planetar-disruptor/`). A deconfliction decision that cannot be replayed is not a safety
   system.
3. **Live fusion already runs.** Four live sensor families publishing typed envelopes onto a
   benchmarked bus, fused into an entity graph that re-identifies moving objects across sensors
   (`../../planetar-ontology`, 45 tests). Swap vessels for aircraft and AIS for telemetry and the
   live half of the thesis is the demonstrated part. Headline bus latency stays the measured
   **p50 80–140 ns / p99 400–900 ns** (SHM, `../../planetar/docs/benchmark-2026-04-27.md`).

## Build vs. propose (honesty spine)

**BUILT (verify each against the repo before citing):**
- `planetar-broker` — bus with WAL; the live-feed chokepoint. *Linux-only today.*
- `zmesg` — envelope with native provenance fields (Apache-2.0 for interoperability).
- `planetar-ontology` — entity graph, identity resolution, trace index, Object API + WS.
- `planetar-registry` — canonical typed data model → codegen → encodings (where the 4D
  trajectory type belongs).
- `planetar-ui` — analyst shell with live map, message trace, human-in-the-loop channels.
- Ingest pattern: `-ais`, `-sat`, `-eo`, `-acoustic` (adapters to copy for ADS-B, ICAO flight
  plans, weather, UAS telemetry).
- Applicant background: named inventor on US Patent 10,936,582 (entity resolution; Salesforce-
  assigned, 1 of 19 — never any ownership phrasing).

**PROPOSE (the net-new work — this is why the application is TRL ~2 today):**
- **Flight-plan authoring** with radio-frequency requirements (Essential 2) and the **4D + spectrum
  repository** as registry types (Essential 3).
- **Constraint model:** airspace volumes (no-fly zones, restricted areas, crewed corridors),
  spectrum allocations, priorities; ingestion of crewed flight plans and weather (Essential 4).
- **4D router:** optimal path under mission goals and physical limits (Essential 5).
- **Conflict engine:** spatio-temporal + spectrum conflict detection over the repository, with
  resolution by configured priority or an explicit human decision recorded with provenance
  (Essential 6).
- **Volume generator:** deconflicted 4D "tunnels" and "boxes" per accepted flight (Essential 7).
- **Live conformance and collision-risk service** over the same repository from real-time
  telemetry, with automatic re-plan proposals gated by the human (Additional 1–2).
- **Windows delivery** (Essential 1): Windows-hosted service (Node/TS runs there) + browser client;
  the C broker is not on the critical path for the planning product — decide the transport in
  the build design, don't promise a broker port.

## What each lane says

- **Lane A — capability sheet for a prime.** Lead with the live half (Additional 1–2) and the
  provenance/audit record; offer the data-service adapters (Essential 4) and the repository
  schema. Never imply the planning core exists. The prime's product is the Essentials.
- **Lane B — the build.** The seven Essentials are the requirements table; the exit criterion is
  TRL 5: validated with live traffic in a relevant environment, with a contemporaneous R&D record
  that answers Q2. Civilian face of the same code: UTM for Canadian BVLOS operators (keep that
  framing out of defence documents, per D3, but it is the commercialization answer for Q10).

## Doctrine hooks to thread

*Inflection Point 2025* (Army modernization) · Canada's Defence Industrial Strategy (domestic
capacity, stable supply chains) · MINERVA capability objective 3 (C2 integration) · NORAD
modernization and Arctic airspace · counter-UAS and air-defence integration · TAK as the
delivery surface the Army already names in every sibling call.

## Cut / demote from Deconfliction narratives

- Dark-vessel detection and maritime domain awareness — one line of provenance, never the pitch.
- The learned cross-modal fusion model (CH13) and the Fusion Compliance Engine (CH14) — absent.
- Nanosecond latency as a headline — it is a supporting fact for the live half, not the thesis.

## Guardrails (from [`../CLAUDE.md`](../CLAUDE.md))

- Only measured numbers; only verified repo facts; dates absolute; `[TODO]` for founder-only facts.
- TRL is stated per component and per application, never blended: substrate TRL 4 (maritime,
  2026-06-22 verification — re-verify), deconfliction application TRL ~2 (2026-09-29).
- GPLv3 for planetar code, Apache-2.0 for `zmesg` (D2a); no third-party NC/ShareAlike data in
  anything released.
