# CH14 submission record — CP6-144220 (AUTHORITATIVE)

**This file is the authoritative current-state record of the CH14 bid** (the CH13 model:
`../../planetar/docs/submission-record.md`). Read it before assuming what was or wasn't filed.

## ⟹ AUTHORITATIVE: CP6-144220 — Replacement Submission, filed 2026-07-20 08:15 PM

**Replaces CP6-143774** (below, retained as history). Source of record:
[`CP6-144220_ProposalSummary.pdf`](CP6-144220_ProposalSummary.pdf) (29 pp, portal-generated
2026-07-20 17:15 PDT), archived here. Same thesis, TRL 2→3, Component 1a, and financials
($181,000; M1 $72,000/13 wk = 39.8%, M2 $109,000/12 wk) — verified identical in the PDF.

**What the replacement changed (the R9 pass — full rationale in
[`replacement-2026-07-19.md`](replacement-2026-07-19.md)):**
1. **MC-2** — EO1 now claims knowledge-based AI explicitly (per CH14 Q&A Q1, amendment 003);
   EO2 mechanizes the Network-security domain via the envelope domain-of-origin field; symbol
   damage fixed ("(2) fusion" → "at least two").
2. **PRC-1** — AI-enabled grounding sentence anchored to the Q&A; "ingestionoutput" fixed.
3. **PRC-4** — false "stays 70%" rendering replaced with the true "Milestone 1 is 39.8% of the
   total, under the 70% CFP cap"; "SAR CFAR" fixed.
4. **PRC-5** — cross-cutting principle now enforce-first (the filed "engine proposes, operator
   adjudicates" contradicted EO1/EO3); "no kernel bypass or FPGA required"; "Bilingual-ready".
5. **Reference Documents** — 3 → **10 entries** (the portal caps at 10; the planned 13-entry
   list is in `submission/26-reference-documents.md`). Filed: [A1] [A2] thesis (date corrected
   2013-12-31 → **2013-12-23**, UVic DSpace-verified) · both patents (clean named-inventor
   wording, no markdown) · [P1] ODRL 2018-02-15 · [P3] XACML 2013-01-22 · [P4] SP 800-162
   2019-08-02 · [S1] ADatP-4774 2017-12-20 · [S2] ADatP-4778 2018-10-26. **Dropped under the
   cap: [S3] Raise the Bar, [S5] PROV-DM, [S6] TBS/ITSG-33** — each remains self-describing
   inline where cited (full names in the narrative text; W3C PROV also has a glossary entry).
6. **All cosmetic artifacts eliminated** — post-filing denylist grep of the PDF: zero hits
   (no `**`, no backticks, no stripped-symbol damage, no "operator adjudicates").

**Residual knowns (accepted):** the three uncited reference keys above; the filed glossary is
shorter than CP6-143774's (11 entries vs ~20 — the CDS/"Raise the Bar" entry among those not
re-entered). Both judged minor: every dangling key's referent is named in prose at the point
of citation.

**Consequences unchanged:** `proposal/` + `submission/` text is filed — no silent edits;
**planetar.ca stays up and evaluator-drivable**; evaluation ~3–6 months (expect movement
~2026-10 → 2027-01). Replacement window closed 2026-07-21 14:00 EDT.

---

# HISTORY — CP6-143774 (REPLACED 2026-07-20 by CP6-144220)

Source: [`CP6-143774_ProposalSummary.pdf`](CP6-143774_ProposalSummary.pdf) (28 pp,
portal-generated 2026-07-18 15:32 PDT), archived in this directory.

## Filed facts (from the portal summary PDF)

| Item | Value |
|---|---|
| Proposal reference | **CP6-143774** · Category: New Submission |
| Submitted | **2026-07-18 06:32 PM** (portal timestamp; PDF generated 15:32 PDT) — 3 days before the extended deadline **2026-07-21 14:00 EDT** |
| Solicitation / challenge | `W7714-248676/014` — CFP6 CH14 "Reliable AI Sensor Fusion for Real-World Missions" |
| Component | **1a** (TRL 1–3, ≤$250K, ≤6 mo) |
| Offeror | zax analytics · representative Steven Ness |
| Title | *Fusion Compliance Engine: Sovereign Real-Time Classification Enforcement for Multi-Sensor Fusion* |
| TRL | **TRL-2 before → TRL-3 end-state** |
| Keywords | multi-sensor data fusion · data provenance and audit lineage · maritime domain awareness · machine-readable classification policy (ODRL) · compliance-by-design / automated policy enforcement |
| Location / language | Victoria, BC, Canada · English |

