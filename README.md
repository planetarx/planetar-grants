# planetar-grants — funding pursuits for the planetar platform

Funding pursuits for **planetar** (Zax Analytics / Steven Ness) **other than** the
submitted IDEaS CFP6 CH13 bid (that lives in `../planetar/`, under evaluation since
2026-06-01). This README is the dashboard; per-opportunity detail lives in each
workspace.

**Last updated: 2026-10-22** (MINERVA Deconfliction not bid → lane B; CH17 pass; Ocean Startup + Schmidt outcomes still unrecorded). Previously 2026-10-06 (NIWC row + IDEaS CH17 watch from the procurement scan; MINERVA row 2026-09-29; earlier rows as of 2026-08-13). Dates and program terms move — each workspace lists its
sources; re-verify before acting.

## ✅ Submitted — under evaluation

| Opportunity | Ask | Submitted | Vehicle | Record |
|---|---|---|---|---|
| **IDEaS CFP6 CH14** "Reliable AI Sensor Fusion" (`W7714-248676/014`), Component 1a — Fusion Compliance Engine | **$181,000 CAD** (TRL 2→3, 25 wk, two-person) | **2026-07-20** as **CP6-144220** (replacement of CP6-143774; evaluation ~3–6 mo) | Zax Analytics | [`planetar-fce/submission-record.md`](planetar-fce/submission-record.md) — authoritative; planetar.ca must stay evaluator-drivable |

## 🔴 Live applications (act this month)

| Opportunity | Ask | Deadline | Vehicle | State | Workspace |
|---|---|---|---|---|---|
| **US Navy NIWC Pacific CSO — Data and Analytics for Maritime Domain Awareness** (`N66001-26-S-C036`) | no ceiling; awards "not expected to exceed $100M"; rough price `[TODO]` | ⏰ **2027-01-07 16:00 Pacific** (5-page solution brief by e-mail) | **Zax Analytics** (to confirm; foreign-owned welcome, SAM.gov before award) | ⚖️ **Screened 2026-10-06, decision pending** — both fit screens pass; source identification + methodology map to built code; gaps: no measured detection performance, no S3/bulk delivery, data rights unchecked. Lanes: (A) brief now · (B) close gaps then brief · (C) team under a prime (`FIT.md`) | [`planetar-niwc-mda/`](planetar-niwc-mda/) |
| **Emergent Ventures** (Mercatus) | **US$50K** | ❌ **DECLINED 2026-07-24** (same-day) — resubmission invited | Steven, individual | Form rejection, no reasons (EV norm); reapply after a fresh milestone (`SUBMISSION.md`) | [`planetar-emergent-ventures/`](planetar-emergent-ventures/) |
| **Ocean Startup Challenge** 2026–27 | up to $25K CAD | 🎯 **SHORTLISTED 2026-08-12** — interview **2026-08-17 15:00 EDT** (Zoom) | Steven, individual (new entity on win) | 15-min interview: 3-min pitch + 12-min panel Q&A; confirm presence by replying to the 2026-08-12 email (`SUBMISSION.md`) | [`planetar-ocean-startup/`](planetar-ocean-startup/) |
| **Schmidt Marine Technology Partners** | year-1 band **$150–200K** ($350K total) | ✅ **SUBMITTED 2026-07-24** — full-proposal invites by 2026-09-01 | **Zax Analytics** (Steven CEO) | Filed as Sustaining Fisheries, TRL 3; confirmation received (`SUBMISSION.md`) | [`planetar-schmidt-marine/`](planetar-schmidt-marine/) |

## 🟡 On hold / watches

| Opportunity | Why waiting | Next action |
|---|---|---|
| **NLnet / Restack** (€5K–50K) | Aug-1 call is Taler/Fediversity only; Restack / regular call reopens **after summer 2026** (verified 2026-07-02) | Check `nlnet.nl/propose` **monthly**; submit [`drafts/01`](planetar-brainstorm/drafts/01-nlnet-application.md) immediately when open (only `[TODO]`: phone) |
| **NRC IRAP + SR&ED** (Track B, $75K–$1M) | Unblocked (D1 + C1) — needs the first conversation | **Call 1-877-994-4727** for an ITA; keep contemporaneous R&D records; accountant confirms share split (SR&ED rate) |
| **CSA smartEarth** (≤~$250K AOs) | No open AO confirmed 2026-07-02 | Quarterly check (next ~2026-10-01) — [`planetar-smartearth/`](planetar-smartearth/) |
| **Compute credits** (NVIDIA Inception, AWS Activate, Google for Startups) | Not cash but offsets the GPU training spend | Apply under Zax; low effort |
| **IDEaS/MINERVA · ISC Challenge Stream · NATO DIANA** | Standing watches | Bid only software/AI-essential calls (the no-bid lesson). **2026-09-29:** MINERVA's 2026 calls run through **ISC Phase 2 (TRL 5–9, SMEs only)**, not IDEaS 1a — see [`planetar-minerva/`](planetar-minerva/) |
| **IDEaS CFP6 CH17** "RF Data Fusion for Command and Control" (`W7714-248676/017`; 1a up to $250K CAD) | 🛑 **PASS — closed 2026-10-20, not screened** (decided 2026-10-22). Essentials were message conversion (MTF-XML, NIEM, NATO Core Data Framework), not fusion | Reference only — [`planetar-brainstorm/08-procurement-scan-2026-10-06.md`](planetar-brainstorm/08-procurement-scan-2026-10-06.md); keep watching `W7714-248676` for /018+ |
| **MINERVA — UAS Deconfliction** (ISC Call 004, `EN578-24ISC4/94`; up to $500K × ~5) | 🛑 **Closed 2026-10-21, NOT BID** (no lane chosen in time; solo bid failed the TRL 5–9 gate anyway). **Lane B chosen 2026-10-22:** build the app to TRL 5 for the next call | Open the build repo + R&D log; contact `MINERVA.Initiative@forces.gc.ca` — checklist in [`planetar-minerva/README.md`](planetar-minerva/README.md) § Status |
| **ONC outreach** (Victoria) | Relationship, not a cheque; compounds into Mitacs/OSC/Schmidt | Find contact, send [`drafts/03`](planetar-brainstorm/drafts/03-onc-outreach-email.md) |

