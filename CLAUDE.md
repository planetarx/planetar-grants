# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

`planetar-grants` (git: `git@github.com:planetarx/planetar-grants.git`) is a **funding/grants
portfolio workspace** — Markdown only, no build/test/lint. It holds the *pipeline* of grant
opportunities for the **planetar** project: research notes, fit/go-no-go analyses, proposal
drafts, and funding-strategy scratchpads. The actual flagship bid (IDEaS CH13) lives in a
sibling repo at `../planetar/`, not here; see "Relationship to siblings" below.

There is no top-level README — each sub-workspace has its own. There are no commands to run;
work is reading, analyzing fit, and authoring Markdown.

## The five sub-workspaces

Each is a self-contained workspace for one funding opportunity (or strategy area). Check the
workspace's own `README.md` first — it's the status dashboard.

| Dir | Opportunity | State |
|---|---|---|
| `planetar-fce/` | IDEaS CFP6 **Challenge 14** — "Reliable AI Sensor Fusion" / Fusion Compliance Engine. `W7714-248676/014`, deadline **2026-07-14 14:00 EDT**, Component 1a (TRL 1–3, ≤$250K, ≤6mo). | **ACTIVE — scaffold, LEAN BID.** The live authoring target. |
| `planetar-diana/` | **NATO DIANA 2027** — "Multidomain Sensing & Advanced Data Processing for Intelligence and Surveillance." Accelerator, €100K (+ up to €300K), deadline **2026-07-03 12:00 BST**, **TRL 4+** gate. | **ACTIVE — drafts built (2026-06-22).** First **non-IDEaS** bid to pass both fit screens. Conditional GO; bandwidth go/no-go by 2026-06-28. |
| `planetar-brainstorm/` | Broad funding/sustainability strategy for planetar as OSS (NLnet, IRAP/SR&ED, Ocean Startup, NATO DIANA, etc.) + ready-to-use `drafts/`. `07-funding-radar.md` = announcement-channel tracker + Gotham-adjacency scan. | Ongoing reference + drafts. |
| `planetar-true-north/` | IDEaS "True North Precision" (drone laser ranging), `W7714-248676/012`. | **NO-BID** (2026-05-31) — kept as reference. |
| `planetar-innovation/` | ISC Testing Stream TS13, `EN578-26ISC1`. | **NO-BID** (2026-06-01) — kept as reference. |

## The fit filter (the load-bearing lesson of this repo)

Both no-bids died for the **same two reasons**. Apply this screen *before* spending effort on
any new opportunity — it's the central institutional knowledge encoded here:

1. **Honest TRL — nuanced after the 2026-06-22 verification.** The IDEaS *funded R&D scope*
   (new fusion/compliance science) is honestly **TRL 1–3** — keep bidding 1a there. But the
   *demonstrated platform substrate* (bus + envelope + four live detectors + entity-graph re-ID +
   shell) was verified **at TRL 4** against the actual repos — integrated and lab-validated, with
   several components at TRL 5 on live feeds (see `planetar-diana/FIT.md`). So **TRL-4-gated calls
   are now reachable** when the bid is framed around the demonstrated platform. Still skip calls
   gated at **TRL 5+/operational-prototype** unless a partner owns that maturity. (The old reading
   "planetar is early R&D, skip all TRL 4+" killed True North's 1b claim and TS13's TRL-7 gate —
   both also failed screen #2, which is the more decisive filter.)
2. **The scored/Essential deliverable must be software/AI/data, not hardware.** When the
   must-pass outcomes are airframes, optics, RF apertures, or weapons, planetar can only be a
   backbone, never the prime. (Killed both no-bids — the decisive screen.)

**CH14 (`planetar-fce`) is significant as the first *IDEaS* challenge whose *Essential* outcomes
are pure software** — it passes both screens; it's the active authoring target. **`planetar-diana`
is the first *non-IDEaS* opportunity to pass both** (software-essential ISR fusion + a TRL-4 gate
the verified substrate clears) — proof the fit filter generalizes beyond the IDEaS portal.

**Good-fit signals:** multi-modal data fusion · entity resolution / re-ID · maritime / Arctic /
ISR · explainable human-in-the-loop decision support · "open infrastructure / software backbone"
framings · individual- or low-partner-dependency calls.

## Relationship to siblings (important — don't confuse the repos)

- `../planetar/` — the **filed CH13 bid** (`W7714-248676/013`, submitted ~2026-05-30). This is the
  canonical proposal spine. `planetar-grants` workspaces **reuse** its artifacts (portfolio,
  GBA+, budget structure, benchmark report, glossary, patent framing) — lift-and-adapt, don't
  re-derive. `planetar-fce/README.md` and `FIT.md` map exactly what transfers.
- `../CLAUDE.md` — the parent workspace's instructions; it documents the planetar code repos and
  proposal conventions. **It applies here too** (it's auto-loaded). This file adds the
  grants-portfolio-specific layer on top.
- The actual planetar **code** (`planetar-broker`, `zmesg`, `planetar-ui`, `planetar-ais`,
  `planetar-ontology`, `planetar-market`, doibio entity graph) lives in other repos under
  `~/github/`. Per the provenance rule: when a draft cites a benchmark, LOC count, or repo path,
  **verify against the actual repo**, don't recall from notes.

## Proposal authoring conventions (shared across workspaces)

The IDEaS workspaces (`planetar-fce`, `planetar-true-north`) mirror the `../planetar/` layout —
filenames are stable, cite by name when working across files:

- `CHALLENGE.md` / `01-CHALLENGE.md` — challenge research note + rubric/outcome mapping
- `FIT.md` — go/no-go + Essential-outcome → planetar-asset map (the must-pass gate)
- `THESIS.md` — single source of truth all narratives must match (FCE-specific)
- `02-STRATEGY.md`, `03-ARCHITECTURE.md`, `08-OPEN-QUESTIONS.md`
- `proposal/` — the narratives that get submitted: `MC-1_trl`, `MC-2_alignment` (mandatory,
  pass/fail) + `PRC-1_st_merit` (10pts), `PRC-2_novelty` (20), `PRC-3_impact` (20),
  `PRC-4_feasibility` (20), `PRC-5_gba_plus` (5), `PRC-6_desired_outcomes` (15), `PRC-7_budget`.

**CFP6 evaluation framework (CH13 = CH14, identical):** MC pass/fail + PRC weighted to 70-pt
threshold, **3,000-character cap per field**, 1a/1b/2 component ladder with **1a (TRL 1–3) the
honest lane**. Narrative drafts are workspace Markdown with headings; **strip headings and
char-count the stripped paste block before submission** (the budgets target ≤2,950 with buffer).

## Working norms (carried from `../CLAUDE.md`)

- **Provenance over polish.** Every claim traces to a measurement, repo path, or citation. Don't
  soften the verifiable spine (patent, benchmark, LOC, dataset URL) into marketing.
- **Conservative claims.** Headline benchmark is `p50 80–140 ns / p99 400–900 ns` (brackets four
  measured runs); don't advertise un-measured post-tuning numbers.
- **Patent framing.** Always "applicant-named inventor on US Patent 10,936,582" (Salesforce-
  assigned, Steven Ness 1 of 19 named inventors). Never claim ownership.
- **Dates are absolute.** Write `2026-07-14`, never "next month." Each research note dates its
  facts and warns that deadlines/terms move — re-verify before acting.
- **One thesis per bid.** Don't copy CH13's learned-fusion-model thesis into CH14 — CH14 inverts
  it (the provenance/compliance substrate is the hero). `planetar-fce/THESIS.md` is the SSOT;
  fix any narrative that drifts from it.
