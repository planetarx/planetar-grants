# REVIEWER — the external validation party (2026-11-05)

**Why it is required, not optional:** Q2 (mandatory, pass/fail) must state "the type of environment(s)
in which this was done **and by whom, including title**" (CFP Att. 2). The TRL gate in `PLAN.md` needs an
external reviewer who has labelled a sample of findings, with agreement measured. Without one, there is
no TRL-5 claim and no bid. The same labels are what calibrate the confidence measure of Essential 4C,
and they back Q3b claim 2 in `COMPETITORS.md`.

## What the reviewer does

- **Labels a sample of findings**, each shown as: the requirement (verbatim clause), the evidence (the
  AIA answer or register field, with its source), and the proposed result (met / partially met / not
  met / not applicable / unable to determine). For each: agree, or the correct result, plus a note.
  The reviewer does **not** see the tool's confidence score (otherwise the calibration is circular).
- **Size:** about 150 findings, stratified by control and by result. That estimates agreement to about
  ±8 points at 95%. A repeat of about 20 findings a week later measures the reviewer's own consistency.
- **Time:** about 8–10 hours in total, remote, in one or two blocks.
- **Window:** labels needed by **2026-12-06** (week 5 validation run in `PLAN.md`), with the gate on
  2026-12-15. Ask by mid-November.
- **Optional, and valuable:** a short written opinion (half a page) on whether the controls read the
  directive correctly. It can be quoted in Q2 with permission.

The reviewer uses the tool's reviewer workflow (Essential 5: validate, reject, modify, annotate, with an
audit log) if it is ready; otherwise a spreadsheet export whose results are imported into the journal.

## Who qualifies

Q2 is strongest with a reviewer whose title evaluators will recognise as competent in GC AI governance:

1. **Someone who has worked with DADM or AIAs:** a former federal public servant from TBS's responsible
   AI or digital policy teams, or a departmental AIA author or peer reviewer (DADM 6.3.7 requires
   qualified-expert reviews, so such people exist in academia and consulting).
2. **An AI-governance academic:** law, public administration or computer science. Candidate places
   (verify current people and interest; nothing here was checked): University of Victoria (local);
   University of Ottawa, Centre for Law, Technology and Society; University of Toronto, Schwartz Reisman
   Institute for Technology and Society; Montreal AI Ethics Institute.
3. **A standards or certification practitioner:** the Digital Governance Council (formerly the CIO
   Strategy Council) publishes a Canadian standard on the ethical design and use of automated decision
   systems (verify the current number); IAPP AI Governance Professional (AIGP) holders in Canada.
4. **A privacy or technology lawyer** who has written on DADM (several national firms have published on
   it).

**Avoid:** current GC employees (conflict of interest, and they may be evaluators); anyone at a
competitor in `COMPETITORS.md`; anyone who would expect equity or a co-applicant role (that becomes a
Q7 team question instead; fine if wanted, but decide it deliberately).

**Payment:** an honorarium paid by Zax before award `[TODO founder: amount]`. If a contract follows,
the reviewer can continue as a Phase 2 subcontractor (up to half the work may be subcontracted).

## Consent to record

- [ ] Name and title may appear in the proposal (Q2) and in the R&D log.
- [ ] Their labels may be reported in aggregate (agreement, calibration). Individual labels stay in the
      journal.
- [ ] No conflict of interest with the SSC challenge; they are not an evaluator.

## Outreach draft (NOT SENT) `[TODO founder: name, honorarium, phone]`

> Subject: Paid expert review of AI-governance findings on public Government of Canada data (8–10 hours, by early December)
>
> Dear [name],
>
> I'm Steven Ness, founder of Zax Analytics, a Canadian company building an open-source tool that
> assesses federal AI systems against the Directive on Automated Decision-Making and related
> instruments. It works only from public data: the GC AI Register and the Algorithmic Impact
> Assessments published on the Open Government Portal. Each finding cites the directive clause, the
> evidence and the result.
>
> I'm looking for an independent expert to review a sample of about 150 findings, marking each as
> correct or giving the right result with a short note. It takes roughly 8–10 hours, remotely, between
> [date] and 2026-12-06, with an honorarium of [amount]. Your review would let us measure how often the
> tool is right, and, with your permission, we would name you and your title as the independent
> reviewer in a proposal to Innovative Solutions Canada.
>
> Given your work on [their specific work], your judgement would carry real weight. Would you be open
> to a 20-minute call to see whether it fits?
>
> Best regards,
> Steven Ness
> CEO, Zax Analytics · [phone]

## Status (2026-11-05)

**The founder has no contacts in this field yet**, so this is cold outreach, and it is the critical
path: no reviewer by about 2026-11-25 leaves too little time to label by 2026-12-06. Routes, in order:

1. **Authors of public work on DADM or AIAs** (papers, op-eds, peer reviews published under DADM
   6.3.7). Their public work is the reason to write to them; cite it. A named shortlist of seven,
   ranked, with the work to cite for each, was compiled 2026-11-05 and is kept **outside this public
   repo** (private repo `planetarx/planetar-private`). Nobody has been contacted.
2. **University research offices and clinics** that broker paid expert work (law-and-technology
   centres; UVic is local).
3. **Mitacs or a university partnership** if a student-plus-supervisor review is acceptable. The
   supervisor's title is what Q2 needs.
4. **Professional networks:** IAPP Canada chapters (AIGP holders), Digital Governance Council events.

Do not use NRC-IRAP advisers: NRC-IRAP evaluates these proposals (CFP §4.1c).

## Founder decisions

- [ ] Shortlist 3–5 people (the categories above are leads, not checked people) and choose who to ask
      first.
- [ ] Honorarium amount.
- [ ] Whether the reviewer may become a Phase 2 subcontractor or team member (affects Q7).
