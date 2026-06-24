# 07 — Funding radar: announcement channels + Gotham-adjacency scan

Two jobs:
- **Part A — Channels to subscribe to** so the next CH13/CH14-style call lands in the inbox
  instead of being found late. Check the box once enrolled; keep the cadence column honest.
- **Part B — Gotham-adjacency scan** — domains a Palantir-Gotham-shaped stack serves, mapped
  to planetar's *actual* assets (bus + provenance envelope + multi-sensor fusion + entity
  resolution / re-ID + analyst shell) and to live/recurring programs found 2026-06-22.

Conventions carried from [`../CLAUDE.md`](../../CLAUDE.md): **absolute dates** (programs move —
re-verify before acting), **provenance over polish**, **honest TRL 1–3 + software-essential
deliverable** screen (the no-bid lesson; see [README](README.md) and [`06`](06-shortlist-and-calendar.md)).
Last swept: **2026-06-22**.

---

## Part A — Announcement channels (subscribe + monitor)

`[ ]` = not yet signed up · `[x]` = enrolled. **Minimum effective setup = rows 1 + 2** (they
catch ~90% of "grants like the ones in this repo"). Everything else is lane-specific coverage.

| # | Channel | What it catches | Signup / monitor URL | Status | Cadence |
|---|---|---|---|---|---|
| 1 | **CanadaBuys** account + keyword email alerts | **Every** federal solicitation: IDEaS, ISC, **CSSP**, all `W7714-…` DRDC/PSPC calls | https://canadabuys.canada.ca/en → account → Manage notifications (keywords: *sensor fusion, situational awareness, data fusion, AI, maritime domain awareness, entity resolution, OSINT*) | `[ ]` | passive (email) |
| 2 | **DND IDEaS** mailing list | Program-level CFP announcements (CFP6 = CH13/CH14) **weeks before** the formal CanadaBuys posting | https://www.canada.ca/en/department-national-defence/programs/defence-ideas.html · confirm via `tpsgc.paidees-apideas.pwgsc@tpsgc-pwgsc.gc.ca` | `[ ]` | passive + check quarterly |
| 3 | **Innovative Solutions Canada (ISC)** | Challenge Stream + Testing Stream problem statements (data-fusion / OSINT / MDA) | https://ised-isde.canada.ca/site/innovative-solutions-canada/en/challenges | `[ ]` | monthly |
| 4 | **NATO DIANA** announcements | Annual challenge call (2027 themes already out — see Part B) | https://www.diana.nato.int/ | `[ ]` | quarterly |
| 5 | **NLnet / NGI** news + Restack calendar | Rolling open-call deadlines (every 2 mo → 2030) | https://nlnet.nl/news/ (RSS) · https://nlnet.nl/propose/ | `[ ]` | bimonthly (deadline-driven) |
| 6 | **Canadian Safety and Security Program (CSSP)** | DRDC public-safety S&T CFPs (gov/industry/academia eligible) — posts on CanadaBuys (row 1 covers it, but watch the page too) | https://science.gc.ca/site/science/en/canadian-safety-and-security-program/cssp-funding | `[ ]` | quarterly |
| 7 | **Public Safety Canada** programs | Cyber Security Cooperation Program · Search & Rescue New Initiatives Fund · emergency-mgmt G&Cs | https://www.publicsafety.gc.ca/ → Funding | `[ ]` | quarterly |
| 8 | **Ocean Startup Project** newsletter | Startup / Idea Challenge (blue-tech) | https://www.oceanstartupproject.ca/ | `[ ]` | passive |
| 9 | **Canada's Ocean Supercluster** | Project calls / consortium openings | https://oceansupercluster.ca/ | `[ ]` | passive |
| 10 | **Horizon Europe** (Canada now directly fundable) | Civil Security for Society (CL3) — border / SAR / situational-awareness calls | https://ec.europa.eu/info/funding-tenders/opportunities/portal/ · https://ised-isde.canada.ca/site/ised/en/horizon-europe | `[ ]` | per work-programme cycle |
| 11 | **Sovereign Tech Agency** | Fund / Fellowship / Standards rounds (2026 rounds closed Apr/May) | https://www.sovereign.tech/ | `[ ]` | watch for re-open |
| 12 | **PacifiCan** (BC regional, incl. RDII) | Regional AI/defence/innovation funding | https://www.canada.ca/en/pacific-economic-development/services/funding.html | `[ ]` | quarterly |

> **Setup note:** CSSP, IDEaS, and the CH13/CH14 bids all run through the same DRDC/PSPC plumbing
> (`W7714-…` prefix, posted on CanadaBuys). One well-tuned CanadaBuys keyword alert (row 1) is the
> single highest-leverage action — it back-stops rows 2, 3, 6 even if a mailing list lapses.

---

