# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this workspace is

`planetar-minerva/` (renamed from `planetar-inno/` on 2026-09-29) is the pursuit workspace for the
Canadian Army **MINERVA Initiative**'s 2026 cycle of six **Innovative Solutions Canada (ISC)
Challenge Stream** calls, inside `../` (the `planetar-grants` portfolio — a plain directory, not a
nested repo; **commit from `../`**). Markdown only; no build, lint, or tests. Verification is web
research with dated citations.

Two live facts drive everything here:

- **Five of the six calls are hardware-platform buys and are NO-BID (decided 2026-09-23)** —
  `DECISION-no-bid.md` is a filed record; append dated updates, don't rewrite.
- **The sixth, UAS Deconfliction (`EN578-24ISC4/94`), closed 2026-10-21 NOT BID**; on 2026-10-22
  the founder chose **lane (B): build to TRL 5 for the next call**. It was the first MINERVA call
  with all-software Essential outcomes (Phase 2, **TRL 5–9 mandatory**; the application is
  unbuilt, TRL ~2). `FIT.md` holds the screen and lane B's plan; `README.md` `## Status` holds the
  dated decision log and the lane-B checklist. **Read the whole
  README before acting** — the status section at the end is authoritative over the banner.

## Inherited rules (read them there)

- `../CLAUDE.md` — workspace pattern, the two-screen fit filter, authoritative-records rule,
  `[TODO]` placeholders, patent phrasing, absolute dates, per-funder face (**defence face** here, D3).
- `../../CLAUDE.md` — planetar-wide norms and the state of the filed CH13/CH14 bids.
- `../planetar-brainstorm/DECISIONS.md` — before any eligibility, vehicle, licensing, or company claim.
  Vehicle here is **Zax Analytics** (ISC requires an incorporated Canadian SME).

## Non-negotiables specific to this workspace

- **Never state a TRL the evidence doesn't support.** ISC Q2 is pass/fail on TRL 5–9 with an R&D
  record. Substrate TRL 4 was verified 2026-06-22 for maritime (`../planetar-diana/FIT.md`); the
  deconfliction application is TRL ~2 (2026-09-29). Re-verify against the repos before repeating
  either; never blend them into one number.
- **One thesis per bid.** `THESIS.md` is the SSOT: hybrid, with **planning as the must-pass core**
  (Essentials 1–7) and **live conformance as the differentiator** (Additional 1–2). No CH13
  learned-fusion model, no CH14 compliance engine, no dark-vessel pitch in Deconfliction text.
- **Essentials vs Additional.** planetar's strengths sit under *Additional* outcomes (≤10 of 130
  points). Any narrative that implies the planning core exists is false. Under lane A (partner-sub)
  the prime owns the Essentials; under lane B they are the build.
- **MINERVA ≠ IDEaS this cycle.** All six calls run through ISC Call 004 (Phase 2, $500K, SMEs
  only). The brainstorm docs' "MINERVA = IDEaS 1a, individual OK" reading is stale; a dated
  correction sits in `../planetar-brainstorm/03-defence-dualuse.md`. Don't reintroduce it.

## Gotchas

- `idea.md` is a Gmail screen paste (UI chrome, a Gemini "AI Overview" block). Cite the ISED
  pages and CanadaBuys, never the AI Overview. Leave the file as-is; it is the raw capture.
- **Name collision:** this is not `../planetar-innovation/` (ISC Testing Stream TS13 no-bid,
  2026-06-01). Link to it as prior art; don't edit it.
- Refer to the forwarder as prior workspaces do ("D. Huang"); don't copy the personal email
  address out of `idea.md`.
- CanadaBuys notice pages list firms that "registered interest in partnering" — a lead list for
  lane A, not endorsements. Research before contacting.
- "Windows-based" (Essential 1) vs. the Linux/epoll-only C broker: don't promise a broker port
  anywhere; the planning product's transport is a build-design decision.
- The Canada.ca MINERVA challenge list lags the ISED pages by weeks (it showed Deconfliction as
  "Upcoming" six days after the notice went live). Trust ISED + CanadaBuys for dates.

## Workflow

Established shape (`../CLAUDE.md` § per-opportunity pattern): `idea.md` → `CHALLENGE.md` →
`FIT.md` → `THESIS.md` → (`OUTREACH.md` | build repo | `proposal/`) → outcome log in `README.md`.
When a status changes, update **both** `README.md` here and the two dashboards: `../README.md`
(live table + repo map) and the layout table in `../CLAUDE.md`. Commit from `../` in the existing
style: `MINERVA: <what> — <date/outcome>`.
