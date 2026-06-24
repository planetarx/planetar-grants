# planetar-brainstorm — funding & sustainability for the OSS project

**What this is.** A working scratchpad for finding money to build and sustain
**planetar** as an open-source project — beyond the one live IDEaS CH13 bid.
Brainstorm + a scanned, dated map of funders that *actually fit* a solo Canadian
founder shipping software/AI/data-fusion at TRL 1–3.

Created 2026-06-01. These notes are a snapshot — **deadlines and program terms
move; re-verify before acting** (each file lists its sources).

## The fit filter (what we learned from two no-bids)

Both no-bid decisions ([ISC Testing Stream TS13](../planetar-innovation/DECISION-no-bid.md),
[True North Precision](../planetar-true-north/DECISION-no-bid.md)) failed for the
**same two reasons**. Use them as a screen before spending effort:

1. **Honest TRL is 1–3.** Skip anything gated at TRL 4+ unless a partner owns the
   maturity. Planetar's bus + envelope + UI + AIS ingest is early R&D.
2. **The deliverable must be software/AI/data, not hardware.** When the *essential*
   (must-pass) outcomes are airframes, optics, RF apertures, or weapons, planetar
   can only be a backbone, never the prime. Pass, or bid only with a hardware partner.

**Good-fit signals:** multi-modal data fusion · entity resolution / re-ID ·
maritime / Arctic / ISR domain awareness · explainable, human-in-the-loop decision
support · "open infrastructure / software backbone" framings · individual-eligible
or low-partner-dependency calls.

## How the files are organized

| File | Covers |
|---|---|
| [`00-FRAMING.md`](00-FRAMING.md) | How to pitch planetar to each funder type; eligibility reality-check; the creator/OSS flywheel |
| [`01-canada-non-dilutive.md`](01-canada-non-dilutive.md) | IRAP, SR&ED, Mitacs, ISC Challenge Stream, PacifiCan / Innovate BC, IDEaS |
| [`02-oss-funders.md`](02-oss-funders.md) | NLnet/NGI Zero, Sovereign Tech, GitHub Sponsors + Open Collective, MOSS, Linux Foundation |
| [`03-defence-dualuse.md`](03-defence-dualuse.md) | NATO DIANA, IDEaS future challenges, CDL Defence, BDC StrongNorth, EU SAFE, RDII |
| [`04-ocean-maritime.md`](04-ocean-maritime.md) | Ocean Supercluster, Ocean Startup Project, COVE, ONC (Victoria-local) |
| [`05-community-revenue.md`](05-community-revenue.md) | GitHub Sponsors, dual-license / open-core, services, YouTube + website flywheel |
| [`06-shortlist-and-calendar.md`](06-shortlist-and-calendar.md) | Ranked shortlist (fit × $ × effort) + a dated calendar of known windows |
| [`07-funding-radar.md`](07-funding-radar.md) | Announcement channels to subscribe to (with status + cadence) + a Gotham-adjacency scan mapping planetar's assets to programs beyond maritime |

## Top picks (the 60-second version)

Detail and reasoning live in [`06-shortlist-and-calendar.md`](06-shortlist-and-calendar.md).

1. **NLnet / Restack** — €5K–50K, rolling (~every 2 months, June 2026→2030), next deadline
   **2026-08-01**, **individual-eligible**, open-source-native, light application. Best first
   move. *(NGI Zero Commons Fund closed 2026-06-01; Restack is its successor.)*
2. **Ocean Startup Challenge** — up to $25K, TRL ≤6, **applications open 2026-06-05**.
   Victoria/maritime fit; low effort.
3. **NRC IRAP** (incl. new **AI Assist** + **Defence Industry Assist** streams) —
   $75K–$1M, *requires a Canadian incorporated for-profit*. Highest $, prerequisite work.
4. **ISC Challenge Stream** — Phase 1 ≤$150K, Phase 2 ≤$1M; same TRL band as CH13.
   Watch for a data-fusion / OSINT / MDA problem statement.
5. **NATO DIANA** — challenge-based, dual-use, ~annual call; Canada is well-represented.

## Decisions made (see [`DECISIONS.md`](DECISIONS.md))

- **D1 — Zax Analytics is incorporated** (~10 yr, has an accountant) → the high-$ Canadian
  stack (IRAP, SR&ED, ISC, Innovate BC) is **unblocked**. One clarification left: Steven's
  legal relationship to the company (it's his wife's) — affects who claims IRAP/SR&ED (C1).
- **D2 — License: permissive bus + AGPL platform** for wide adoption. Verified: only
  `planetar-broker` needs relicensing (AGPL→permissive); `ontology`/`registry` need a
  LICENSE added; rest already match. Plan: [`drafts/04-license-and-funding-setup.md`](drafts/04-license-and-funding-setup.md).

## Ready-to-use drafts → [`drafts/`](drafts/)

NLnet application, one-pager, Ocean Startup Challenge prep, ONC outreach email, and the
license/funding-rails setup are drafted in [`drafts/`](drafts/) (with `[TODO]` placeholders
for founder-only facts). Start there.
