# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

`planetar-grants` (git: `git@github.com:planetarx/planetar-grants.git`) is Zax Analytics'
**funding-pursuits portfolio** for the planetar platform — every pursuit *other than* the filed
IDEaS CFP6 CH13 bid, which lives in the sibling repo `../planetar/`. It is **Markdown only — no
code, no build, no lint, no tests.** The work is researching opportunities, screening them with
the fit filter, recording bid/no-bid/hold decisions, authoring application drafts, and — for
filed pursuits — tracking outcomes. Several workspaces now hold **submitted applications under
evaluation**; their filed text follows the same no-silent-edits rule as `../planetar/`.

**Git layout exception:** unlike most `planetarx/` subdirectories, this directory *is* the git
repo — the workspaces inside are plain directories, not nested repos. Commit here.

Workspace-wide norms from `../CLAUDE.md` (provenance over polish, conservative claims, the exact
patent phrasing, absolute dates) apply fully.

## Where current state lives (read before assuming anything)

- **Each workspace's own `README.md` is the authoritative per-opportunity status dashboard.**
  Read it before acting in that workspace — the **whole** file: status flips land in the
  `## Status:` section at the end, and top banners can lag behind it (a stale "ACTIVE"
  banner can sit above a DECLINED status).
- The top-level `README.md` is the portfolio dashboard (live deadlines, vehicles, asks, remaining
  founder inputs) — useful, but it lags when work lands in bursts. When a status changes, update
  **both** the workspace README and the top-level dashboard.
- **Everything here is dated snapshot research.** Deadlines, TRL gates, and program terms move —
  re-verify against each file's listed sources before acting on or repeating a date, amount, or
  eligibility claim, and date the update.

## Layout — one directory per pursuit

States verified 2026-08-16 (MINERVA row added 2026-09-29); trust the workspace READMEs over this table.

| Directory | Opportunity | State |
|---|---|---|
| `planetar-brainstorm/` | The funding map: pitch framing (`00`), funder research (`01`–`05`), shortlist + calendar (`06`), announcement-channel radar (`07`), `DECISIONS.md`, reusable `drafts/` | Active reference |
| `planetar-fce/` | IDEaS CFP6 **Challenge 14** "Reliable AI Sensor Fusion" (`W7714-248676/014`), Component 1a, Fusion Compliance Engine thesis | ✅ **SUBMITTED — CP6-144220** (replacement, filed 2026-07-20; $181K, TRL 2→3). Under evaluation ~3–6 mo; `submission-record.md` is authoritative; `proposal/` + `submission/` text is **filed**; planetar.ca must stay evaluator-drivable |
| `planetar-diana/` | NATO DIANA 2027 "Multidomain Sensing…" accelerator (€100K + up to €300K) | **NOT SUBMITTED** — 2026-07-02/03 window missed on the DUNS blocker (recorded 2026-07-13); DUNS request in flight; workspace stays content-complete for the next DIANA call |
| `planetar-emergent-ventures/` | Emergent Ventures / Mercatus (US$50K, individual, rolling) | ❌ **DECLINED 2026-07-24** (same-day, no reasons — EV norm); resubmission explicitly invited — reapply after a fresh milestone (`SUBMISSION.md`) |
| `planetar-ocean-startup/` | Ocean Startup Challenge 2026–27 (≤$25K CAD) — applied as **individual**, not Zax; new entity on win | 🎯 **SHORTLISTED 2026-08-12** (submitted 2026-07-23) — interview 2026-08-17 15:00 EDT; prep kit `INTERVIEW.md` |
| `planetar-schmidt-marine/` | Schmidt Marine Technology Partners (year-1 US$150–200K, annual renewals) — **Zax** applicant, civilian face only | ✅ **SUBMITTED 2026-07-24** — full-proposal invites by 2026-09-01 |
| `planetar-irap/` | NRC IRAP (AI Assist + DI Assist streams) + SR&ED | **ON HOLD** (2026-06-30, pending cash flow) — `DECISION-hold.md` has the re-engage trigger |
| `planetar-smartearth/` | CSA smartEarth EO-applications AOs (≤~$250K) | WATCH — quarterly check |
| `planetar-true-north/` | IDEaS "True North Precision" (`W7714-248676/012`) | NO-BID (2026-05-31) — reference |
| `planetar-innovation/` | ISC Testing Stream TS13 (`EN578-26ISC1`) | NO-BID (2026-06-01) — reference |
| `planetar-minerva/` | Canadian Army **MINERVA** 2026 cycle — six ISC Call 004 **Phase 2** calls (TRL 5–9, $500K, incorporated SMEs only). Five hardware calls NO-BID (2026-09-23); **UAS Deconfliction `EN578-24ISC4/94`** — all-software Essentials — closed **2026-10-21 NOT BID** | 🛑 Not bid; **lane B (build to TRL 5 for the next call) chosen 2026-10-22** — checklist in its README `## Status`; `FIT.md`, `THESIS.md` draft |
| `planetar-niwc-mda/` | US Navy NIWC Pacific CSO `N66001-26-S-C036` — data and analytics for maritime domain awareness, feeds into SeaVision; first procurement, first non-Canadian pursuit; SAM.gov (NCAGE first) needed before award | 🛠️ **Lane B** (2026-10-22): close gaps, then brief — target send 2026-12-18, closes 2027-01-07; `BRIEF-outline.md` holds the build schedule |

