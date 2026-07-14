# HANDOFF — DIANA 2027 bid (resume-from-cold)

> **2026-07-13: OVERTAKEN BY EVENTS — the bid was NOT submitted** (DUNS did not arrive before
> the 2026-07-02/03 close; see the status update in `README.md`). Keep this handoff as the
> playbook for the next DIANA call.

> Written **2026-06-23**. Snapshot so the submission can be finished even if this session/person
> changes. **The bid is content-complete and GO; the only blocker is obtaining a DUNS number.**
> Working deadline: **2026-07-02.** Everything lives in `planetar-diana/`.

## TL;DR

- **Decision: GO** — submit the DIANA 2027 bid (`MyContent`/portal account already created by Steven).
- **Status:** all narrative content drafted; the differentiator (cross-sensor re-ID) **built + verified**.
- **The one blocker: a DUNS number** — required to register on the portal *and* to submit (UEI no
  longer accepted). **Check the lookup first — Zax may already have one** →
  https://www.dnb.com/duns-number/lookup.html
- **Deadline: 2026-07-02.** Portal challenge cards say "Submission ends Jul 2"; the welcome email
  says the window closes 2026-07-03 12:00 BST. **Work to Jul 2.**

## The opportunity (re-verify on the portal — DIANA pages move)

- **Program:** NATO DIANA 2027 cohort — 6-month accelerator, starts Jan 2027.
- **Challenge:** *Multidomain Sensing and Advanced Data Processing for Intelligence and Surveillance*
  — "integrated intelligence, surveillance, and reliable situational awareness across complex
  environments."
- **Award:** €100K accelerator; top performers up to **+€300K** (Mission Track).
- **Portal:** https://proposals.diana.tech/ (create user + company profile; **2FA via authenticator
  app**; **DUNS required**). Challenge info: https://www.diana.nato.int/challenges.html
- **Submission format:** 1-page **Quad Chart** + 4-page **Long-Form**, using **DIANA's official
  templates** (font/format enforced — non-compliant = auto-reject). Then a **30-min panel**
  (10-min pitch + 20-min Q&A).

## Decisions locked

- **GO** (founder, 2026-06-22) — first non-IDEaS opportunity to pass *both* fit screens (honest TRL +
  software-essential deliverable).
- **Applicant = Zax Analytics**, a **British Columbia–registered** Canadian company; **Steven Ness,
  Director & CEO** (resolves the C1 entity question; satisfies DIANA's company + majority-NATO-national
  rule). **Residual check:** confirm the cap table is majority owned/controlled by NATO nationals.
- **TRL framing:** the platform *substrate* is **TRL 4** (verified against the actual repos), several
  components **TRL 5** on live data, and cross-sensor re-ID is **demonstrated**. DIANA funds TRL 4→5/6.
  This is consistent with the IDEaS "TRL 1–3" framing — that scopes *new R&D layered on top* of the
  substrate. (Detail + evidence: `FIT.md`.)

## Workspace inventory (all in `planetar-diana/`)

| File | What it is |
|---|---|
| `README.md` | Status dashboard |
| `CHALLENGE.md` | Challenge research note — gates, criteria, dates, DUNS, sources |
| `FIT.md` | Go/no-go + evidence-backed TRL-4 assessment + risks (C1, bandwidth) |
| `THESIS.md` | Single source of truth all narratives match |
| `proposal/quad-chart.md` | 1-page quad chart content (4 quadrants) |
| `proposal/long-form.md` | 4-page proposal content, mapped to DIANA's scoring criteria |
| `proposal/pitch.md` | Stage-3: 10-min deck (slide-by-slide) + 20-min Q&A + backup slides B1–B9 |
| `DEMO.md` | Reproducible cross-sensor re-ID demo — runbook + verified output |
| `HANDOFF.md` | This file |

## The differentiator — verified cross-sensor re-ID (the bid's centerpiece)

A dark vessel is re-identified across **two sensor domains** (satellite SAR → EO) by the entity
graph, with field-level provenance. **Verified end-to-end 2026-06-23.** Full runbook + output in
`DEMO.md`. Reproduce:

