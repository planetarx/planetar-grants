# PRC-1 — Science & Technology merit (10 pts)

> **Field cap:** 3,000 characters. CH13 analogue: `../../planetar/proposal/PRC-1_st_merit.md`.
> Threshold: contributes to the 70-pt minimum. Inline-labelled prose (DIP strips line breaks).

## Draft (workspace markdown — strip headings before submission)

**(a) Sound S&T evidence.** The 1a's science — real-time, per-element policy enforcement inside a multi-sensor fusion pipeline — rests on recognised standards, working implementations, and the applicant's peer-reviewed record. *Machine-readable policy:* W3C ODRL [P1], a standards-track rights language used across IDSA, Gaia-X, and JPEG Trust, supplies the policy vocabulary; the applicant has already built an ODRL expression layer (`planetar-market`, test-covered). *Attribute-based decisioning:* mapping a policy to a decision over an element's {classification, domain, source, modality, releasability} is an attribute-based formulation [P4] applied in-path rather than at an access gate. *Classification + provenance standards:* the design targets NATO STANAG 4774 confidentiality-label syntax [S1] with STANAG 4778 binding [S2], and models exportable lineage on W3C PROV [S5] — interoperable foundations, not bespoke markings. *Engineering evidence:* the enforcement seat is a built, provenance-tracked single-file C bus whose shared-memory chokepoint is benchmarked at p50 95–100 ns / p99 1.0–1.6 µs (four 1M-message runs), with a CRC32 append-only WAL for immutable audit. *Pedigree:* the applicant's peer-reviewed ML on continuous, scarce-label sensor streams [A1, A2] and productionised entity-resolution-with-provenance experience evidence the capability to deliver a measurable system.

**(b) State of the art.** The FCE advances current practice on three axes. *Enforcement placement:* incumbent policy languages decide access at a decision point (XACML/ABAC [P3, P4]) and cross-domain guards screen at a network boundary (NCDSMO "Raise the Bar" [S3]); the FCE instead renders per-element dispositions — permit/restrict/downgrade/segregate — in-path during fusion, inherently always-invoked and non-bypassable because every element crosses one bus. *Expression vs enforcement:* ODRL [P1] expresses rights but, by design, does not enforce them; the 1a's evaluation-and-enforcement engine binding an ODRL policy to a real-time disposition is the advance. *Lineage as a property, not a report:* because each decision is journalled to a replayable CRC32 WAL and every fused edge carries provenance, accreditation-grade lineage is structural — beyond the post-hoc audit that current manual-review compliance produces.

Falsifiable 1a outcomes: (i) FCE-on enforcement overhead vs. the no-FCE baseline; (ii) policy-decision correctness on a labelled synthetic Protected-B set; (iii) lineage-export fidelity — reconstructed ingestion→output chain vs. ground truth.

## TODO
- [x] Authored **2026-06-22**; 3 falsifiable metrics stated; S&T credentials reused from CH13 [A1, A2] (re-verified apt for the compliance angle); XACML/ABAC [P3, P4] contrast placed here per the PRC-2 parking note.
- [ ] Benchmark phrasing is forward (Q7 gate covers it — extend Q7 scope to include PRC-1).

## Char-count budget
Target ≤ 2,950.