## Financial proposal as filed (matches R8 lock, $181,000)

| | Period | Labour | Materials | Other | **Total firm price** |
|---|---|---|---|---|---|
| **Milestone 1** | 13 weeks | $70,000 (PI 400 h + IC-design eng 100 h, both $140/h) | — | $2,000 (cloud compute $1,500 + software/tools $500) | **$72,000** |
| **Milestone 2** | 12 weeks | $102,200 (PI 500 h + IC-design eng 230 h) | $3,800 (FPGA dev board) | $3,000 (cloud $2,000 + data reserve $500 + tools $500) | **$109,000** |
| **Total** | 25 weeks | | | | **$181,000** |

SC-1 checks as filed: total $181,000 ≤ $250K ✅ · M1 = $72,000 / $181,000 = **39.8% ≤ 70%** ✅.
Work plan: M1 = 5 activities (policy-hook design 2 wk, ODRL policy model 3 wk, envelope
classification/domain fields 2 wk, two-modality demo data 2 wk, hardware-datapath architecture
4 wk); M2 = 5 activities (enforcement engine 3 wk, WAL enforcement-record + exportable PROV
lineage 2 wk, evaluator-operable planetar.ca demo 2 wk, measurement/evaluation incl.
disposition bias audit 2 wk, RISC-V RTL + FPGA prototype 3 wk).

## Deltas between the filed proposal and the workspace drafts

1. **Reference Documents filed with 3 entries, not the 12-entry draft.** The filed article
   contains only the applicant-credential entries — Orchive PhD thesis (2013-12-31),
   US Patent 11,442,952 B2 (2022-09-13), US Patent 10,936,582 B2 (2021-03-02) — without the
   bracketed citation keys. The standards/prior-art entries drafted in
   `submission/26-reference-documents.md` (ODRL, STANAG 4774/4778, PROV, XACML/ABAC, Raise the
   Bar, TBS/ITSG-33) were **not** filed as reference documents; the narrative bracket keys
   ([P1], [S1], [S2], [S5], [P3]/[P4], [S3], [S6]) therefore do not resolve to a reference
   list. Mitigation as filed: the **Glossary** article defines ODRL, STANAG 4774/4778, W3C
   PROV, ABAC/XACML, and Raise the Bar (inside the CDS entry), so the terms are decodable.
2. **Markdown artifacts in filed text (cosmetic):** the two patent Author cells contain a
   literal `**not**`; several cost-description cells carry stray backticks (e.g. "No model
   training.`"); one M2 other-cost description begins "Description: `…".
3. Both patents appear in the filed reference list with the exact named-inventor framing —
   compliant with the Q6 / CLAUDE.md rule. ✅

## Consequences (post-submission rules now in force)

- Text under `proposal/` and `submission/` is **filed** — no silent edits; append dated notes.
- **planetar.ca must stay up and evaluator-drivable** — the filed MC-1 end-state and M2 work
  plan promise an evaluator-operable live demonstration there (same standing obligation as
  CH13).
- **Replacement window until 2026-07-21 14:00 EDT:** per the CH13 precedent (CP6-132296
  replaced by CP6-132484), a revised proposal submitted before the deadline replaces this one.
  If that happens, supersede this record with the new reference number.
  **2026-07-18: the founder plans a revised submission after reviewing the filed text** —
  candidate fixes are the deltas above (reference-document list, markdown artifacts).
- Evaluation runs ~3–6 months from close (per CH13 experience) → expect movement
  ~2026-10 → 2027-01.
- Q8 (the CH14 Q&A doc, notice amendment 003): filed on CFP6 Amendment 2 as governing;
  see `08-OPEN-QUESTIONS.md` §Q8 for the trail.

*Record created 2026-07-18 from the portal summary PDF.*
