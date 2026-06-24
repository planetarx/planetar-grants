# FIT — DIANA 2027 ISR challenge: go/no-go + evidence

> The must-pass gate before effort. Uses the repo's two-screen fit filter
> ([../planetar-brainstorm/README.md](../planetar-brainstorm/README.md)) plus DIANA's own gates.
> TRL evidence verified against the actual repos on **2026-06-22** (provenance rule — not recalled).

## The two-screen fit filter

| Screen | Test | Result |
|---|---|---|
| **#1 — Honest TRL** | Is the gated TRL reachable honestly? DIANA requires **TRL 4+**. | ✅ **PASS** — substrate is **at TRL 4** today (evidence below). This is the key difference from the True North / TS13 no-bids, where the gated TRL was genuinely out of reach. |
| **#2 — Software-essential deliverable** | Is the scored deliverable software/AI/data, not hardware? | ✅ **PASS, cleanly** — the ISR challenge is pure sensor-fusion + analytics software. No airframe/optics/RF-aperture gate. |

**Both screens pass** — the first non-IDEaS opportunity to do so. The blocker is therefore **not
fit**; it's **bandwidth + the corporate-applicant question** (see "Open risks").

## TRL evidence (verified against the repos, 2026-06-22)

**Standard:** TRL 4 = components **integrated and validated working together in a lab**;
TRL 5 = validated in a **relevant environment** (real-world-representative data/conditions).

| Layer | Repo | Verified state | TRL |
|---|---|---|---|
| Envelope | `zmesg` | self-describing format (UUIDv7, ns ts, correlation/causation ids); used across all components | 4 |
| Bus | `planetar-broker` | ~1.4k LOC C11, 4 transports, WAL, tests; **benchmarked** p50 80–140 ns / p99 400–900 ns SHM (measured, predecessor) | 4–5 |
| AIS | `planetar-ais` | live aisstream + mock; Victoria + Strait-of-Hormuz theatres; → bus | 4–5 |
| SAR | `planetar-sat` | **real Sentinel-1** scenes (Copernicus), CFAR detector, land mask, geocoder; → bus + UI `#sar-detections` | 4 |
| EO | `planetar-eo` | **live** BC Ferries + Hakai webcams, YOLO, re-ID; → bus | 4–5 |
| Acoustic | `planetar-acoustic` | **live** ONC + OrcaSound hydrophone, Lyons cochlear model + classifier; → bus | 4–5 |
| Entity graph | `planetar-ontology` | 5 phases done, **30 tests pass**, "verified live against running broker", dark-vessel kinematic re-ID, Object API + WS | 4 |
| Shell | `planetar-ui` | React 19, TCP↔WS bridge, live map, per-vessel + detector channels | 4 |

**Integration — verified vs. gap:**
- ✅ **End-to-end verified**: AIS → broker → bridge → UI, two live theatres, dark-vessel AIS-drop
  on a live map (`planetar/HANDOFF-DEMO.md`, "done and verified", 2026-05-19).
- ✅ SAR → broker → UI channel; bus ↔ ontology verified live per phase.
- ✅ **Gap 1 — CLOSED (code) 2026-06-23.** The fused entity graph + re-ID is now surfaced in the
  shell: added `OntologyClient.getLinks()` and a "Re-identified · N cross-sensor matches" block per
  vessel card (`planetar-ui` `src/lib/ontology.ts`, `src/components/tabs/GraphTab.tsx`, `App.css`).
  `tsc -b` passes. (In-browser view pending a local `vite`/rolldown reinstall — see [DEMO.md](DEMO.md).)
- ✅ **Gap 2 — CLOSED + VERIFIED 2026-06-23.** A deterministic driver (`planetar-ontology/tools/
  demo-reid.ts`) runs AIS→dark→SAR→EO on the live bus; the entity graph re-identifies one vessel
  across **two** sensor domains (links: `planetar-sat` then `planetar-eo`, score 0.9 each), with
  field-level provenance fusing AIS + EO. Runbook + verified output in [DEMO.md](DEMO.md).

