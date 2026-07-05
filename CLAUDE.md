# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

`planetar-grants` tracks Zax Analytics' funding pursuits for the planetar platform **other than** the live IDEaS CFP6 CH13 bid (that one lives in `../planetar/`). It is **Markdown only — no code, no build, no lint, no tests.** The work here is researching funding opportunities, screening them, recording bid/no-bid decisions, and drafting applications.

Workspace-wide norms (provenance over polish, conservative claims, the exact patent phrasing, absolute dates) come from `../CLAUDE.md` — they apply fully here.

**Current state lives in `README.md`** (the dashboard: live deadlines, vehicles, decision pointers, remaining founder inputs) — read it before assuming what is or isn't done, and keep it updated when statuses change.

**Git layout exception:** unlike most `planetarx/` subdirectories, the three directories inside this repo are *not* nested git repos. `planetar-grants` itself is the repo — commit here.

## Layout

One directory per pursuit thread:

| Directory | What | State |
|---|---|---|
| `planetar-brainstorm/` | The live funding map: pitch framing (`00-FRAMING.md`), funder research by category (`01`–`05`), ranked shortlist + deadline calendar (`06`), `DECISIONS.md`, and ready-to-send application drafts in `drafts/` | **Active** |
| `planetar-ocean-startup/` | Ocean Startup Challenge 2026–27 (≤$25K, TRL ≤6) — apply as **individual**, not Zax | **ACTIVE — closes 2026-07-26**; draft answers live in `planetar-brainstorm/drafts/02` |
| `planetar-schmidt-marine/` | Schmidt Marine Technology Partners initial proposal (US$100K–400K, ocean philanthropy) — civilian face only | **ACTIVE — closes 2026-07-31** |
| `planetar-emergent-ventures/` | Emergent Ventures grant (US$1K–50K, individual, rolling) | **ACTIVE — rolling, submit ASAP** |
| `planetar-smartearth/` | CSA smartEarth EO-applications AOs (historically ≤~$250K) | **WATCH** — no open AO as of 2026-07-02; check quarterly |
| `planetar-true-north/` | IDEaS "True North Precision" drone+laser challenge (W7714-248676/012) | **CLOSED — no-bid** (2026-05-31); kept as reference if a hardware partner re-opens the system-integrator angle |
| `planetar-innovation/` | ISC Testing Stream TS13 (EN578-26ISC1) | **CLOSED — no-bid** (2026-06-01) |

The two closed workspaces follow a per-opportunity pattern — reuse it when a new opportunity arrives (new `planetar-<name>/` directory):

1. Raw capture (`idea.md` or `idea/` — forwarded email, screenshots)
2. `CHALLENGE.md` — verified research note / transcribed challenge text, every fact sourced and dated
3. Strategy/architecture docs (numbered `01-…`, `02-…`)
4. `DECISION-no-bid.md` (or a `proposal/`) — the outcome, with rationale, options considered, and a forward plan
5. A `README.md` whose file index states each doc's status

## Authoritative records — read before acting

- **`planetar-brainstorm/DECISIONS.md`** is the decision record: D1 (Zax Analytics incorporated, Steven is CEO), D2 (license model: permissive bus + AGPL platform), D3 (civilian-forward public identity), and clarifications C1–C3. Every other file cross-references these by number. Check current status there before repeating any claim about eligibility, licensing, or company structure.
- The **`DECISION-no-bid.md`** files are filed, dated decisions. Don't rewrite them — append dated updates or add new docs if circumstances change.
- The **fit filter** (`planetar-brainstorm/README.md`) screens new opportunities: (1) honest TRL is 1–3 — skip anything gated at TRL 4+ unless a partner owns the maturity; (2) the Essential/must-pass deliverable must be software/AI/data, not hardware platforms. Both no-bids failed exactly these two tests.

## Working norms specific to this repo

- **Everything is dated snapshot research.** Deadlines, TRL gates, and program terms move — re-verify against each file's listed sources before acting on or updating a date/amount/eligibility claim, and date the update.
- **Claims must stay auditable.** Capability claims trace to a repo path, measurement, or citation (see `../planetar/docs/built-services-inventory.md` and the benchmark doc before repeating one). Per `drafts/README.md`: don't soften them either.
- **`[TODO]` placeholders in `drafts/`** mark founder-only facts (contacts, handles, exact budgets). Never invent values for them.
- **Pitch framing is per-funder, per D3:** civilian/open-infrastructure face for OSS and ocean funders, dual-use/defence face for IDEaS/DIANA. One codebase, honest framing — don't mix the faces in one document.
- **Sensitive facts are deliberate on-the-record material:** C1 (corporation registered in Steven's wife's name; Steven is CEO) and C2 (spouse works at Open Ocean Robotics → proactively disclose in ocean-sector applications) must be represented precisely as recorded in `DECISIONS.md`, not paraphrased loosely.
