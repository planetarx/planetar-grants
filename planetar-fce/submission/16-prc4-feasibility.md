# Field 16 — PRC-4: Feasibility and Approach of Proposed Solution

**Form section:** Component 1a → PRC-4 (20 pts) · **Cap:** 3,000 characters
**LOCAL CHAR COUNT:** 2939 (cap 3,000)
**Source:** `../proposal/PRC-4_feasibility.md` — R8 team/hardware amendment + 2026-07-13 benchmark; blank lines stripped per DIP rule.
**Status:** ✅ READY — **R9 replacement text (2026-07-20)**: `≤70%` claim replaced with the true "39.8% of the total, under the 70% CFP cap" (the DIP PDF generator strips `≤`, leaving a false "stays 70%"); `SAR → CFAR` de-arrowed; Broughton credential trimmed to compensate. Matches `paste/16-prc4-feasibility.txt`.

## Paste-protocol notes

- Blank lines stripped (they count toward the DIP cap). Single newline between paragraphs.
- Markdown emphasis removed; (a)/(b)/(c), (1)/(2)/(3), (i)/(ii)/(iii), (EOn)/(DOn) labels kept as plain text.
- Citation keys like [P1]/[S1]/[A1] stay in — they resolve in field 26 (Reference Documents).
- After paste, DIP's counter should read ~2939 (±2). If it reads noticeably higher, normalize smart chars (— – µ " ') to ASCII and re-paste.

--- PASTE THIS BELOW ---
Starting position de-risks the build. The FCE is not built beside a fusion system; it is enforcement added at a chokepoint the applicant already owns and operates. Built, open-source, and broker-integrated today: planetar-broker (the C message bus and its CRC32 append-only WAL), zmesg (the typed provenance envelope), planetar-market (the W3C ODRL policy-expression layer, test-covered), planetar-ontology (per-edge lineage), planetar-ui (the analyst shell), and four per-modality ingest/detection services — planetar-ais (live AIS), planetar-sat (Sentinel-1 SAR with CFAR detection on a real Sentinel-1C scene), planetar-eo, and planetar-acoustic. The substrate already carries provenance and journals every message immutably; the 1a adds the enforcement engine, not the pipeline.
Scoped, bounded 1a build. Six bounded increments: (1) add classification-marking and domain-of-origin fields to the zmesg envelope; (2) a synchronous policy-evaluation hook in the broker publish/subscribe path; (3) the ODRL-to-classification policy model with permit/restrict/downgrade/segregate dispositions and hot-reload; (4) an enforcement-action record type in the WAL; (5) an exportable ingestion-to-output lineage format; (6) a hardware enforcement datapath — a RISC-V core with custom instructions for envelope parse, label match, and disposition — simulated and FPGA-prototyped for server and sensor-adjacent (camera/UAS) profiles.
Latency feasibility — the FCE's key risk — is already evidenced. The challenge forbids latency that degrades tactical decisions. The bus's shared-memory path is benchmarked at p50 95–100 ns / p99 1.0–1.6 µs over four 1M-message runs, leaving ample headroom to evaluate a policy and write a disposition. The 1a will measure FCE-on enforcement overhead against this baseline and report it conservatively (bracketing measured runs, no post-tuning figures).
Data feasibility. DND/CAF supply no data; the applicant already generates the needed feeds (live AIS, Sentinel-1 SAR via Copernicus) and will apply synthetic classification markings (open AIS unclassified, SAR detections marked Protected B) so the demonstrator exercises a genuine cross-domain-merge decision with no real classified material.
Team and plan. A two-person team delivers the 6-month 1a: the founder (PhD, CS/ML), who built the entire spine, and IC-design engineer Colin Broughton — named inventor on US patents including a multithread embedded processor (US 7,320,065) — owning increment (6). Milestone 1: policy model, envelope fields, demo/data setup, datapath architecture + simulation. Milestone 2: enforcement engine, WAL audit record, exportable lineage, evaluator-operable planetar.ca demo, overhead benchmark, and the FPGA datapath prototype on live bus traffic; Milestone 1 is 39.8% of the total, under the 70% CFP cap. Software risk is additive integration onto a working substrate; the hardware package is scoped to FPGA proof, not silicon.
--- END PASTE ---
