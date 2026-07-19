# Field 18 — PRC-6: Alignment of Desired Outcomes

**Form section:** Component 1a → PRC-6 (15 pts) · **Cap:** 3,000 characters
**LOCAL CHAR COUNT:** 2444 (cap 3,000)
**Source:** `../proposal/PRC-6_desired_outcomes.md` — R8 team/hardware amendment + 2026-07-13 benchmark; blank lines stripped per DIP rule.
**Status:** ✅ READY (regenerated 2026-07-13, post-R8)

## Paste-protocol notes

- Blank lines stripped (they count toward the DIP cap). Single newline between paragraphs.
- Markdown emphasis removed; (a)/(b)/(c), (1)/(2)/(3), (i)/(ii)/(iii), (EOn)/(DOn) labels kept as plain text.
- Citation keys like [P1]/[S1]/[A1] stay in — they resolve in field 26 (Reference Documents).
- After paste, DIP's counter should read ~2444 (±2). If it reads noticeably higher, normalize smart chars (— – µ " ') to ASCII and re-paste.

--- PASTE THIS BELOW ---
(DO1) Real-time enforcement at tactical-decision speed. The FCE enforces at the message chokepoint every fused element already crosses, benchmarked at p50 95–100 ns / p99 1.0–1.6 µs on its shared-memory path over four 1M-message runs — orders of magnitude under any tactical-decision threshold. Because the policy check is synchronous and in-path, enforcement is real-time by construction across the demo's two modalities (AIS, SAR) and Protected B markings. The 1a measures FCE-on overhead against this baseline and reports it conservatively (bracketing measured runs, no post-tuning figures), so the "no added tactical latency" outcome is evidenced, not asserted.
(DO2) Adaptable policy without restart. FCE policy is W3C ODRL [P1] — data, not code — so classification guides, release authorities, and coalition caveats are reconfigured by swapping a policy set, not recompiling. The 1a demonstrates a live policy hot-reload mid-session (e.g. tightening a releasability caveat) with enforcement continuing uninterrupted: the adaptable-framework outcome shown on a running system, not described.
(DO3) SWaP / edge deployment. The enforcement substrate is a dependency-light, single-file C broker (~1.5k LOC, half again as much in doc comments) that runs on commodity hardware — directly the CH14 Tactical-Edge / Dismounted example (a compliance layer on a ruggedized laptop or edge server). The 1a states the measured compute and memory envelope of FCE-on operation, showing enforcement is maintained within an edge SWaP budget rather than requiring datacentre resources. It also delivers an FPGA-prototyped hardware enforcement datapath — a RISC-V core with custom instructions for envelope parse, label match, and disposition — evidencing a path to sensor-adjacent enforcement on cameras and uncrewed platforms, and to server-side offload, within the same SWaP envelope.
(DO4) Explainability + controlled override. Every disposition is rendered for the operator: planetar-ui drills from a compliance decision back through its causation chain to the governing rule and the element's provenance, so an analyst sees why data was permitted, restricted, downgraded, or segregated. Override is a first-class, accountable action — an authorized operator can override a disposition, and the override is itself written to the CRC32 append-only WAL as an immutable, attributable enforcement record, satisfying the accountability-safeguard requirement.
--- END PASTE ---
