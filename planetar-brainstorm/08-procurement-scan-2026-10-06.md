# 08 — Procurement scan: data-platform and data-fusion buys (2026-10-06)

**Question asked:** which real public-sector procurements could planetar be mapped against, and
bid, in the category Palantir sells into (data integration, operational data platform, data
fusion, common operating picture)?

**Snapshot date: 2026-10-06.** Every fact was read on the primary notice or its attached
document unless tagged **[U]** (unverified: from a search snippet or secondary source). Dates and
terms move; re-verify on the notice before acting.

**Scope rule.** Procurements whose purpose is identifying, monitoring or tracking individual
people were excluded (list at the end). Everything kept concerns vessels, sensors, logistics or
generic data platforms.

## Headline findings

1. **No platform-class prime contract is enterable today by a one-person Canadian company.**
   The platform buys found (EMSA, NATO NCIA, UK NDTP) gate on establishment in a named
   jurisdiction, turnover, framework membership, security clearance or an incumbent technology.
   The large Palantir-style awards are not competed at all; the UK Ministry of Defence's £240.6M
   renewal (signed 2025-12-30) was a direct award under a defence and security exemption **[U]**.
2. **The enterable routes are innovation calls**, which is where this portfolio already works.
   Four of the eight candidates are innovation calls; two were already in this repo.
3. **Best mapping target: #1, the US Navy NIWC Pacific CSO.** Workspace:
   [`../planetar-niwc-mda/`](../planetar-niwc-mda/).
4. **Time-sensitive and unscreened: #3, IDEaS Challenge 17**, the same solicitation family as
   CH13 and CH14, closing **2026-10-20 14:00 EDT**.
5. **Best platform benchmark: #2, EMSA Blue Data Warehouse** — closed and not biddable, but its
   capability checklist is public. Mapped in
   [`09-platform-benchmark-emsa-bdw.md`](09-platform-benchmark-emsa-bdw.md).

## Ranked candidates

| # | Buyer, title | Reference | Published → closes | Value | Route |
|---|---|---|---|---|---|
| 1 | US Navy NIWC Pacific, "Data and Analytics for Maritime Domain Awareness" | `N66001-26-S-C036` | 2026-01-08 → 2027-01-07, **OPEN** | No ceiling; awards "not expected to exceed $100M" | Commercial Solutions Opening |
| 2 | EMSA, "Blue Data Warehouse" | `EMSA/2025/OP/0038`; TED 851191-2025 | 2025-12-22 → 2026-02-18, CLOSED | EUR 2,500,000 | Open competition |
| 3 | DND IDEaS, "RF Data Fusion for Command and Control" | `W7714-248676/017`; cb-846-73690703 | 2026-09-10 → 2026-10-20, **OPEN** | CAD 250K / 1.5M / 5M by TRL band | Innovation challenge |
| 4 | NATO DIANA, "Multidomain Sensing and Advanced Data Processing for Intelligence and Surveillance" | not found | 2026-06-01 → 2026-07-03, CLOSED | EUR 100,000 each | Innovation challenge |
| 5 | UK Department for Business and Trade, "National Digital Twins Programme – Data Pipelines, Analytics and Visualisation" (prior information notice) | tender_540420/1600490 | 2026-08-07; pipeline only | up to £10.5M | Call-off, Spark DPS RM6094 |
| 6 | NATO NCIA, "eAirC2 Data Platform, Governance, and Usage" | `IFB-CO-42602163-eAirC2` | 2026-02-12 → 2026-05-08 (anticipated), CLOSED | EUR 3,000,000 each, up to three suppliers | NATO competitive dialogue |
| 7 | Canadian Coast Guard, "RFI Vessel Traffic Management System" | `WS5757126243` | 2026-07-16 → 2026-10-02, CLOSED | not found | Request for information |
| 8 | DND via Innovative Solutions Canada, "MINERVA – Uncrewed Aircraft System Deconfliction" | `EN578-24ISC4/94`; cb-961-40172327 | 2026-09-23 → 2026-10-21, **OPEN** | CAD 500,000 per contract | Innovation challenge |

## Per-candidate notes

**1. NIWC Pacific CSO** — https://sam.gov/opp/8469e11a72a5431abc33990cb3a63e56/view.
Vessel detection and tracking including dark targets; minimum technical data includes source
identification and a methodology description. Buys feeds into SeaVision, explicitly not a new
common operational picture. Foreign-owned companies welcome; SAM.gov registration before award.
Step 1 is a five-page brief. Full nine-page solicitation read. → [`../planetar-niwc-mda/`](../planetar-niwc-mda/)