**Verdict:** **planetar is at TRL 4 now** (several components at 5 on live data), and the
demonstrated cross-sensor re-ID — the bid's centerpiece — now **runs and is verified end-to-end**.
The remaining distance is hardening + NATO-relevant-environment validation: **exactly what DIANA's
€100K + test-centre access funds (TRL 4 → 5/6).**

## Challenge outcome → planetar asset map

| ISR challenge asks for | planetar asset | Honest gap DIANA would fund |
|---|---|---|
| Fusion across **platforms** (autonomous, satellite, ground) | satellite SAR (`-sat`) + satellite/terrestrial AIS (`-ais`) + ground EO (`-eo`) + subsea acoustic (`-acoustic`) on one bus | UAS/autonomous-platform adapter; broader sensor onboarding |
| Fusion across **sources, formats, security classifications** | `zmesg` envelope normalizes formats; bus carries provenance + correlation ids | classification-aware routing / multi-level-security partitioning |
| **Analytics / AI / causal models** | entity resolution + kinematic dark-vessel re-ID (`-ontology`) | learned multi-sensor association; predictive track models |
| **Actionable, causality-based intelligence** | provenance lineage (UUIDv7 + correlation/causation) → auditable "why" per entity | surface lineage/causality in the analyst shell |
| **Predictive insights** | kinematic re-acquisition of vessels that drop AIS | probabilistic forecast of re-emergence location/time |
| **Situational awareness UI** | `planetar-ui` 4-pane analyst shell, live | wire entity-graph view (Gap 1) for the fused picture |

Strong, honest alignment — the challenge reads like a spec for what's already half-built.

## Open risks (the real blockers — not fit)

1. **Bandwidth / deadline collision** — DIANA closes **2026-07-02**, IDEaS **CH14 closes
   2026-07-14**. Two proposals + a CH14 demo in ~3 weeks, solo. The accelerator itself is a
   multi-month commitment if selected. **This is the binding constraint.** Mitigation: the quad
   chart + long-form reuse the CH13/CH14 spine heavily; the TRL-4 demo work overlaps CH14.
2. **Corporate-applicant (C1) — RESOLVED 2026-06-22.** Lead applicant is **Zax Analytics**, a
   **British Columbia–registered company** (Canada, a NATO member nation); **Steven Ness is a
   Director & CEO**, so he is an authorized representative and the bid is filed by a company, not
   an individual — clearing DIANA's eligibility bar. Residual check (low risk): confirm the cap
   table is **majority owned & controlled by NATO nationals** (true if all shareholders are
   Canadian) before the business-identification step. *(Note: the separate IRAP/SR&ED "who claims"
   question is a tax matter for the accountant — not blocking for DIANA.)*
3. **TRL self-assertion** — claiming TRL 4 must survive a panel that may ask for the live demo.
   Mitigation: close Gap 1 + capture Gap 2 before the pitch stage (not needed for the written
   submission, but needed for the 30-min panel).
4. **Accelerator obligations** — selection implies travel/time at test centres + reporting. Park
   as a "if selected" cost; doesn't affect the application decision.

## Recommendation

**GO — confirmed 2026-06-22 (founder).** Fit is excellent, the TRL gate is honestly cleared
(TRL 4 verified), and C1 is resolved (Zax Analytics, BC; Steven Ness Director & CEO). **Decision:
submit the DIANA 2027 bid before 2026-07-02 12:00 BST.**

`[x]` **submit 2027** · `[ ]` defer to 2028 (timing)

Remaining to submit (portal: **https://proposals.diana.tech/**):
(a) ⚠️ **DUNS number for Zax** (UEI no longer accepted) — required to register *and* submit; **check
the DUNS lookup first** (Zax may already have one → instant: dnb.com/duns-number/lookup.html), else
request from D&B (several days) — do this **first**; (b) register the portal account (needs an authenticator app for
2FA) + download DIANA's official Quad Chart + Long-Form templates and transfer content;
(c) fill remaining `[TODO]` founder facts (traction metrics, collaborators, contact);
(d) confirm the majority-NATO-national cap-table check. The two integration gaps below matter only
for the **pitch stage**, not the written submission.
