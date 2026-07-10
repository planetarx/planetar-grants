# 06 — References (CH14 / Fusion Compliance Engine)

Citation list for the CH14 bid. Grouped by role. **This is the FCE-tailored list** — the thesis
is compliance-by-design (policy enforcement + provenance + exportable lineage at the fusion
chokepoint), so the load-bearing third-party references are **policy/rights languages, classification
& cross-domain standards, and data-provenance standards** — not the learned-fusion references of CH13.

> **Verification status.** A-series (applicant pubs/patents) reused verbatim from CH13
> (`../../planetar/06-REFERENCES.md`), verified there against the PhD thesis appendix + Google Patents.
> **Third-party standards (P/S/B series) web-verified 2026-06-22** for exact document number, title, and
> date — except **S4 (Bell-LaPadula)**, a textbook-canonical MITRE report not re-checked this pass.
> Two standing caveats before a narrative leans on them: (1) **STANAG 4774/4778 full text is NOT
> public** — obtain via National Technical Expert (NATEX); cite the public NATO promulgation
> (ADatP-4774/4778) + implementing-vendor descriptions, do not imply we hold the classified text.
> (2) **"Raise the Bar" (S3) is a US standard**, not a Canadian/NATO requirement — cite as the
> recognized CDS security bar the FCE's approach is positioned against, not as a CH14 obligation.

---

## Applicant publications & patents (pedigree — cited in MC-1, PRC-1, PRC-2, PRC-4)

Reused subset from CH13 (full list + verification notes: `../../planetar/06-REFERENCES.md`). Only the
entries CH14 leans on are carried here; keys are identical to CH13 so cross-references stay stable.

### A1 — Maritime / hydrophone (the ONC anchor) — *PRC-2 pedigree*
[**A1**] Sattar, F.; Driessen, P.F.; Tzanetakis, G.; **Ness, S.R.**; Page, W.H. (2011). *"Automatic Event Detection for Long-Term Monitoring of Hydrophone Data."* IEEE PacRim 2011, pp. 668–674. Evaluation on NEPTUNE Canada / ONC operational hydrophone data.

### A2 — Semi-supervised archival hydrophone ML — *PRC-2 pedigree*
[**A2**] Bergler, C.; et al.; **Ness, S.R.**; Tzanetakis, G.; Nöth, E. (2021). *"ORCA-SLANG: An Automatic Multi-Stage Semi-Supervised Deep Learning Framework for Large-Scale Killer Whale Call Type Identification."* Interspeech 2021, pp. 2396–2400. DOI: 10.21437/Interspeech.2021-616.

### A4 — Multi-output probabilistic fusion — *background for the fusion-path framing*
[**A4**] **Ness, S.R.**; Theocharis, A.; Tzanetakis, G.; Martins, L.G. (2009). *"Improving automatic music tag annotation using stacked generalization of probabilistic SVM outputs."* ACM Multimedia 2009, pp. 705–708. DOI: 10.1145/1631272.1631393.

### A8 — Granted patents (named-inventor background — provenance/entity-resolution IP)
[**A8a**] **Ness, S.R.**, one of 19 named inventors. **US Patent 10,936,582 B2** (granted 2021-03-02; assignee Salesforce, Inc.). *"Integrated entity view across distributed systems."* Background entity-resolution/provenance IP (named-inventor credit, **not assignee**); planetar's lineage substrate develops substantially beyond it. **Cite exactly as "applicant-named inventor on US 10,936,582"; never as ownership** (`CLAUDE.md` patent rule).
[**A8b**] **Ness, S.R.**, one of 11 named inventors. **US Patent 11,442,952 B2** (granted 2022-09-13; assignee Salesforce, Inc.). *"User interface for commerce architecture."* Secondary background credential; named-inventor credit, not assignee. *(Dropped from PRC-2 in the 2026-06-22 char-trim; restore here if a narrative re-cites it.)*

---

## Policy & rights languages (the machine-readable-policy prior art — cited in PRC-2 (a)(2), PRC-4)

ODRL is the FCE's chosen policy language (already built as *expression* in `planetar-market`); XACML and
NIST ABAC are the incumbent attribute-based access-control prior art the FCE's in-path disposition model
(permit/restrict/downgrade/segregate) is positioned against.

