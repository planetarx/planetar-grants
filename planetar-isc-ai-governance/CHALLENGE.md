# CHALLENGE — SSC "AI decision-making process visibility, traceability and compliance governance"

Verified 2026-11-02 against the ISC challenge page:
<https://ised-isde.canada.ca/site/innovative-solutions-canada/en/artificial-intelligence-ai-decision-making-process-visibility-traceability-and-compliance-governance>.
**Re-verified 2026-11-05 against the solicitation documents** (§ *Solicitation terms* below): the
challenge notice `CB-189-51083224` (page dated 2026-10-30, last amendment 2026-10-30, none since)
and the Call 004 PDF `isc-call-for-proposals-004-en578-24isc4.pdf` (146 pp., SHA-256 `74821908…a9dc`)
plus its Amendment 001 (SHA-256 `391e6b51…48ab`), both from `CB-331-17030872`. The PDFs are
copyright, so they are not committed here; fetch them from CanadaBuys. Re-verify before submission;
amendments post on CanadaBuys.

## Terms

| | |
|---|---|
| Sponsor | Shared Services Canada (SSC), via Innovative Solutions Canada (ISED) |
| Vehicle | **ISC Challenge Stream, Phase 2 only** (prototype development) — a **contract** |
| CanadaBuys | `CB-189-51083224` (challenge notice) · `CB-331-17030872` (solicitation documents) |
| Opens / closes | 2026-10-30 / **2026-12-22 14:00 ET** (notice: "2026/12/22 14:00 EST"). Call 004 Amendment 001 extends the *umbrella* CFP to 2026-12-24 23:59 — that is **not** this challenge's close |
| Enquiries | written, **no later than 10 calendar days before close → by 2026-12-12** (CFP §2.4); cite the numbered item of the solicitation; answers go to all offerors. Notice contact `TPSGC.PASIC-APISC.PWGSC@tpsgc-pwgsc.gc.ca`; CFP §2.5 names `TPSGC.SIC-ISC.PWGSC@tpsgc-pwgsc.gc.ca` as Contracting Authority — send to both. No technical authority named |
| Required TRL | **5–9** (mandatory Q2; basic research or vague justification fails) |
| Award | up to **$2,000,000 CAD** excl. taxes, shipping, travel; **estimated 1 contract** (the notice says 1, not 1–2); up to **20 months** (excl. final report); no travel, all meetings by phone/video |
| Eligibility | for-profit, incorporated in Canada, ≤499 FTE, R&D in Canada, ≥50 % Canadian wages / FTEs / senior execs — **Zax Analytics passes** (D1) |
| Scope | AI governance across the GC, explicitly incl. generative and agentic AI |

## Essential outcomes (all mandatory — Q1a)

1. **Continuous alignment** — keep registered AI systems aligned with regulations/policies/directives; identify affected systems and flag reassessment when requirements change.
2. **Interoperability** — standards-based APIs/connectors to enterprise systems and AI/ML lifecycle tools; aggregate governance data across systems; open standards against lock-in.
3. **Access and data control** — restrict/monitor admin, support and data access; customer-set residency, retention, access, deletion policies without vendor intervention.
4. **Assessment and reassessment** — requirements → traceable controls → compliance assessment and non-conformities; versionable/retirable frameworks, per-system criteria. Must cover at minimum: **Policy on Service and Digital, Directive on Automated Decision-Making, Algorithmic Impact Assessment, AI Strategy + AI ethics**; NIST / ISO / EU AI Act extensibility encouraged. Findings human-readable (requirement, evidence, result, confidence); assurance artifacts linked with RBAC attribution; results met / partially / not met / N/A / unable to determine.
5. **Human review** — reviewers validate/reject/modify/annotate findings, audit-logged.
6. **Risk, data and output evaluation** — data risk/quality baselines and thresholds; org-defined risk/performance/quality measures; monitor outputs for accuracy, quality, fairness, consistency, safety.

Additional (Q1b, 10 pts): on-prem / private / Canadian cloud; bilingual EN/FR; multi-tenant; reports + alerts + ticketing integration.

## Evaluation

Mandatory pass/fail: Q1a (all Essentials), **Q2 (TRL 5–9 with evidence of validation, environments and parties)**, Q3a (ISC innovation definition), Q3b (advance on state of the art, ≥ some points).
Point-rated, 130 total, **65 to pass**: Q1b 10 · Q3b 20 · Q4 S&T risk 10 · Q5 project risk 10 · Q6 plan 20 · Q7 team 20 · Q8 inclusivity 20 · Q9 financial controls 10 · Q10 commercialization 10.

## Solicitation terms (Call 004 + notice, read 2026-11-05)

