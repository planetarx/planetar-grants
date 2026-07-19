# Field 26 — Reference Documents

**DIP page:** Component 1a → Reference Documents. Each entry needs **Title / Author / Publication Date / Relevance**.
**Status:** ✅ READY. FCE-tailored — applicant credentials + the standards the engine implements/depends on.
**Key map (as cited in the narratives):** [A1]=entry 5 · [A2]=entry 4 · [P1]=entry 6 · [P3]/[P4]=entry 10 ·
[S1]=entry 7 · [S2]=entry 8 · [S3]=entry 11 · [S5]=entry 9 · [S6]=entry 12. **Include the bracketed key at the
start of each Title field** so the narrative citations resolve for the evaluator.
**Two reminders:** (1) patents are **named-inventor credit, not ownership** (Q6 / CLAUDE.md). (2) Items marked
`VERIFY` need an exact date confirmed before entry (the standards' dates are web-verified 2026-06-23; the thesis
day and the STANAG/GoC dates still need a source check). Don't over-stuff — these are the load-bearing documents.

---

## A — Applicant background IP & credentials (your documents)

=== 1 — entity-resolution / provenance background IP (named inventor) ===
Title: US Patent 10,936,582 B2 — Integrated entity view across distributed systems
Author: Steven R. Ness, one of 19 named inventors (assignee: Salesforce, Inc. — named-inventor credit only, **not** the assignee/owner)
Publication Date: 2021-03-02 (grant date; confirmed Google Patents / USPTO)
Relevance: The integrated-entity-view / entity-resolution architecture the applicant contributed to; `planetar-ontology` (the FCE's per-edge lineage graph that tracks provenance from ingestion through fused output) is a substantial development beyond it.

=== 2 — second identity-resolution background patent (named inventor) ===
Title: US Patent 11,442,952 B2 — User interface for commerce architecture
Author: Steven R. Ness, one of 11 named inventors (assignee: Salesforce, Inc. — named-inventor credit only, **not** the assignee/owner; issued from App. 16/264,391)
Publication Date: 2022-09-13 (grant date; confirmed Google Patents)
Relevance: Canonical-data-model matching / identity-reconciliation prior art the applicant contributed to — secondary background credential for the provenance-and-lineage substrate, distinct from the project's net-new FCE foreground IP.

=== 3 — applicant's PhD thesis (archive-scale ML + human-in-the-loop) ===
Title: The Orchive: A System for Semi-Automatic Annotation and Analysis of a Large Collection of Bioacoustic Recordings
Author: Steven R. Ness (PhD thesis, University of Victoria, Dept. of Computer Science; supervisor George Tzanetakis)
Publication Date: 2013 — VERIFY exact date on UVic DSpace if the form requires a specific day
Relevance: The applicant's doctoral work — archive-scale machine learning on a 20,000-hour, 30-year hydrophone archive with a **human-in-the-loop** design in which classifier outputs are shown back to the operator in the same interface. Grounds two FCE threads: the capability to deliver a measured system, and the **explainable-decision / operator-in-the-loop** surface (`planetar-ui` clicks a compliance disposition back through its causal chain; controlled, logged override).

=== 4 — applicant's semi-supervised deep-learning credential ===
Title: [A2] ORCA-SLANG: An Automatic Multi-Stage Semi-Supervised Deep Learning Framework for Large-Scale Killer Whale Call Type Identification
Author: C. Bergler, M. Schmitt, A. Maier, H. Symonds, P. Spong, S. R. Ness, G. Tzanetakis, E. Noeth
Publication Date: 2021-08-30 (Interspeech 2021)
Relevance: Applicant's co-authored, peer-reviewed semi-supervised deep learning on continuous, scarcely-labelled sensor streams — evidence of the capability to deliver reliable ML over noisy real-world data.

=== 5 — applicant's acoustic / Ocean Networks Canada credential ===
Title: [A1] Automatic Event Detection for Long-Term Monitoring of Hydrophone Data
Author: F. Sattar, P. Driessen, G. Tzanetakis, S. R. Ness, W. Page
Publication Date: 2011-08-23 (IEEE Pacific Rim Conference, PacRim 2011)
Relevance: Peer-reviewed event detection on Ocean Networks Canada operational hydrophone data — precedent for reliable analytics on continuous real-world sensor streams.

---

## B — Standards the FCE implements or depends on (the "other docs")

=== 6 — the FCE policy language ===
Title: [P1] ODRL Information Model 2.2 (and ODRL Vocabulary & Expression 2.2)
Author: W3C (World Wide Web Consortium) — W3C Recommendations
Publication Date: 2018-02-15
Relevance: The machine-readable, standards-track rights/policy language the FCE adopts for classification guides, release authorities and coalition caveats. The applicant has built an ODRL *expression* layer (`planetar-market`); the project builds the engine that *enforces* it.

=== 7 — machine-readable classification markings ===
Title: [S1] NATO STANAG 4774 (ADatP-4774) — Confidentiality Metadata Label Syntax
Author: NATO Standardization Office
Publication Date: Edition A — VERIFY edition/date (standard text is NATEX-restricted; cite the public NATO promulgation)
Relevance: The NATO standard for a machine-readable confidentiality label (policy id, classification level, releasability, timestamp) — the marking syntax the FCE's classification/domain fields are designed to.

=== 8 — binding markings to data ===
Title: [S2] NATO STANAG 4778 (ADatP-4778) — Metadata Binding Mechanism
Author: NATO Standardization Office
Publication Date: VERIFY edition/date (NATEX-restricted; cite the public promulgation)
Relevance: Binds a confidentiality label (STANAG 4774) to the data object across its lifecycle — the standards basis for "provenance that travels with each element," and the coalition-interoperability target.

=== 9 — provenance & lineage standard ===
Title: [S5] PROV-DM / PROV-O (the W3C PROV family)
Author: W3C (World Wide Web Consortium) — W3C Recommendations
Publication Date: 2013-04-30
Relevance: The standard model for representing provenance and lineage; the interoperable target format for the FCE's exportable ingestion-to-output lineage (for compliance review, forensic analysis, accreditation).

---

## C — Prior-art / context (**REQUIRED** — [P3]/[P4], [S3] and [S6] are cited in the scored narratives)

=== 10 — incumbent attribute-based policy ===
Title: [P3] eXtensible Access Control Markup Language (XACML) Version 3.0 (OASIS Standard); [P4] NIST SP 800-162, Guide to Attribute Based Access Control (ABAC)
Author: OASIS; NIST
Publication Date: XACML 3.0 — 2013-01-22; SP 800-162 — 2014 (updated 2019-08-02)
Relevance: The established attribute-based access-decision approach the FCE contrasts with — XACML/ABAC decide access at a policy decision point; the FCE renders per-element dispositions in-path during fusion.

=== 11 — cross-domain solution security standard ===
Title: [S3] NCDSMO "Raise the Bar" — Cross Domain Solution design principles
Author: National Cross Domain Strategy & Management Office (US NSA)
Publication Date: 2018 (VERIFY citable public overview)
Relevance: The recognized security bar for cross-domain solutions (perimeter guards) — the prior art the FCE improves on by enforcing in-path, always-invoked and non-bypassable. (US standard; cite as context, not a CH14 requirement.)

=== 12 — Canadian classification framework ===
Title: [S6] Standard on Security Categorization (TBS Directive on Security Management, Appendix J); CSE ITSG-33
Author: Treasury Board of Canada Secretariat; Communications Security Establishment
Publication Date: VERIFY current edition
Relevance: The Government of Canada framework defining Protected B — the sovereign Canadian classification level the FCE enforces to in the demonstration.

## Notes
- The full annotated list is `../06-REFERENCES.md`. **All twelve entries are load-bearing** — sections B and C keys are cited in MC-2/PRC-1/2/3/6 (see the key map above); do not drop entries 10–12.
- Patent entries: keep the "named-inventor credit, not assignee/owner" wording in both Title/Author and Relevance.
