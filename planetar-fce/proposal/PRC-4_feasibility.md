# PRC-4 — Feasibility (20 pts)

> **Field cap:** 3,000 characters. **Tight + high weight.** CH13 analogue: `../../planetar/proposal/PRC-4_feasibility.md`.
> Core argument: **we already own the chokepoint** → the 1a is additive, not greenfield. ⚠️ LOC TODO (re-audit).

## Draft (workspace markdown — strip headings before submission)

**Starting position de-risks the build.** The FCE is not built beside a fusion system; it is enforcement added at a chokepoint the applicant already owns and operates. Built, open-source, and broker-integrated today: `planetar-broker` (the C message bus and its CRC32 append-only WAL), `zmesg` (the typed provenance envelope), `planetar-market` (the W3C ODRL policy-expression layer, test-covered), `planetar-ontology` (per-edge lineage), `planetar-ui` (the analyst shell), and four per-modality ingest/detection services — `planetar-ais` (live AIS), `planetar-sat` (Sentinel-1 SAR → CFAR, validated on a real Sentinel-1C scene), `planetar-eo`, and `planetar-acoustic`. The substrate already carries provenance and journals every message immutably; the 1a adds the enforcement engine, not the pipeline.

**Scoped, bounded 1a build.** Five well-defined increments, each small relative to the existing substrate: (1) add classification-marking and domain-of-origin fields to the `zmesg` envelope; (2) a synchronous policy-evaluation hook in the broker publish/subscribe path; (3) the ODRL-to-classification policy model with permit/restrict/downgrade/segregate dispositions and hot-reload; (4) an enforcement-action record type in the WAL; (5) an exportable ingestion-to-output lineage format. See `../03-ARCHITECTURE.md`.

**Latency feasibility — the FCE's key risk — is already evidenced.** The challenge forbids latency that degrades tactical decisions. The bus's shared-memory path is benchmarked at p50 80–140 ns / p99 400–900 ns over a 1M-message run, leaving ample headroom to evaluate a policy and write a disposition. The 1a will **measure FCE-on enforcement overhead** against this baseline and report it conservatively (bracketing measured runs, no post-tuning figures), the same discipline applied to the existing benchmark.

**Data feasibility.** DND/CAF supply no data; the applicant already generates the needed feeds (live AIS, Sentinel-1 SAR via Copernicus) and will apply **synthetic classification markings** (open AIS unclassified, SAR detections marked Protected B) so the demonstrator exercises a genuine cross-domain-merge decision without touching real classified material.

**Team and plan.** A solo founder (PhD, CS/ML) who built the entire spine delivers a focused 6-month 1a in two milestones — Milestone 1: policy model, envelope fields, and demo/data setup; Milestone 2: the enforcement engine, WAL audit record, exportable lineage, an evaluator-operable live planetar.ca demonstration, and the overhead benchmark — with Milestone 1 held to ≤70% of budget per CFP rules. The risk profile is integration of additive components onto a working substrate, not invention from zero.

## TODO
- [x] SAR claim corrected **2026-06-22**: was "validated on a real 433-Mpx scene" — `planetar-sat/README.md`
      shows CFAR validated on *windows* of a real Sentinel-1C scene (land 1582→28, open-water kept 19);
      433-Mpx is the *honest-limitation* (a full GRD scene exceeds memory). Now reads "real Sentinel-1C scene."
- [ ] Insert audited LOC/test counts once re-audited (or keep qualitative).
- [ ] Mirror CH13 milestone/financial granularity (PRC-7; `planetar/submission/20-work-plan-milestones.md`).

## Char-count budget
Target ≤ 2,960. **Measured 2026-06-22: ~2,644** (stripped paste block) — comfortable headroom; "runs over" note was stale.
