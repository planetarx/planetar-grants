# PRC-6 — Desired outcomes (15 pts)

> **Field cap:** 3,000 characters. **Tightest section historically** — budget hard.
> Traceability: [`../01-CHALLENGE.md`](../01-CHALLENGE.md) DO1–DO4. CH13 analogue: `../../planetar/proposal/PRC-6_desired_outcomes.md`.

## Draft (workspace markdown — strip headings before submission)

**(DO1) Real-time enforcement at tactical-decision speed.** The FCE enforces at the message chokepoint every fused element already crosses, benchmarked at p50 95–100 ns / p99 1.0–1.6 µs on its shared-memory path over four 1M-message runs — orders of magnitude under any tactical-decision threshold. Because the policy check is synchronous and in-path, enforcement is real-time by construction across the demo's two modalities (AIS, SAR) and Protected B markings. The 1a measures FCE-on overhead against this baseline and reports it conservatively (bracketing measured runs, no post-tuning figures), so the "no added tactical latency" outcome is evidenced, not asserted.

**(DO2) Adaptable policy without restart.** FCE policy is W3C ODRL [P1] — data, not code — so classification guides, release authorities, and coalition caveats are reconfigured by swapping a policy set, not recompiling. The 1a demonstrates a live policy hot-reload mid-session (e.g. tightening a releasability caveat) with enforcement continuing uninterrupted: the adaptable-framework outcome shown on a running system, not described.

**(DO3) SWaP / edge deployment.** The enforcement substrate is a dependency-light, single-file C broker (~1.5k LOC, half again as much in doc comments) that runs on commodity hardware — directly the CH14 Tactical-Edge / Dismounted example (a compliance layer on a ruggedized laptop or edge server). The 1a states the measured compute and memory envelope of FCE-on operation, showing enforcement is maintained within an edge SWaP budget rather than requiring datacentre resources.

**(DO4) Explainability + controlled override.** Every disposition is rendered for the operator: `planetar-ui` drills from a compliance decision back through its causation chain to the governing rule and the element's provenance, so an analyst sees *why* data was permitted, restricted, downgraded, or segregated. Override is a first-class, accountable action — an authorized operator can override a disposition, and the override is itself written to the CRC32 append-only WAL as an immutable, attributable enforcement record, satisfying the accountability-safeguard requirement.

## TODO
- [x] Authored to prose **2026-06-22** (one substantive paragraph per DO, concrete demo evidence). DO2 cites ODRL [P1].
- [x] LOC re-audited **2026-06-22**: `planetar-broker.c` = **3,125 lines** total, ≈1,355 doc comments → **~1.5k LOC
      of code** (single file) + 223-LOC `shm-consumer.c` test client. The honest "LOC" is the **code** figure ~1.5k
      (the stale "~1.2k" was an older code count; my interim "~3.1k LOC" wrongly counted comments). Workspace
      standardized **2026-06-22** at **~1.5k LOC** across PRC-6, `01-CHALLENGE.md`, `README.md`, `FIT.md`.
      (CH13 filed with ~1.2k; code grew ~1.2k→~1.5k May→June — honest, not a contradiction.)
- [ ] Re-measure char count at T-3 (CH13 PRC-6 was the binding one at ~2,997).

## Char-count budget
Target ≤ 2,970 (treat as the binding field).