### P1 — W3C ODRL (the FCE policy language) — *load-bearing for PRC-2 novelty* ✅ verified 2026-06-22
[**P1**] W3C **Open Digital Rights Language (ODRL)** — **Information Model 2.2** and **Vocabulary &
Expression 2.2**, both **W3C Recommendations, 15 February 2018** (w3.org/TR/odrl-model/,
w3.org/TR/odrl-vocab/). The standards-track rights-expression language the FCE adopts for classification
guides, release authorities, and coalition caveats. **Adopted across JPEG Trust (ISO/IEC 21617), IDSA,
DSSC, Gaia-X, and EUIPO** (`planetar-market/RESEARCH-LEGAL.md` §B / `src/odrl.ts`). The honesty point the
novelty rests on: **ODRL *expresses* rights; it does not *enforce* them** — the evaluation-and-enforcement
engine is the FCE's net-new IP.

### P2 — Prior-art signal: a commercial data marketplace already on ODRL
[**P2**] **Dawex** publishes data-listing rights using ODRL (`RESEARCH-LEGAL.md` §B). Cite as evidence that
machine-readable rights are an *emerging* civil-data practice — strengthening "we bring a maturing
civil-standards substrate to sovereign defence fusion," **not** as a defence-compliance precedent.
`verify:` Dawex's current ODRL usage if cited (the only remaining unverified P/S item).

### P3 — OASIS XACML 3.0 (incumbent policy language — the contrast case) ✅ verified 2026-06-22
[**P3**] OASIS **eXtensible Access Control Markup Language (XACML) Version 3.0**, **OASIS Standard,
22 January 2013** (docs.oasis-open.org/xacml/3.0/; Errata 01, 2017). The established standardized
attribute-based authorization language. Contrast: XACML externalizes *access decisions at a policy
decision point*; the FCE instead renders *in-path per-element dispositions during fusion*.

### P4 — NIST Attribute-Based Access Control ✅ verified 2026-06-22
[**P4**] NIST **SP 800-162**, *Guide to Attribute Based Access Control (ABAC) Definition and
Considerations*. **Originally January 2014; updated through Update 2, 2 August 2019**
(csrc.nist.gov/pubs/sp/800/162/upd2/final). The reference ABAC model; the FCE's
`{classification, domain, source, modality, releasability}` decision attributes are an ABAC attribute set
applied in-path rather than at an access gate.

---

## Classification, cross-domain & provenance standards (EO2/EO4/EO5/EO6 — cited in PRC-2, PRC-3, PRC-6)

The defence-classification and data-lineage standards the FCE implements or is measured against — the
highest-value references for a DND reviewer.

### S1 — NATO confidentiality metadata label syntax — *EO2/EO4 machine-readable markings* ✅ verified 2026-06-22
[**S1**] NATO **STANAG 4774** / **ADatP-4774 Edition A**, *Confidentiality Metadata Label Syntax*. NATO's
XML schema for a machine-readable confidentiality label — **policy identifier, classification level,
releasability markings, creation timestamp** — which maps almost directly onto CH14 EO4's required
provenance (source ID, classification, timestamp, domain) and the FCE's element attributes. The
coalition-interoperability anchor. **Full text not public — obtain via NATEX; public corroboration:
NATO ADatP promulgation + implementing-vendor descriptions (Isode, archTIS, Fortra).**

### S2 — NATO metadata binding mechanism — *EO4 provenance binding + verifiable WAL* ✅ verified 2026-06-22
[**S2**] NATO **STANAG 4778** / **ADatP-4778**, *Metadata Binding Mechanism* (NATO Data-Centric Security).
Binds a confidentiality label (S1) to the data object across its lifecycle; supports **portion marking**
(different labels for different parts of an object) and **cryptographic binding via digital signatures** —
the standards basis for "provenance that travels with each element," and a direct parallel to the FCE's
CRC32-bound WAL records. Portion marking parallels the FCE's per-element (vs whole-object) dispositions.
**Full text not public — same NATEX caveat as S1.**

### S3 — Cross-domain solutions / "Raise the Bar" (the prior-art the FCE improves on) — *PRC-2 (a)(1)* ✅ verified 2026-06-22
[**S3**] **NCDSMO "Raise the Bar" (RTB)** — cybersecurity standards for **Cross Domain Solutions (CDS)**,
published by the National Cross Domain Strategy & Management Office (NSA), **first published 2018** (US
NSM-8, 19 Jan 2022, mandates RTB progress reporting). RTB's foundational **RAIN** principles —
**Redundant, Always-Invoked, Independent implementations, Non-Bypassable**. The incumbent the FCE contrasts
with: CDS/guards screen at a *network boundary* (perimeter, coarse pass/block) *beside or after* fusion;
the FCE enforces *in-path, per-element, during* fusion. **Reviewer-pleasing hook:** the chokepoint design
is inherently *Always-Invoked* and *Non-Bypassable* (every element crosses the one bus). **This is the
reference PRC-2's prior-art TODO needed.** *(US standard — frame as the recognized CDS bar, not a CH14 requirement.)*

