# STATUS — SSC AI-governance bid, everything in one place (2026-11-05)

Zax Analytics is preparing a bid to Shared Services Canada's AI-governance challenge under ISC Call 004,
which closes **2026-12-22 at 14:00 ET**. The research and bid paperwork for weeks 1–2 are done. The
build (`planetar-govern`) is underway. **The critical path is the external reviewer:** we need one by
about **2026-11-25**, and we have no contacts yet.

This file summarises the others; the detail lives in the files linked from each section. The repo is
public, so personal names (the accountant, reviewer candidates) are kept out of it. Names and private details live in the
private repo `planetarx/planetar-private` (`../../planetar-private/isc-ai-governance/`).

## Key dates

| Date | What | Source |
|---|---|---|
| 2026-11-25 (about) | Reviewer agreed, or there is too little time to label | `REVIEWER.md` |
| 2026-12-01 | Checkpoint: on track for the gate? Budget and cash position settled | `PLAN.md`, `FINANCE.md` |
| 2026-12-06 | Reviewer labels in (week 5 validation run) | `REVIEWER.md` |
| 2026-12-12 | **Last day for written enquiries** (10 calendar days before close, CFP §2.4) | `CHALLENGE.md` |
| 2026-12-15 | **TRL gate**: bid only if every gate item passes | `PLAN.md` |
| 2026-12-21 | Our target submission day (one day of buffer) | `PLAN.md` |
| 2026-12-22 14:00 ET | **Challenge closes** (Amendment 001's 2026-12-24 date is the umbrella CFP, not this challenge) | `CHALLENGE.md` |

## The call

Details: [`CHALLENGE.md`](CHALLENGE.md), read against the solicitation PDFs on 2026-11-05.

- **What SSC wants:** AI governance across the GC. Six mandatory Essentials: continuous alignment,
  interoperability, access and data control, assessment and reassessment, human review, and risk / data /
  output evaluation. Assessment must cover at least DADM, the AIA, the Policy on Service and Digital, the
  AI Strategy and "AI ethics and responsibilities".
- **SSC's stated problem:** existing offerings "require significant manual effort … interpreting evolving
  AI governance requirements, applying them to specific AI systems, updating controls and assessments,
  and identifying their ecosystem-wide impacts." That is our lead story.
- **Money and shape:** Phase 2 only, up to **$2M** excluding taxes, up to **20 months**, an estimated
  **one** contract.
- **Evaluation:** four pass/fail questions (Q1a Essentials, **Q2 TRL 5–9**, Q3a innovation, Q3b advance
  on the state of the art), then 130 points with **65 to pass**.
- **Rules that bind us:**
  - Q2 must name the validation environment **and who validated it, with title**. So an external
    reviewer is mandatory.
  - Evaluators ignore URLs (§3.3.2). Every measurement must be in the proposal text. Text past a
    field's character limit is not read.
  - Zax must do at least half of the Phase 2 work; up to half may be subcontracted.
  - Zax owns the foreground IP. Canada gets a licence, source code for custom software, and ownership of
    the prototype deliverables. This is compatible with GPLv3.
  - Canada pays within 30 days of an acceptable invoice, by progress or milestone payments.
  - A **financial-capability check** comes before award (§4.5.2).
  - Evaluators are NRC-IRAP and/or departmental experts. A passing bid sits in a pool for 12 months.

## Our pitch

Details: [`THESIS.md`](THESIS.md) (SSOT), [`PLAN.md`](PLAN.md).

A Canadian-built assessor that turns each GC requirement into a versioned, machine-checkable control. It
assesses every registered AI system from dated evidence, and journals every finding, reviewer decision
and requirement change so results can be replayed and re-opened when a requirement changes.

**Build state (`planetar-govern`, owned by a parallel session):**

- The AI Register is ingested: 412 systems from 43 organisations.
- 11 baseline controls, plus DADM s.6 as 32 clause-hashed controls.
- A TBS clause splitter: DADM has 61 clauses, PSD has 138.
- Published-AIA ingest: 32 machine-readable AIAs, each decoded against the tool version that made it.
- A five-result assessment engine with an append-only journal.

These parts are not wired together yet, and nothing is pushed.

**Build consequences from the solicitation:**

- Every finding needs a confidence measure (4C).
- Requirements must be assignable to systems or groups (4B).
- Change propagation goes first.
- Build an export and import for the reviewer sample, with the confidence column hidden from the reviewer.

**TRL gate (2026-12-15).** All of these must hold:

- Every Essential is shown end to end on real Register data.
- A reviewer's labels are in, and agreement has been measured.
- A requirement change flags the affected systems.
- A past assessment replays exactly.
- One live model is monitored (the fusion detector).
- The R&D log covers methods, results, environments and parties.

## Competitors and our claims of advance

Details: [`COMPETITORS.md`](COMPETITORS.md). These come from secondary sources; re-verify each before
quoting it.

- **The GC incumbent is NuEnergy.ai** (Ottawa):
  - ISC Testing Stream pilots in 2019–2022 worth more than $2.4M.
  - An ESDC licence of $1.3M, amended to more than $3M.
  - It integrates the GC AIA and reports a red/yellow/green "trust index".
  - It is a likely bidder.
- **Gartner's 2026 AI-governance leaders** (as reported) are IBM watsonx.governance (with Credo AI
  content), ServiceNow AI Control Tower and Truyo ($250K a year).
  - All of them curate regulatory content by hand.
  - None ships DADM or PSD content that we found.
