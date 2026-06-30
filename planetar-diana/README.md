# planetar-diana — NATO DIANA 2027 (ISR sensor-fusion challenge)

**Status dashboard.** Workspace for a bid into NATO DIANA's **2027** challenge
**"Multidomain Sensing and Advanced Data Processing for Intelligence and Surveillance."**
The first non-IDEaS opportunity to pass *both* fit screens (honest TRL + software-essential).

Created 2026-06-22. **Deadline-driven and fast-moving — re-verify every DIANA fact on the portal
before acting.** Deadline: **2026-07-02** (portal cards say "Submission ends Jul 2"; the email cites
2026-07-03 12:00 BST — **work to Jul 2**).

## The 60-second version

- **What:** open, provenance-native multi-domain sensor fusion + cross-sensor re-identification —
  already running on live feeds. Thesis SSOT: [THESIS.md](THESIS.md).
- **Why it fits:** the challenge reads like a spec for what's half-built; both fit screens pass.
- **Maturity:** **TRL 4 today** (verified against the repos 2026-06-22 — [FIT.md](FIT.md)); DIANA
  funds TRL 4 → 5/6. This is the clean break from the True North / TS13 no-bids.
- **Award:** €100K accelerator (+ up to €300K Mission Track) + NATO test centres & end-users.
- **The real blocker is bandwidth**, not fit: DIANA closes 2026-07-02, **CH14 closes 2026-07-14**.

## Files

| File | Role | State |
|---|---|---|
| [CHALLENGE.md](CHALLENGE.md) | Challenge research note — requirements, gates, criteria, dates, sources | ✅ drafted |
| [FIT.md](FIT.md) | Go/no-go + **evidence-backed TRL-4 assessment** + outcome→asset map + risks | ✅ drafted |
| [THESIS.md](THESIS.md) | Single source of truth all narratives must match | ✅ drafted |
| [proposal/quad-chart.md](proposal/quad-chart.md) | 1-page quad chart **content** (4 quadrants) | ✅ draft — needs transfer to official template |
| [proposal/long-form.md](proposal/long-form.md) | 4-page proposal **content**, mapped to scoring criteria | ✅ draft — runs long, cut to 4pp in template |
| [proposal/pitch.md](proposal/pitch.md) | Stage-3 panel: 10-min deck (slide-by-slide) + 20-min Q&A prep | ✅ draft |
| [DEMO.md](DEMO.md) | Reproducible cross-sensor re-ID demo — runbook + verified output | ✅ verified 2026-06 |

## What transfers from the CH13/CH14 spine (lift-and-adapt)

- One-pager, architecture, **benchmark report** (`planetar/docs/benchmark-2026-04-27.md`), patent
  framing, applicant bio, dual-use posture, GBA+/ethics language — all reusable.
- Do **not** reuse CH13's learned-fusion thesis or CH14's compliance-substrate thesis verbatim —
  DIANA's hero is the demonstrated fusion + re-ID capability ([THESIS.md](THESIS.md)).

## Open items (blockers & must-dos before submit)

1. ~~Bandwidth go/no-go~~ — ✅ **GO confirmed 2026-06-22.** Submitting before 2026-07-02.
2. ~~C1 — lead applicant entity~~ — ✅ **RESOLVED.** Applicant = **Zax Analytics** (BC-registered
   Canadian company); **Steven Ness, Director & CEO**. Residual: confirm majority-NATO-national
   cap table before business-identification. ([FIT.md](FIT.md))
3. **Format compliance** — download DIANA's official **Quad Chart + Long-Form templates** from the
   portal and paste content in; obey font/page rules (non-compliant = auto-reject).
4. **`[TODO]` founder facts** — company/role, any traction metrics, collaborator list, contact.
5. ~~Pitch-stage integration gaps~~ — ✅ **CLOSED 2026-06-23.** Cross-sensor re-ID demo runs and is
   verified end-to-end; the shell now renders the re-ID evidence. Runbook: [DEMO.md](DEMO.md).
   Remaining for a *live screen* demo: a local `vite`/rolldown reinstall (npm optional-deps bug,
   not our code — see [DEMO.md](DEMO.md)).

## Next actions (decision = GO; portal: https://proposals.diana.tech/)

1. ⚠️ **DUNS number for Zax Analytics** (UEI no longer accepted) — required to register *and* submit.
   **Check the lookup first** (Zax may already have one → instant): https://www.dnb.com/duns-number/lookup.html;
   else request from D&B (several days). **Do this first** (the one true deadline blocker).
2. Register the portal account (authenticator-app 2FA) → download the official Quad Chart + Long-Form
   templates.
3. Transfer content from [proposal/](proposal/), fill remaining `[TODO]` founder facts (traction
   metrics, collaborators, contact), confirm the cap-table check, cut to 1pp/4pp, **submit before
   2026-07-02 12:00 BST**.
4. The verified TRL-4 evidence ([FIT.md](FIT.md)) + the re-ID demo ([DEMO.md](DEMO.md)) are reusable
   in CH14's feasibility/validity sections.

## Relationship to siblings

Reuses the [`../../planetar/`](../../planetar/) CH13 spine and the
[`../planetar-fce/`](../planetar-fce/) CH14 work; the funding-radar entry is
[`../planetar-brainstorm/07-funding-radar.md`](../planetar-brainstorm/07-funding-radar.md)
(row 4) and the go/no-go originated in
[`../planetar-brainstorm/03-defence-dualuse.md`](../planetar-brainstorm/03-defence-dualuse.md).