**2. EMSA Blue Data Warehouse** — https://ted.europa.eu/en/notice/-/detail/851191-2025.
Twenty titled capability requirements plus a governance guideline (catalogue, lineage,
permissions). Not biddable: EU and listed neighbour states only (Canada absent); EUR 1,000,000
yearly turnover; three Databricks references; 13 CVs; "the technology adopted to implement the
BDW is Databricks". Specifications and two appendices read on the EU Funding & Tenders portal.
→ [`09-platform-benchmark-emsa-bdw.md`](09-platform-benchmark-emsa-bdw.md)

**3. IDEaS Challenge 17, RF Data Fusion for Command and Control** —
https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-846-73690703.
"convert, analyze, and fuse real-time, domain-specific, content-rich data transmitted over radio
frequency (RF) bearers into a secure, standardized pan-domain Command and Control (C2) format".
Same CFP 006 vehicle as CH13 and CH14: Component 1a is TRL 1–3, up to CAD 250,000, six months;
open to individuals; Canadian content (threshold amended to 70%). Challenge statement and call
document read. **Not screened against the fit filter.** First read only:
- Screen #2 looks like a pass. All five Essential outcomes are software: a software capability;
  all domains and functional services; standards-compliant messaging (MTF-XML) and exchange
  protocols (NIEM, NATO Core Data Framework) with documented import/export interfaces;
  configurable and modular with Character-Oriented Information Exchange processing; documented
  integration interfaces including simulation and wargaming.
- The title says "fusion" but the Essentials are message conversion and standards conformance;
  fusion appears only as a Desired outcome. The nearest planetar asset is `planetar-registry`
  (one typed registry generating several encodings). The military messaging standards
  themselves are a domain planetar has not touched.
- Fourteen days remain, and the MINERVA decision closes the next day.

**4. NATO DIANA** — https://www.diana.nato.int/challenges.html. Already in this repo:
[`../planetar-diana/`](../planetar-diana/). Annual call; TRL 4+, companies only. Its examples
include signals and communications intelligence, so any mapping stays with object tracking.

**5. UK National Digital Twins Programme** —
https://www.contractsfinder.service.gov.uk/Notice/db2de9db-8790-4d2b-ada2-dc6d4c166fc5.
Notable because the supplier must "work within NDTP's open source delivery model". Spark DPS
members only; filters "Location UK" and "Security Above Official". An invitation to tender was
"anticipated" for September 2026; none was found. A watch, not a pursuit.

**6. NATO NCIA eAirC2** — notice mirrored at
https://oinsip.mo.gov.cz/sites/oinsip/files/2026-02/42602163-eAirC2.pdf. Needs a national
Declaration of Eligibility and NATO SECRET clearances. Bid package not public.

**7. Coast Guard vessel traffic management RFI** —
https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/ws5757126243-doc5785722339.
"an integrated image, showing both vessel traffic and waterways conditions". Documents need an
SAP Business Network login; not read. Closed 2026-10-02; watch for the follow-on solicitation.

**8. MINERVA UAS Deconfliction** — already in this repo: [`../planetar-minerva/`](../planetar-minerva/)
(decision pending, closes 2026-10-21).

## Excluded, and not accessed

- **Excluded by the scope rule:** UK Home Office "Land Based ISR and Common Operating Picture"
  (2025/S 000-035519), built to detect migrant small boats; NCIA "Information Environment
  Assessment Capability Data Platform" (`IFB-424210-IEAC`), where online-media monitoring could
  not be ruled out; Frontex notices.
- **Not eligible:** UKDI Security Open Call 2026 Cycle 2 (UK organisations only).
- **Could not access:** Find a Tender keyword search (single notices load, scripted search does
  not filter); TED notice web pages (the TED API was used instead); NCIA's own site (mirrored
  notices read); the EMSA spreadsheet appendices and its 118 published questions and answers.
- **Not covered:** US portals other than SAM.gov for candidate 1; Australian, New Zealand and
  Japanese procurement; Canadian provincial buys.

## What this means for the "compete with Palantir" goal

The contracts Palantir holds are reached through references, clearances and framework
memberships, not through an open tender a newcomer can answer. The realistic sequence is
innovation award → reference customer → framework membership → platform call-off. On that
path the differentiator the buyers themselves keep naming is openness: source identification
and method transparency (candidate 1), an "open source delivery model" (candidate 5), lineage
and catalogue governance (candidate 2).