- **OneTrust (DataGuidance) and Holistic AI do sell regulatory-change tracking**, as research and news.
  So we cannot claim that nobody tracks change.

Q3b needs two significant improvements, each with a number:

1. **Change computed from the official text.** A clause-level change in the official text yields the
   computed affected controls, and from those the affected systems.
   - *Measure:* replay real DADM amendments. Report the precision and recall of the affected-system set,
     and the latency from amendment to flag.
2. **Confidence calibrated against an external reviewer.** Most products assert their scores.
   - *Measure:* reviewer agreement and calibration error.

Minor claims: GC instruments built in; replayable audit; open and portable (GPLv3, open formats, no
vendor needed for hosting). Do not disparage named competitors in the proposal.

## Money

Details: [`FINANCE.md`](FINANCE.md).

- Three different things:
  - the **budget table** (at most $2M);
  - **Q9 financial controls** (10 points);
  - the **financial-capability check** after selection (pass/fail; failing it means no contract).
- **Payment comes after the work**, so Zax carries the costs in the meantime. On a full $2M contract,
  modelled peak cash is **$190K–$540K**:
  - $190K with monthly progress payments and no holdback;
  - $370K with a 10% holdback;
  - $290K–$490K with milestones every two to four months.
- **The levers:**
  - Negotiate monthly progress payments with the lowest holdback.
  - Keep milestones short.
  - **Size the ask to the cash we can show.** $1.0–1.5M with a credible cash position beats $2M without
    one.
  - Arrange a line of credit or a shareholder loan.
- **State as of 2026-11-05:**
  - Target budget: unknown.
  - Cash and credit: unknown.
  - The books are kept by Zax's long-standing accountant. Q9 still needs the firm, their professional
    designation, and whether they can prepare monthly cash-flow forecasts.
  - Plan for the low end of the budget until the cash position is known.

## External reviewer (critical path)

Details: [`REVIEWER.md`](REVIEWER.md); names in `planetar-private/isc-ai-governance/reviewer-shortlist.md`.

- **Task:** label about 150 findings, stratified by control and result. That estimates agreement to
  about ±8 points.
  - The reviewer does not see the tool's confidence scores.
  - About 20 findings are repeated a week later to measure the reviewer's own consistency.
  - About 8–10 hours, remote. Labels due 2026-12-06.
  - A half-page written opinion is optional.
  - Paid an honorarium (amount TBD).
- **Who qualifies:** a person who has worked on DADM or AIA review, an AI-governance academic, a
  standards practitioner, or a technology lawyer.
- **Who to avoid:** current GC employees, NRC-IRAP (they evaluate these proposals), and anyone at a
  competitor.
- **Shortlist:** seven candidates were found from their public work on DADM and AIAs.
  - The top fit is the authors of the report behind TBS's Guide to Peer Review of Automated Decision
    Systems. Check whether they are advising on this challenge before asking.
  - Suggested order: ask two or three at a time, starting with the closest fit.
- **Other routes:**
  - University law-and-technology centres (UVic is local).
  - Mitacs: a student does the review under a supervisor, and the supervisor's title goes in Q2.
  - IAPP Canada (AIGP holders) and the Digital Governance Council.
- **Status:** no one contacted. The outreach email is drafted in `REVIEWER.md` and needs the person's
  name and the honorarium.

## Enquiry email (on hold)

Details: [`QUESTIONS-email.md`](QUESTIONS-email.md). Put on hold by the founder on 2026-11-05; the hard
deadline is **2026-12-12**. Answers go to all bidders, so the questions reveal no approach. The four
questions:

1. Is public GC data plus a monitored live model a relevant environment for TRL 5?
2. Which documents count as the "AI Strategy" and "AI ethics and responsibilities"?
3. Does SSC prefer particular open standards (for example OSCAL) or connectors?
4. Will the contractor get an SSC test environment in Phase 2?

Question 1 matters most. If the environment is not accepted, the Q2 pass/fail risk stays open.

## Decisions only Steven can make

- [ ] Who to ask first as reviewer, and the honorarium amount.
- [ ] Whether the reviewer may become a Phase 2 subcontractor or team member (affects Q7).
- [ ] Target budget ($0.75M–$2M) and the team it pays for (Q7). Settle by 2026-12-01.
- [ ] Cash and credit Zax can show by 2026-12-15 (line of credit or shareholder loan?).
- [ ] Accountant's firm and designation for Q9, and whether they can produce monthly cash-flow forecasts.
- [ ] Whether Zax has prior-year financial statements.
- [ ] When to send the enquiry email (by 2026-12-12; earlier is better for question 1).
- [ ] Whether `planetar-govern` gets a public GitHub remote.
- [ ] Q8 inclusivity and Q7 team content.

## Not part of the bid: other work on 2026-11-05

The hydrophone bus went to production on EC2 www0 on 2026-11-05 at 22:24:

- `planetar:orcahello` now publishes OrcaHello detections on the `acoustic.orcahello` topic.
- `planetar:orca-service` subscribes to that topic, so there is no second poller.
- The vic UI was rebuilt.
- The pm2 ecosystem file was replaced; the backup is at `.bak-2026-11-05`.