## Decisions on record → [`planetar-brainstorm/DECISIONS.md`](planetar-brainstorm/DECISIONS.md)

- **D1** Zax Analytics incorporated; **C1** Steven is CEO → IRAP/SR&ED track unblocked.
- **D2** License — **superseded by D2a (2026-07-27): single-license GPLv3 + paid services** (zmesg stays Apache-2.0; dual-license dropped). **C3** applied 2026-06-03.
- **D3** Civilian-forward identity for OSS/ocean funders; defence face for IDEaS/DIANA.
- **D4** (2026-07-04) Vehicle doctrine: **individual** for Ocean Startup / EV / NLnet;
  **Zax** for Schmidt Marine / IRAP / SR&ED.
- **D5** (2026-07-04) EV ask US$50K, split 25/15/10.
- **D6** (2026-07-04) Schmidt Marine: Zax applicant, US$200K over 18 months.
- **⚠️ Still open:** dilutive-funding stance (equity/VC — BDC StrongNorth path). No
  deadline pressure.

## Remaining founder inputs (nothing else blocks)

1. Founder **phone** (NLnet form, for the fall window).
2. **Schmidt budget line items** (US$200K shape) + portal field mapping at first login.
3. **Ocean Startup interview 2026-08-17 15:00 EDT:** confirm presence (email reply) + prep
   the 3-min pitch and panel Q&A.
4. Later: YouTube/demo-video/sponsor links in the one-pager; GitHub Sponsors + Open
   Collective handles ([`drafts/04`](planetar-brainstorm/drafts/04-license-and-funding-setup.md)).
5. The **equity stance** decision (records as D7 when made).
6. ~~**MINERVA Deconfliction lane**~~ — closed 2026-10-21 not bid; **lane B chosen 2026-10-22**
   (build for the next call — [`planetar-minerva/README.md`](planetar-minerva/README.md)).
7. **NIWC lane** — (A) brief now / (B) close gaps then brief / (C) team / stop. Independent of
   the lane and with lead time: start SAM.gov registration; e-mail the notice's contact
   ([`planetar-niwc-mda/FIT.md`](planetar-niwc-mda/FIT.md)).
8. ~~**IDEaS CH17**~~ — pass (closed 2026-10-20; recorded 2026-10-22).

## Repo map

| Directory | What | State |
|---|---|---|
| [`planetar-brainstorm/`](planetar-brainstorm/) | Funder research (00–06), `DECISIONS.md`, reusable drafts | Active — the map |
| [`planetar-fce/`](planetar-fce/) | IDEaS CFP6 CH14 Fusion Compliance Engine bid | ✅ **submitted (CP6-144220, replacement filed 2026-07-20)** — under evaluation |
| [`planetar-emergent-ventures/`](planetar-emergent-ventures/) | EV grant application | ✅ Ready to submit |
| [`planetar-ocean-startup/`](planetar-ocean-startup/) | Ocean Startup Challenge application | 🎯 shortlisted 2026-08-12 — interview 08-17 |
| [`planetar-schmidt-marine/`](planetar-schmidt-marine/) | Schmidt Marine initial proposal | ⏰ closes 07-31 |
| [`planetar-smartearth/`](planetar-smartearth/) | CSA smartEarth watch | 👀 quarterly |
| [`planetar-true-north/`](planetar-true-north/) | IDEaS True North Precision (/012) | 🛑 no-bid 2026-05-31 (reference) |
| [`planetar-innovation/`](planetar-innovation/) | ISC Testing Stream TS13 | 🛑 no-bid 2026-06-01 (reference) |
| [`planetar-minerva/`](planetar-minerva/) | Canadian Army MINERVA 2026 — six ISC Phase-2 calls: five hardware no-bids + **UAS Deconfliction** | 🛑 Deconfliction not bid (closed 2026-10-21) → lane B build-for-next (2026-10-22) |
| [`planetar-niwc-mda/`](planetar-niwc-mda/) | US Navy NIWC Pacific CSO — maritime domain awareness data and analytics (first procurement, first non-Canadian pursuit) | ⚖️ screened 2026-10-06, decision pending — closes **2027-01-07** |

**History of this push:** funder scan + shortlist built 2026-06-01→03 (post-CH13);
re-verified and expanded 2026-07-02→04 (NLnet correction, Schmidt Marine + Emergent
Ventures + smartEarth added, vehicles + asks decided, drafts completed).