### S4 — Multilevel security / classification model — *the downgrade/segregate disposition lineage*
[**S4**] Bell, D.E.; LaPadula, L.J. (1976). *"Secure Computer System: Unified Exposition and Multics
Interpretation."* MITRE Technical Report MTR-2997. The foundational multilevel-security confidentiality
model; "downgrade" and "segregate" are MLS concepts — cite as the theoretical grounding for the FCE's
disposition space. `verify:` report number/year (textbook-canonical; not re-checked this pass).

### S6 — Canadian classification framework (the sovereign "Protected B" anchor) — *EO2* ✅ verified 2026-06-22
[**S6**] Government of Canada classification: **Protected B** — sensitive information whose unauthorized
disclosure could cause *serious injury outside the national interest*. Framework: **TBS Directive on
Security Management, Appendix J — Standard on Security Categorization**
(tbs-sct.canada.ca/pol/doc-eng.aspx?id=32614); security controls per **CSE ITSG-33**; **PBMM** (Protected B
/ Medium integrity / Medium availability) is the GoC baseline cloud profile and the most common level in
government contracting. Cite for EO2's "at least Protected B" as the **Canadian sovereign** classification
the FCE enforces to — pairs with NATO STANAG 4774 markings (S1) for coalition interop. `verify:` ITSG-33
exact title/edition if cited directly (TBS Appendix J + PBMM confirmed this pass).

### S5 — Data provenance & lineage standard — *EO4/EO6 exportable lineage* ✅ verified 2026-06-22
[**S5**] W3C **PROV** family — **PROV-DM** (data model), **PROV-O** (ontology), **PROV-N** (notation), all
**W3C Recommendations, 30 April 2013** (w3.org/TR/prov-overview/). The standard model for representing
provenance/lineage (entities, activities, agents). The interoperable target format the FCE's "exportable
ingestion-to-output lineage for compliance review / forensic analysis / accreditation" (EO6) can map to.

---

## Systems & messaging (the chokepoint + WAL audit-spine — cited in PRC-4, 03-ARCHITECTURE)

Reused from CH13 (`../../planetar/06-REFERENCES.md` B-series, verified there). These ground the
"ns-scale chokepoint + append-only log as audit/lineage spine" feasibility argument.

### B1 — Ultra-low-latency messaging (the chokepoint lineage)
[**B1a**] Thompson, M.; Barker, D.; Gee, A.; Stewart, R. (2011). *"Disruptor: High performance alternative to bounded queues..."* LMAX Technical Paper. The canonical ring-buffer ultra-low-latency messaging reference; planetar's bus is in this lineage.
[**B1b**] **Aeron** — open-source reliable UDP/IPC message transport. https://github.com/real-logic/aeron. Reference implementation studied.

### B2 — Log-as-source-of-truth (the WAL audit + lineage spine)
[**B2a**] Kreps, J. (2013). *"The Log: What every software engineer should know about real-time data's unifying abstraction."* The canonical event-log architecture text; the FCE's CRC32 append-only WAL (immutable audit trail + replayable lineage) is this pattern.
[**B2b**] **Apache Kafka** documentation — append-only log, log compaction, exactly-once semantics. Reference architecture for the WAL + projection pattern.

---

## TODO / wiring
- [x] **Web-verify standards (2026-06-22):** P1 (ODRL, 2018-02-15), P3 (XACML 3.0, 2013-01-22), P4 (NIST
      SP 800-162, 2014/2019), S1 (STANAG 4774 / ADatP-4774-A), S2 (STANAG 4778 / ADatP-4778), S3 (RTB,
      NCDSMO 2018), S5 (W3C PROV, 2013-04-30) all confirmed. Remaining `verify:` items: **P2 (Dawex)**,
      **S4 (Bell-LaPadula identifier)** — both low-stakes.
- [ ] PRC-2 cites wired (a)(1)→[S3], (a)(2)→[P1] on 2026-06-22. Consider adding the XACML/ABAC contrast
      [P3, P4] to **PRC-1 or PRC-4** (PRC-2 has no char room and no XACML prose).
- [ ] Evaluate citing S1/S2 (STANAG) in **MC-2 / PRC-6** for the machine-readable-markings (EO2/EO4) and
      coalition-interoperability framing — high reviewer value; mind the NATEX "not-public-text" caveat.