```sh
# bus on :12001/:12002 (real broker, or the /tmp/planetar-broker-shim.mjs dev stand-in)
cd ~/github/planetarx/planetar-ontology && PLANETAR_ONTOLOGY_DB=/tmp/demo-reid.db npm start   # API :4000
cd ~/github/planetarx/planetar-ontology && node tools/demo-reid.ts
curl -s "localhost:4000/objects/planetar:Vessel?mmsi=316007777" | python3 -m json.tool
```
Expect: entity `MV Shadow Runner`, `status: reacquired`, provenance fused (AIS+EO), two
`reacquisition` links — `planetar-sat` (score 0.9, gap 40 min) + `planetar-eo` (0.9, gap 20 min).

## Code changes made this session (so they aren't lost)

All typecheck clean (`tsc -b`), lint clean for the changed files.
- **`planetar-ui`** (surfaces the re-ID in the shell):
  - `src/lib/ontology.ts` — added `getLinks()` + `LinkRecord` / `LinkWithTarget` types.
  - `src/components/tabs/GraphTab.tsx` — fetches + renders each vessel's `reacquisition` links
    ("Re-identified · N cross-sensor matches").
  - `src/components/tabs/MapTab.tsx` — new **"Re-ID / dark (fused)" overlay layer** from the ontology
    entities store (halo + dot, colored by status; toggle + popup).
  - `src/App.css` — `.entity-reacq*` / `.reacq-*` styles.
- **`planetar-ontology`**:
  - `tools/demo-reid.ts` — new deterministic demo driver (AIS→dark→SAR→EO).

## Environment issue (blocks ONLY the in-browser UI)

`vite` dev *and* build fail with a missing `@rolldown/binding-darwin-arm64` native binary — the known
npm optional-deps bug (npm/cli#4828), **not our code**. Fix before any live screen demo:
```sh
cd ~/github/planetarx/planetar-ui && rm -rf node_modules package-lock.json && npm i
```
The pipeline + Object API + the UI types are all verified independently of the browser.

## What's left to submit (the runway — all founder-side)

1. **DUNS** — check the lookup; if none, request from D&B (can take several business days). **This is
   the only thing that can blow the deadline.**
2. **Register** the portal account (authenticator-app 2FA) + company profile.
3. **Download** DIANA's official Quad Chart + Long-Form templates.
4. **Transfer** content from `proposal/` into the templates; **trim to 1pp / 4pp**.
5. **Fill the `[TODO]`s** (below).
6. **Submit by 2026-07-02.**
7. *(Optional, high-value for the pitch)* fix the bundler and record a demo screencast.

## Fill-in checklist (`[TODO]`s across the docs)

**Need before submit:**
- **Contact details** (email/phone).
- **Public open-source date** — resolve the discrepancy: one-pager says **2026-05-15**, GitHub
  initial commits show **2026-06-10**. Use the correct one. (`pitch.md` B1)
- **Collaborators** — list them, or confirm "solo" (the team section + Q&A handle solo). (`long-form.md`,
  `pitch.md` B6)

**Strengthens (honest "minimal/none" is fine):** traction numbers (GitHub stars/forks/contributors,
Sponsors/Open Collective, reach, press) — `long-form.md` Commercial + `pitch.md` B1; partner pipeline
(ONC/fisheries/research convos + LOIs) — `pitch.md` B1; use-of-funds % split — `pitch.md` B8;
in-program phase durations (from portal) — `long-form.md` + `pitch.md` B5; confirm h-index/citations —
`pitch.md` B6; optional: target test-centre (B5), named competitors (B7), market sizes (B9).

## Guardrails (keep the credibility spine intact)

- **Benchmark:** `p50 80–140 ns / p99 400–900 ns` (measured, brackets four runs) — never quote
  un-measured post-tuning numbers.
- **Patent:** always *"applicant-named inventor on US Patent 10,936,582"* (Salesforce-assigned, 1 of
  19). **Never** claim ownership.
- **TRL:** honest **4** for the substrate; don't inflate to a polished operational prototype.
- **Provenance over polish:** every claim traces to a repo path, a measurement, or a citation.

## Related (not in this workspace)

- **CH14 (`../planetar-fce/`)** — separate IDEaS bid, **handled in another session**; deadline
  **2026-07-14**. Reuses this bid's TRL-4 evidence + re-ID demo. Don't duplicate effort here.
- **GO record + funding radar:** `../planetar-brainstorm/03-defence-dualuse.md` (go/no-go),
  `06-shortlist-and-calendar.md` (calendar), `07-funding-radar.md` (channels + Gotham scan).