## The fit filter (the load-bearing lesson of this repo)

Both no-bids died on the same two screens. Apply this *before* spending effort on any new
opportunity:

1. **Honest TRL — nuanced since the 2026-06-22 verification.** The IDEaS *funded R&D scope* (new
   fusion/compliance science) is honestly **TRL 1–3** — keep bidding Component 1a there. But the
   *demonstrated platform substrate* (bus + envelope + live detectors + entity-graph re-ID +
   shell) was verified **TRL 4** against the actual repos, with components at TRL 5 on live feeds
   (evidence: `planetar-diana/FIT.md`). So **TRL-4-gated calls are reachable** when the bid is
   framed around the demonstrated substrate. Still skip TRL 5+/operational-prototype gates unless
   a partner owns that maturity. *(Note: `planetar-brainstorm/README.md` still states the older,
   stricter "skip all TRL 4+" reading — the nuanced version here is current.)*
2. **The scored/Essential deliverable must be software/AI/data, not hardware.** When the
   must-pass outcomes are airframes, optics, RF apertures, or weapons, planetar can only be a
   backbone, never the prime. This is the more decisive screen — it killed both no-bids.

**Good-fit signals:** multi-modal fusion · entity resolution / re-ID · maritime / Arctic / ISR ·
explainable human-in-the-loop decision support · "open infrastructure / software backbone"
framings · individual-eligible or low-partner-dependency calls.

## Authoritative records — read before acting

- **`planetar-brainstorm/DECISIONS.md`** is the decision record — D1 (Zax incorporated, Steven is
  CEO), D2 (license — **superseded by D2a 2026-07-27: single-license GPLv3 + paid services;
  zmesg stays Apache-2.0**), D3 (per-funder identity), D4 (vehicle
  doctrine: individual vs Zax per funder), D5/D6 (EV and Schmidt asks), clarifications C1–C3.
  Check there before repeating any claim about eligibility, licensing, vehicles, or company
  structure.
- **`DECISION-no-bid.md` / `DECISION-hold.md` / `SUBMISSION.md` / `submission-record.md` are
  filed, dated records.** Don't rewrite them — append dated outcome updates (submitted →
  shortlisted → declined/won) or add new docs if circumstances change. Filed application text
  (e.g. `planetar-fce/proposal/` + `submission/`, filed form-kit answers) gets no silent edits.
- **Sensitive facts are deliberate on-the-record material:** C1 (company registration/officer
  details) and C2 (spouse works at Open Ocean Robotics → proactively disclose in ocean-sector
  applications) must be represented exactly as recorded in `DECISIONS.md`, never paraphrased
  loosely.

## Per-opportunity workspace pattern

When a new opportunity arrives, create `planetar-<name>/` and follow the established shape:

1. Raw capture (`idea.md` or `idea/` — forwarded email, screenshots)
2. `CHALLENGE.md` — verified research note, every fact sourced and dated
3. `FIT.md` — go/no-go against the fit filter + Essential-outcome → planetar-asset map
4. `THESIS.md` — single source of truth all narratives must match (for committed bids)
5. Numbered strategy/architecture docs (`01-…`, `02-…`, `08-OPEN-QUESTIONS.md`)
6. `proposal/` (and, for IDEaS, `submission/`) — or `DECISION-no-bid.md` with rationale
7. `SUBMISSION.md` on filing — the filed record plus a dated outcome log
8. `README.md` — the status dashboard, with a file index stating each doc's state

## IDEaS authoring conventions (CH13 = CH14, identical framework)

- **CFP6 evaluation:** MC-1/MC-2 pass/fail + PRC-1…7 weighted to a 70-pt threshold; **3,000-char
  cap per field**; 1a/1b/2 component ladder with 1a (TRL 1–3) the honest lane.
- Narrative drafts are workspace Markdown with headings; **strip headings and char-count the
  stripped paste block before submission** — budgets target **≤2,950** for buffer.
- **One thesis per bid.** CH13 = learned cross-modal fusion model; CH14 inverts it (the
  provenance/compliance substrate is the hero). Each bid's `THESIS.md` is its SSOT — fix any
  narrative that drifts, never cross-pollinate theses.
- **Lift-and-adapt from `../planetar/`** (portfolio, GBA+, budget structure, benchmark report,
  glossary, char-count protocol) — reuse the spine, not the thesis.

## Working norms specific to this repo

- **Claims must stay auditable — and unsoftened.** Capability claims trace to a repo path,
  measurement, or citation (`../planetar/docs/built-services-inventory.md`, benchmark doc
  `../planetar/docs/benchmark-2026-04-27.md`; headline is p50 80–140 ns / p99 400–900 ns). When a
  draft cites a benchmark, LOC count, or repo path, verify against the actual repo under
  `~/github/`, don't recall from notes.
- **`[TODO]` placeholders in drafts mark founder-only facts** (contacts, handles, exact budgets,
  phone). Never invent values for them.
- **Pitch framing is per-funder, per D3:** civilian/open-infrastructure face for OSS and ocean
  funders; dual-use/defence face for IDEaS/DIANA. One codebase, honest framing — never mix the
  faces in one document.
- **Patent framing:** always "applicant-named inventor on US Patent 10,936,582"
  (Salesforce-assigned, 1 of 19 inventors). Never any ownership phrasing.
- **Dates are absolute:** `2026-07-14`, never "next week."