## Part B — Gotham-adjacency scan

**What Gotham is, functionally:** ingest many heterogeneous sources → resolve them to common
entities → keep full lineage/provenance → let an analyst reason over the live picture and act.
planetar is the **same shape** (envelope + bus + fusion + entity graph + shell), built open and
maritime-first. So every Gotham domain is a *potential* planetar domain — gated by the fit screen
and by how much new domain work an "enhanced version" needs.

**Maturity legend:** 🟢 today's stack maps directly (swap detectors/ontology) · 🟡 needs a new
data-domain + ontology but core engine reused · 🔴 needs substantial new capability (don't
over-claim).

### B.1 — Domain → planetar-asset map

| Gotham use case | planetar asset that carries it | Lift | Honest TRL note |
|---|---|---|---|
| **Defence ISR / multi-domain awareness** | fusion + re-ID + shell (the flagship demo) | 🟢 | this *is* the CH13/CH14 thesis |
| **Maritime domain awareness / dark-vessel** | AIS+SAR+EO+hydrophone+RF fusion | 🟢 | built today (auditable) |
| **Border surveillance / situational awareness** | same multi-sensor fusion, land/maritime border ontology | 🟡 | swap detectors + entities |
| **Emergency mgmt / disaster response (COP)** | bus + shell as a real-time common operating picture; ingest flood/fire/weather feeds | 🟡 | new feeds, core reused |
| **Search & rescue (civilian, on-mission)** | fusion + kinematic track re-ID | 🟢 | strong civilian framing already in one-pager |
| **Critical-infrastructure monitoring** | bus + provenance + detectors over sensor/SCADA telemetry | 🟡 | new sensor adapters |
| **Financial crime / AML (graph analytics)** | entity resolution + provenance lineage (the doibio / Patent 10,936,582 spine) | 🟡 | non-spatial entities, no sensor layer; engine fits well |
| **Anti-human-trafficking intelligence** | entity resolution across fragmented records + re-ID | 🟡 | data-access & ethics heavy; partner-led |
| **Public health / epidemiology / contact graphs** | entity graph + provenance + temporal correlation ids | 🔴 | new domain; only with a research partner |
| **Supply-chain / sanctions-evasion tracing** | vessel/entity re-ID + provenance (maritime overlaps dark-vessel) | 🟡 | natural extension of dark-vessel work |
| **Law-enforcement / fusion-centre analytics** | shell + entity graph | 🔴 | civil-liberties / GBA+ heavy; tread carefully, civilian-first posture |

> **The two transferable crown jewels** are (1) the **nanosecond provenance bus** (any domain that
> needs real-time, auditable data movement) and (2) **entity resolution / re-ID** (any domain with
> "is this the same actor across fragmented sources?"). Those are exactly Gotham's two pillars, and
> they're the parts of planetar with the deepest provenance (benchmark + Patent 10,936,582). Lead
> with them when pitching outside maritime.

### B.2 — Live / recurring programs that fit the adjacency (found 2026-06-22)

