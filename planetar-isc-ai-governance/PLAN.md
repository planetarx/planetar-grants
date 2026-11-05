# PLAN — sprint to TRL 5 for the SSC AI-governance call (closes 2026-12-22 14:00 ET)

Lane chosen 2026-11-02 by Steven. Vehicle: Zax Analytics. Thesis: [`THESIS.md`](THESIS.md).

## What "TRL 5" has to mean here

ISC TRL 5 = component and/or process validation in a **relevant environment** (beta prototype
tested under the end user's conditions); Q2 also demands the R&D record — methods, results,
validation level, environments and **parties involved** (`../planetar-minerva/FIT.md` § TRL,
Call 004). Proposed relevant environment, *to be confirmed with the Contracting Authority*:

- **Real GC governance data:** the public **GC AI Register** (MVP, launched 2025-11-28, ~409
  systems from 42 institutions, Open Government Portal) and published AIAs, assessed against the
  real current texts of DADM, the AIA questionnaire, PSD, and the AI Strategy.
- **A real AI system under continuous monitoring:** the `planetar-fusion` Stage-1 SAR detector
  (live checkpoint, holdout scorer already exists) — output accuracy/drift/data-quality per E6.
- **An external party:** at least one independent reviewer (GC or AI-governance practitioner)
  labelling a sample of findings → the measured confidence and the Q2 "parties involved". **This
  is the weakest leg; start outreach week 1.**

## Schedule

| Week | Dates | Build | Proposal / admin |
|---|---|---|---|
| 1 | 11-02 → 11-08 | New build repo; ingest AI Register; encode DADM + AIA + PSD + AI Strategy as versioned controls with evidence queries | Read Call 004 PDF + challenge notice attachments; send `QUESTIONS-email.md`; reviewer outreach; R&D log starts (`RD-LOG.md` in build repo, for Q2 + SR&ED) |
| 2 | 11-09 → 11-15 | Assessment engine → findings (5-state result, evidence, confidence); assurance artifacts with RBAC attribution | Competitor scan for Q3b (measurable comparisons) |
| 3 | 11-16 → 11-22 | Reviewer workflow (validate/reject/modify/annotate), journalled to WAL; requirement-change propagation → affected-system flags | Draft Q1a / Q2 skeletons |
| 4 | 11-23 → 11-29 | Interop export (open format); residency/retention/access/deletion policy (ODRL) enforced; output + data-quality monitoring of the fusion detector | Draft Q4–Q6, Q9, Q10 |
| 5 | 11-30 → 12-06 | **Validation run**: full Register assessment, reviewer-labelled sample, measured precision/confidence calibration, replay test | **12-01 checkpoint**: on track for the gate? |
| 6 | 12-07 → 12-13 | Fixes; bilingual UI strings (Additional 2) if time | Full draft; Q7 team + Q8 inclusivity `[TODO founder]`; budget `[TODO founder]`; enquiries close ~12-12 |
| — | **12-15** | **TRL gate (below)** | go → finalize; no-go → record and switch to build-for-next-call |
| — | 12-16 → 12-21 | — | Char-check, portal entry, submit by **12-21** (one day buffer) |

## TRL gate (2026-12-15) — all must be true, each with a file/measurement behind it

- [ ] All six Essentials demonstrated end to end on the real Register data (not mocks).
- [ ] ≥1 external reviewer has labelled a findings sample; agreement/precision measured and recorded.
- [ ] Requirement-change demo: edit one control → affected systems flagged → reassessment journalled.
- [ ] Replay demo: a past assessment reproduced from the journal.
- [ ] One live AI system monitored (fusion detector) with recorded output metrics.
- [ ] R&D log covers methods, results, environments, parties (Q2 text writes itself from it).

Fail any → no TRL-5 claim; record outcome in README `## Status`.

## Progress

- 2026-11-03: build repo `../../planetar-govern/` (Python stdlib) — AI Register ingest with provenance,
  412 systems / 43 orgs, completeness profile, `RD-LOG.md` started. Not pushed (no GitHub repo yet).
- 2026-11-05: `planetar-govern` `05250d1` — requirements as versioned controls (`controls/gc-baseline.json`, 11
  controls, AIA questionnaire + Privacy Act s.10(1) pinned by hash) and the assessment engine (five results,
  evidence, missing evidence, provisional flag, append-only). First run on 412 systems in `RD-LOG.md`.
  `fd7b838` (parallel session) — DADM s.6 as 32 clause-hashed controls (TOML), TBS clause splitter (DADM 61,
  PSD 138 clauses), published-AIA ingest (32 machine-readable, decoded per tool version). **Not yet wired
  together.** Still not pushed.
- 2026-11-05: solicitation read (`CHALLENGE.md`, `3e61e53`). Build consequences:
  - **4C: every finding needs a confidence score or certainty measure.** The engine leaves `confidence`
    empty until reviewer labels exist. Week 2: add an interim certainty from evidence coverage (full vs.
    partial evidence, pinned vs. provisional requirement text), then calibrate it against reviewer labels
    in week 5. Say which one the proposal reports.
  - **4B: requirement sets assigned to individual systems or groups by intended use / risk profile.**
    `applies` rules select by register fields today; add explicit assignment (per system, per group,
    by AIA impact level).
  - **Lead story: change propagation.** SSC's problem statement is the manual effort of interpreting
    evolving requirements and their impact across the estate. Clause-hash amendment detection → affected
    controls → affected systems goes first in Q1a and in the demo; pull it forward from week 3.
  - **Q2 must name the validation environment and who validated it, with title.** The external reviewer
    is mandatory, not a nice-to-have.
  - **Evaluators ignore URLs (CFP §3.3.2).** Every measurement goes in the proposal text.
- 2026-11-05: Q3b competitor scan (`COMPETITORS.md`, `a03ce24`). The two "significant improvement" claims
  and the measurement each needs (both go in the **week 5 validation run**):
  1. **Change propagation computed from the official text** (IBM/Credo, ServiceNow and Saidot curate
     regulatory content by hand). Measure by replaying real DADM amendments (TBS published the 2024–25 text
     changes on wiki.gccollab.ca): precision/recall of the affected-system set, and amendment-to-flag latency.
  2. **Confidence calibrated against reviewer labels** (the GC incumbent NuEnergy.ai reports a red/yellow/
     green trust index). Measure reviewer agreement and calibration error.
  - Reuse candidate for Essential 2C: compliance-trestle (OSCAL tooling, CNCF sandbox) — check its licence
    against GPLv3 before importing.

## Open issues

- ~~**NIWC collision.**~~ Resolved 2026-11-03: NIWC no-bid under D7 (no US bids). This sprint has priority.
- ~~Phase 2 subcontracting cap~~ Settled 2026-11-05 (CFP §1.4.1): the offeror does ≥ half the Phase 2 work. IP terms: see `CHALLENGE.md`.
- Is "public GC data + one external reviewer" accepted as a relevant environment? → enquiry.
- Budget shape for up to $2M / 20 months; team for Q7 (solo founder scores poorly) `[TODO]`.
- Data licence: AI Register is under the Open Government Licence – Canada (verify) — fine to use;
  `planetar-fusion` weights are xView3 CC BY-NC-SA → demo/benchmark only, say so.
