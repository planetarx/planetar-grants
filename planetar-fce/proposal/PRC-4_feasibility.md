# PRC-4 — Feasibility (20 pts)

> **Field cap:** 3,000 characters. **Tight section** (high weight). CH13 analogue: `../../planetar/proposal/PRC-4_feasibility.md`.
> Core argument: **we already own the chokepoint** → cheapest credible path to a working FCE in a 1a.

## Draft (skeleton)

- **Starting position (de-risks the build):** the substrate is built and broker-integrated —
  bus, typed envelope, CRC32 WAL, ODRL policy, ≥2 modality detectors, analyst shell. The 1a
  is *additive*, not greenfield. [enumerate with LOC/tests from `planetar/docs/built-services-inventory.md`]
- **Scoped 1a build:** (1) class+domain envelope fields; (2) policy-eval hook at publish/sub;
  (3) WAL enforcement-action record type; (4) exportable lineage format; (5) ODRL→classification
  mapping for 2 demo modalities. Each is small and well-bounded (`../03-ARCHITECTURE.md`).
- **Latency feasibility (the FCE's key risk):** measured ns-scale chokepoint (`zbroker0`
  p50 80–140 ns / p99 400–900 ns) gives headroom; the 1a **measures FCE-on overhead** and
  reports it conservatively (bracket measured runs, no post-tuning numbers — CH13 norm).
- **Data feasibility:** DND provides none; applicant already generates AIS/SAR/EO/acoustic
  feeds + can synthesize Protected-B markings. [resolves Q2]
- **Team/timeline:** solo founder, 6-mo 1a; reuse CH13 work-plan/milestone structure (PRC-7,
  `planetar/submission/20-work-plan-milestones.md`).

## TODO
- [ ] Milestone breakdown (mirror CH13's M1/M2 granularity).
- [ ] Name the 2 demo modalities + the measurable overhead target.

## Char-count budget
Target ≤ 2,960 (tight).