| Program | Domain | Fit | $ | Timing / deadline | Notes |
|---|---|---|---|---|---|
| **NATO DIANA 2027 — "Multidomain Sensing & Advanced Data Processing for Intelligence & Surveillance"** | Defence ISR / fusion | ★★★ 🟢 | €100K + accelerator | **Closes 2026-07-02 12:00 BST** | Near-exact match. **Gate corrected 2026-06-22: DIANA needs TRL 4+ (not TRL 1–3); planetar verified at TRL 4 → passable.** Drafts built: [`../planetar-diana/`](../planetar-diana/). Blocker is bandwidth, not fit. ([source](https://www.diana.nato.int/challenges.html)) |
| **NATO DIANA 2026 — "Decision Superiority for NATO Warfighters" / "Data Assisted Decision Making" (Ch.10)** | Decision support | ★★ 🟢 | €100K + accel. | 2026 cohort (verify open status) | "Integrate analytics, sensor fusion, space intel into existing digital command platforms." May favour higher maturity. ([CFP](https://www.diana.nato.int/resources/site1/general/challenges/docs/2026-challenge-programme-cfp.pdf)) |
| **CSSP (Canadian Safety & Security Program, DRDC)** | Public safety / CIP / emergency mgmt | ★★★ 🟡 | project-scale | CFPs rolling on CanadaBuys (last: `W7714-248656`) | **Same plumbing as IDEaS.** Gov/industry/academia eligible; public-safety S&T. Watch via rows 1+6. Strong civilian-forward fit. ([CSSP](https://science.gc.ca/site/science/en/canadian-safety-and-security-program/cssp-funding)) |
| **Horizon Europe CL3 `HORIZON-CL3-2026-01-BM-01`** | Border surveillance & situational awareness | ★★ 🟡 | ~€6M/award (consortium) | 2026-2027 work programme | Canada now **directly fundable** on most CL3 calls incl. sensitive AI. Needs EU consortium — high effort; better as partner than prime. ([call](https://eufundingportal.eu/call-for-proposals-to-support-research-and-innovation-projects-for-advanced-border-surveillance-and-situational-awareness/) · [CA eligibility](https://ised-isde.canada.ca/site/ised/en/canadian-excellence-horizon-europe-sensitive-calls)) |
| **Horizon Europe CL3 `…-01-DRS-03`** | Disaster-resilient SAR | ★★ 🟡 | consortium | 2026-2027 | "Limited situational awareness, degraded comms, poor cross-agency interoperability" — the bus's interop story. Partner play. ([WP](https://ec.europa.eu/info/funding-tenders/opportunities/docs/2021-2027/horizon/wp-call/2026-2027/wp-6-civil-security-for-society_horizon-2026-2027_en.pdf)) |
| **Public Safety — Search & Rescue New Initiatives Fund** | Civilian SAR | ★★ 🟡 | project G&C | rolling | $61M since 2015; civilian SAR framing already in one-pager. ([PS funding](https://www.publicsafety.gc.ca/cnt/mrgnc-mngmnt/index-en.aspx)) |
| **FINTRAC / new Financial Crimes Agency** | AML / financial-crime graph analytics | ★ 🟡 | (future procurement, not a grant) | Agency legislation tabled 2026-04-27; FATF eval 2026-06 | FINTRAC is investing in **graph analytics + ML** for entity/network analysis — a direct entity-resolution use case. Track as a future *customer/partner*, not a CFP. ([FCA](https://www.canada.ca/en/department-finance/news/2026/05/minister-champagne-highlights-spring-economic-update-measures-to-fight-financial-crimes.html)) |
| **US OVC / Tech Against Trafficking (BSR)** | Anti-trafficking | ★ 🔴 | $5K–$1.85M (US, nonprofit-skewed) | grants.gov rolling | Recognized Gotham use case but US-centric & nonprofit/partner-shaped; low fit for a solo Canadian for-profit. Note only. ([OVC](https://ovc.ojp.gov/program/human-trafficking/grants-funding) · [TAT](https://techagainsttrafficking.org/)) |

### B.3 — Reading of the scan

1. **Closest-fit *new* opportunity is NATO DIANA 2027 ISR/fusion.** The TRL gate (4+) was a scare
   that resolved in our favour — planetar's substrate is verified **at TRL 4**, so DIANA clears
   *both* fit screens (the first non-IDEaS opportunity to do so). Drafts are built in
   [`../planetar-diana/`](../planetar-diana/). **Decision: GO (2026-06-22) — submitting** before
   **2026-07-02** (accepted cost: bandwidth overlap with CH14 two weeks later). C1 resolved
   (applicant = Zax Analytics, BC; Steven Ness Director & CEO).
2. **CSSP is the sleeper.** Same DRDC/PSPC machinery as the IDEaS bids you already know how to win,
   but aimed at *civilian* public-safety S&T — which is exactly planetar's civilian-forward identity
   (D3). It passes both fit screens (TRL 1–3 ok, software-essential). Add it as a first-class
   standing watch alongside IDEaS/ISC, not a footnote.
3. **Horizon Europe is now real for Canada** but every relevant call is consortium-scale — pursue
   only *with* an EU partner; backbone/partner role, never prime (the no-bid lesson, applied
   internationally).
4. **The non-maritime expansion path that doesn't need new sensors is financial-crime / AML
   entity resolution** — it reuses the doibio + Patent 10,936,582 spine directly. Not a grant today,
   but the highest-credibility "Gotham pivot" if a defence/maritime anchor customer ever wants it.
5. **Stay disciplined:** law-enforcement and public-health graph use cases are real Gotham markets
   but carry civil-liberties / GBA+ weight that cuts against the civilian-first, open posture. Keep
   them 🔴 / partner-gated; don't let "Gotham can do it" pull the roadmap off the honest TRL lane.

---

## Next actions

1. **Do rows 1 + 2 today** (CanadaBuys keyword alert + IDEaS list) — 30 min, covers most of the repo.
2. **Add CSSP to the standing-watch trio** in [`06`](06-shortlist-and-calendar.md) → make it a quad:
   IDEaS/MINERVA · ISC · NATO DIANA · **CSSP**.
3. **NATO DIANA 2027 — GO, submit before 2026-07-02.** Drafts + applicant facts done in
   [`../planetar-diana/`](../planetar-diana/); remaining = download DIANA's official templates,
   transfer content, fill `[TODO]` founder facts, submit.
4. Re-sweep this file each quarter; flip `[ ]`→`[x]` as channels are enrolled, and date the sweep.