What the documents settle, with the section to cite. "CFP" = the Call 004 PDF; "notice" = `CB-189-51083224`.

- **Problem statement (notice).** SSC says existing AI-governance offerings, Canadian and international,
  "typically require significant manual effort … interpreting evolving AI governance requirements,
  applying them to specific AI systems, updating controls and assessments, and identifying their
  ecosystem-wide impacts." That is the thesis's change-propagation leg (requirement → affected
  controls → affected systems); lead Q1a and Q3b with it.
- **Essentials in full (notice).** Sub-items the summary above compresses: 2A exchange via
  standards-based APIs (metadata, risk assessments, findings, audit evidence, monitoring, approvals,
  decision records, AIAs, "control requirements (playbooks)"); 2B aggregate across systems; 2C open
  standards; 3A residency/retention/access/deletion **without vendor intervention**; 4A must cover at
  minimum **PSD, DADM, AIA, AI Strategy and "AI ethics and responsibilities"**; 4B add/modify/version/
  replace/retire requirements and **assign them to systems or groups by intended use or risk
  profile**; NIST / ISO / EU AI Act extensibility encouraged; 4C each finding names requirement,
  evidence, result and **confidence score or certainty measure**; 4D artefacts (control mapping,
  assessments, evidence refs, approvals, exceptions, attestations, remediation, audit history) with
  **RBAC attribution**; 4E five results; 6A–6C data, model and output measures with baselines,
  thresholds and a traceable record.
- **Q2 must name the environment and the people (CFP Att. 2, Q2).** Method, objectives, results,
  data, highest validation level, "the type of environment(s) in which this was done **and by whom,
  including title**". Paraphrasing a TRL definition fails. The external-reviewer leg of the TRL gate
  is therefore required, not optional.
- **Only the proposal text is evaluated (CFP §3.3.2).** "Canada will not evaluate information such as
  references to Web site addresses." Demo links and repos earn nothing; every measurement must be in
  the text. Text past a field's character limit is not evaluated (§3.1.5). The limits are in the
  online submission form (ISED), not in the CFP; read them when the form is opened.
- **Subcontracting (CFP §1.4.1, Att. 6 §2.6(b)(iii)).** Offeror must do **at least half** of the
  Phase 2 work; up to half may be subcontracted (academic, company, not-for-profit; subcontractors
  need not be eligible). Settles the open issue in `PLAN.md`.
- **IP (CFP §1.8.5, Att. 6 §12.5–12.6).** Contractor owns Foreground IP. Canada gets a non-exclusive,
  perpetual, irrevocable, royalty-free licence to Foreground for its own (non-commercial) use, a
  licence to Background as needed, **source code for software custom-designed for Canada**, and
  **unrestricted ownership of prototype deliverables**. A compilation built from data Canada supplies
  belongs to Canada (§12.5d). Consistent with GPLv3: no conflict, but say so in Q5 (IP risk) and Q10.
- **Financial capability check before award (CFP §4.5.2).** Canada may ask for financial
  statements, a monthly cash-flow statement, bank balance and a signing-officer certification, and
  will not award if resources look inadequate. **A real risk for a solo company on a $2M contract**;
  Q9 should anticipate it. `[TODO founder]`
- **Payment (CFP Att. 6, Annex 5).** Milestone payments at firm amounts, or cost-reimbursable to a
  ceiling: labour at firm hourly rates (inclusive of overhead and profit), materials and subcontracts
  at cost without markup. Every cost needs price support (Contract Cost Principle 1031-2).
- **Selection (CFP §4.1–4.3).** Evaluated by NRC-IRAP and/or other departments' experts (external
  experts possible). Passing puts the bid in a pool for **12 months**; a selection committee then
  weighs GC priorities, prior investments and TRL, and may pick none. Another department may select
  the bid too.
- **Q8 (Att. 2).** Give no personal information about any individual. Registered Indigenous
  businesses get the full 20 points.
- **Partnering list (notice).** Xstal Consulting Limited and ABEN HUB INC. have listed themselves as
  interested in partnering: candidate partners or competitors, check for Q3b.

## The other two challenges in the same mailing (not researched further)

| Challenge | Sponsor | Closes | Phase / TRL | Deliverable |
|---|---|---|---|---|
| Weak magnetic anomaly detection for defence and security | ISED | 2026-11-27 14:00 ET | Phase 2 only, TRL 5–9 | a novel magnetometer (quantum/classical) |
| Strengthening Canada's NV diamond capability | ISED | 2026-11-27 14:00 ET | Phase 1 or 2 | NV-diamond materials / industrial capacity |

Source for those two: the newsletter only ([`idea.md`](idea.md)).
