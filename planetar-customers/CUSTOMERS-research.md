# First paying customers for planetar: research (2026-10-22)

**Question:** who could realistically become planetar's first *paying* customer (not a grant)
within about six months, under decision D2a (GPLv3 software plus paid support, hosting,
integration and defence contracts)?

**Snapshot date: 2026-10-22.** Every fact below was read on the page cited, on 2026-10-22, unless
it is tagged **[U]** (unverified: search-engine summary or secondary source only). "Not found"
means one or two targeted searches turned up nothing. It does not mean the thing doesn't exist.
Nothing here was sent to anyone. No contact was made.

**Scope rule:** vessels only. Uses aimed at identifying, monitoring or tracking individual people
are excluded, for example migrant small-boat surveillance and crew/passenger analytics.

**What planetar can sell today** (from [`../planetar-niwc-mda/FIT.md`](../planetar-niwc-mda/FIT.md),
2026-10-06): live AIS ingest for two areas, Sentinel-1 CFAR ship detection, webcam YOLO "boat"
detection, a hydrophone pipeline, rule-based kinematic dark-vessel re-identification, per-result
provenance (`/trace/:id`), and REST/WebSocket/TCP delivery. **Gaps:** no measured detection
accuracy, no vessel typing, no bulk or S3 export, no API auth, one person, and no owned data. The
commercial redistribution rights for aisstream.io are **not found**: its home page says "free"
but links no terms page (read 2026-10-22).

---

## Headline findings

1. **The money in this market pays for data, and planetar owns none.** Each buy we found pays for
   collection or licensed data, not open software: DFO's dark-vessel service (MDA RADARSAT-2),
   Transport Canada's CAD 2.9M Kpler AIS contract, and NOAA's sole-source to Starboard ("exclusive
   licensing agreements"). Selling open software or services *beside* a data owner is realistic.
   Selling *instead of* one is not.
2. **Free tools rule out paid analytics for most fisheries and NGO buyers.** Skylight (AI2) is
   free to governments, regional fisheries bodies and qualifying NGOs. Global Fishing Watch data
   is non-commercial (CC BY-NC 4.0), and GFW has no public commercial licence. A one-person
   vendor cannot charge a fisheries agency or NGO for dark-vessel *detections*. It can charge for
   **integration, hosting or local sensors that those free tools don't cover**: webcams,
   hydrophones, community radar, and an on-prem or sovereign deployment.
3. **The best first customer is another vendor, not an agency.** Larus Technologies (Ottawa)
   holds a CAD 8.3M DND IDEaS contract (2025-08-27 → 2028-03-31) and a CAD 2.5M three-year Royal
   Canadian Navy MDA contract. A small subcontract (provenance layer, Sentinel-1 ingest, open bus
   integration) avoids the clearance, size and incumbent blockers that stop direct sales.
4. **The federal small-contract route exists but requires paperwork first.** Under Government
   Contracts Regulations s.6(b)(iv), any federal department can award a services contract of
   ≤ CAD 40,000 without bids. Most professional-services buys of that size go through
   **ProServices**, whose pre-qualification is "ongoing". Pre-qualifying is a precondition for
   nearly every Canadian lead below.
5. **Nothing is closeable in six months without a named buyer conversation first.** No open
   solicitation fits planetar today. The ISC Testing Stream (TS13) closed 2026-06-17 and targets
   TRL 7–9. The Coast Guard VTMS RFI closed 2026-10-02 (see [`08`](../planetar-brainstorm/08-procurement-scan-2026-10-06.md)).
   Each top candidate starts with an exploratory contact through a public channel.

## Ranked candidates

Score = realistic-in-6-months (1–3) × revenue (1–3) × fits-today (1–3). The scores are judgement
calls, and the notes give the reasons.

| # | Candidate | What they'd buy from planetar | Route | Size signal | Score |
|---|---|---|---|---|---|
| 1 | **Larus Technologies** (Ottawa MDA software firm) | Subcontract: open ingest/provenance layer, Sentinel-1 detection feed, bus integration | Private subcontract (no public procurement) | Holds CAD 8.3M IDEaS + CAD 2.5M RCN contracts | 2×2×2 = **8** |
| 2 | **Clear Seas** (Vancouver marine-shipping research non-profit) | AIS processing / vessel-traffic analysis consultancy | Open RFPs on its site (none active today) | Past RFPs: 2023 geospatial/AIS data contractor; 2024 Pacific traffic forecast | 1.5×2×3 = **9** if a call opens, else ~4 |
| 3 | **Transport Canada EMSA program** (Indigenous/coastal maritime awareness, Fujitsu-built) | Pilot: add Sentinel-1/webcam detections and provenance to a community's EMSA picture; integration services | Directed services contract ≤ CAD 40k (ProServices) | 860+ licences, 69 Indigenous communities (2025-02) [U] | 1.5×1.5×2 = **4.5** |
| 4 | **BC coastal First Nations stewardship / Guardian programs** | Locally-hosted, community-owned AIS + webcam (+ hydrophone) monitoring for a territory; data sovereignty by construction (GPLv3, self-hosted) | Direct services contract with a Nation or its stewardship body | Not found (no public budgets) | 2×1×2 = **4** |
| 5 | **World Bank-financed Pacific fisheries projects (PROP/PROPER)** | Individual MCS-technology consultancy | World Bank individual-consultant EOIs posted by national agencies | Values not found; recent EOIs closed 2026-05-08 | 1.5×2×1.5 = **4.5** |
| 6 | **US Navy NIWC Pacific MDA CSO** (cross-ref, already mapped) | Dark-target candidate feed with source identification | Commercial Solutions Opening, closes 2027-01-07 | Up to USD 100M programme | 1×3×2 = **6** (low realism; see FIT.md) |
| 7 | **Ocean Networks Canada / ECHO ecosystem** (Victoria) | Subcontract or paid collaboration on hydrophone vessel detection | Partner contract; see [`drafts/03`](../planetar-brainstorm/drafts/03-onc-outreach-email.md) | ONC has run ECHO infrastructure since 2015 [U] | 1.5×1×2 = **3** |
| 8 | **Pacific Islands Forum Fisheries Agency (FFA)** | Integration or analytics services around its surveillance picture | FFA RFPs via `procurement@ffa.int` | Buys satellite AIS from exactEarth/Geospatial Intelligence [U] | 1×2×1.5 = **3** |
| 9 | **Federal MDA operators directly** (MSOC West, DFO C&P Pacific, RCN Pacific) | Small integration or analytics pilot on BC waters | Directed contract ≤ CAD 40k, or an IDEaS/ISC vehicle | Not found | 1×1.5×2 = **3** |
| 10 | **Kongsberg Geospatial** (Ottawa) | Subcontract feeding AIS/SAR tracks into its geospatial/C2 products | Private subcontract | CSA smartEarth funding for AIS+ADS-B fusion (2022) [U] | 1×2×1.5 = **3** |

**On the order:** the score puts Clear Seas (9 if a call opens) and NIWC (6) above Larus (8 or
less). The table ranks by realism first. Clear Seas has no open call today, and NIWC needs gaps
closed before any brief. Larus is the only top-three lead that can start with a conversation this
month.

## Per-candidate notes

### 1. Larus Technologies: subcontract under a funded MDA prime
- **What they buy today:** they *sell* MDA. Their IDEaS award notice: CAD 8,305,500, DND via
  PSPC, competitive, IDEaS CFP 003 Component 1a lineage, 2025-08-27 → 2028-03-31
  ([CanadaBuys CW2409671](https://canadabuys.canada.ca/en/tender-opportunities/award-notice/cw2409671)).
  Invest Ottawa (2025-10-17) reports a "three-year, $2.5 million contract with the Royal Canadian
  Navy" for AI/ML maritime domain awareness, product TotalForesight
  ([Invest Ottawa](https://www.investottawa.ca/blog/spotlighting-larus-technologies-ottawa-roots-and-the-opportunity-ahead-for-canadas-defence-innovation-sector/)).
  A 2016 exactEarth–Larus alliance on Total::Insight [U]
  ([GeoConnexion](https://geoconnexion.com/publication-articles/exactearth-and-larus-technologies-announce-strategic-alliance)).
- **Fit:** an open Sentinel-1 detection feed, per-result provenance (`/trace/:id`), and the
  zmesg/bus ingest path. These pieces sit underneath a decision-support product, so they don't
  compete with it.
- **Blockers:** no relationship. Larus may treat ingest as core IP. Defence work may need security
  screening (unverified). **Cross-bid hygiene:** don't offer deliverables that the CH13/CH14 bids
  fund (see FIT.md risk 6).
- **First step:** use Larus's public website contact form or a defence-industry event to propose
  a 30-minute technical call about an open, auditable ingest/provenance layer. Show
  https://planetar.ca.

### 2. Clear Seas: AIS-analysis consultancy
- **What they buy:** research consultants via public RFPs. Their 2023 "Geospatial Database &
  Programming Contractor" RFS covered AIS processing, including "AIS-based track lines python
  modeling" [U]. Their 2024-02-05 RFP was a vessel-traffic forecast for the Pacific, and it said
  other regions were "expected to be the subject of future studies" [U]. The site says there is
  no active call ([research opportunities](https://clearseas.org/research-opportunities) [U]).
- **Fit:** the strongest skill fit in this list. It is AIS processing and analysis, with a BC
  focus, and needs no detection-accuracy claim.
- **Blockers:** no open call today. Clear Seas wants consultancy deliverables (reports), not a
  platform.
- **First step:** watch the research-opportunities page, and ask to be added to its consultant
  or RFP notification list through its public contact page.

### 3. Transport Canada EMSA: integration add-on
- **What they buy today:** TC picked Fujitsu Consulting (Canada) "to develop, host and maintain"
  EMSA for up to CAD 2.5M (2019-03-08,
  [TC release](https://www.canada.ca/en/transport-canada/news/2019/03/government-of-canada-and-10-indigenous-coastal-communities-select-developer-for-maritime-awareness-information-syste.html)).
  Its data sources are terrestrial and satellite AIS, local knowledge, historical positions,
  weather, tides and sensitive areas. **No radar or camera sensors are listed.** The page was last
  modified 2026-09-23 and says EMSA "will continue to grow the number of Indigenous community
  partnerships" ([TC EMSA page](https://tc.canada.ca/en/campaigns/protecting-our-coasts-oceans-protection-plan/stronger-partnerships-indigenous-coastal-communities/expanding-enhanced-maritime-situational-awareness-program)).
  Over 860 licences and 69 Indigenous communities as of 2025-02 [U]
  ([TC news 2025-02](https://www.canada.ca/en/transport-canada/news/2025/02/significant-investments-in-marine-safety-and-to-support-indigenous-communities-through-the-oceans-protection-plan.html)).
- **Fit:** EMSA lacks non-AIS detections. Sentinel-1 and webcam detections of non-AIS vessels,
  with provenance, are a clean add-on for one pilot community.
- **Blockers:** Fujitsu is the incumbent integrator, so any feed may have to go through them. A
  ProServices SA is likely needed even for a ≤ CAD 40k directed contract. Unmeasured detection
  accuracy.
- **First step:** use the public program mailbox listed on the EMSA page
  (`TC.MaritimeAwareness-ConnaissanceMaritime.TC@tc.gc.ca`) to ask whether EMSA accepts
  third-party detection feeds and how a pilot would be contracted.

### 4. BC coastal First Nations stewardship programs
- **What they buy today:** not found. The Coastal Stewardship Network (formerly the Coastal
  Guardian Watchmen Network) runs a "Regional Monitoring System" for field data [U]. The Haida
  Gwaii Marine Awareness Project (Council of the Haida Nation with LGL) monitored 18 nearshore
  areas in 2021 using wildlife cameras plus EMSA [U]
  ([Clear Seas](https://clearseas.org/?p=22206)). Transport Canada ran a 2018 Haida/Gitga'at
  vessel-traffic pilot under a CAD 62.5M five-year initiative [U]
  ([CKPG](https://ckpgtoday.ca/?p=172433)).
- **Fit:** good. Camera-plus-AIS fusion is exactly what planetar-eo plus planetar-ais do. GPLv3
  and self-hosting fit Indigenous data-sovereignty expectations.
- **Blockers:** relationships and trust must come first, budgets are small and grant-funded, and
  EMSA is already free to them. **Scope check:** monitor vessels only, never people on shore or
  aboard.
- **First step:** use the Coastal First Nations / Coastal Stewardship Network public contact
  (coastalfirstnations.ca) to offer a no-cost demo. A paid pilot only follows if the Nation asks.

### 5. Pacific fisheries projects financed by the World Bank (PROP/PROPER)
- **Evidence:** MIMRA (Marshall Islands) issued a PROPER EOI for an individual Coastal Fisheries
  MCS&E consultant, IDA-E1650, due 2026-05-08 [U]
  ([MIMRA TOR](https://www.rmimimra.com/images/2026/04/MCS%20%20E%20REOI%20%20TOR.pdf)). Tuvalu
  Fisheries advertised a consultant to pick MCS technology "over the next 4-5 years" (2025) [U]
  ([Tuvalu Fisheries](https://tuvalufisheries.tv/tag/consultant/)). FFA-related World Bank
  consultancies (database design) closed in May 2026 [U].
- **Fit:** domain consulting more than software. Steven has no fisheries MCS track record, so
  those roles will likely require one.
- **First step:** watch the PROPER pages of MIMRA, Tuvalu Fisheries and FSM DoFA for
  technology/data roles.

### 6. NIWC Pacific CSO (cross-reference)
Already mapped in [`../planetar-niwc-mda/FIT.md`](../planetar-niwc-mda/FIT.md). Biggest prize,
low six-month realism: no measured detection performance, no S3/bulk export, and SAM.gov
registration is needed.

### 7. Ocean Networks Canada / ECHO
ONC has provided ECHO infrastructure and data management since 2015, and JASCO operates the
Boundary Pass listening station [U]
([Green Marine](https://green-marine.org/stayinformed/news/jasco-deploys-an-underwater-listening-station-in-the-salish-sea-to-protect-endangered-whales/)).
Incumbent acoustic contractors (JASCO) are well established. The realistic outcome is a
collaboration (Mitacs) that later becomes paid work. Use the existing draft
[`drafts/03-onc-outreach-email.md`](../planetar-brainstorm/drafts/03-onc-outreach-email.md).

### 8. FFA
FFA buys satellite AIS on multi-year contracts from exactEarth with Geospatial Intelligence [U]
([Space Connect](https://www.spaceconnectonline.com.au/industry/4397-leveraging-space-to-protect-the-pacific-s-fishing-resources)).
It is a Canadian DVD partner, and Skylight is free to it. Its RFPs ask for bids by e-mail to
`procurement@ffa.int` (e.g. CP01_2627, due 2026-08-28,
[FFA RFP](https://www.ffa.int/wp-content/uploads/_pda/2026/08/Request-for-Proposal-CP-Electronic-Reporting-Technicians-AFT1.pdf)).
Watch only.

### 9. Direct federal MDA operators
The three MSOCs fuse partner data: RCMP, TC, CCG, DFO, CBSA and DND
([TC MSOC page](https://tc.canada.ca/en/marine-transportation/marine-security/operations/marine-security-operation-centres) [U]).
West is in the Victoria/Esquimalt area, which matches planetar's demo area. There is no open
buy. The only routes are a directed ≤ CAD 40k contract to an interested program officer, or
IDEaS/ISC. Not realistic without a sponsor inside the department.

### 10. Kongsberg Geospatial
Ottawa geospatial/C2 software firm. It received CSA smartEarth funding for RAVENS, which merges
ADS-B and AIS tracks [U]
([Kongsberg Geospatial](https://www.kongsberggeospatial.com/news/kongsberg-geospatial-receives-funding-from-the-canadian-space-agency-smartearth-initiativee)).
Possible integration partner for a SAR/EO detection feed. No signal that they buy from small
vendors.

## Procurement facts (Canada)

- **No-bid thresholds:** "the estimated expenditure does not exceed … in the case of a goods
  contract, $25,000 … in the case of any other contract … $40,000". Other grounds are emergency,
  public interest, and "only one person is capable"
  ([GCR SOR/87-402 s.6](https://laws-lois.justice.gc.ca/eng/regulations/SOR-87-402/section-6.html)).
- **ProServices:** mandatory for professional services below the CKFTA threshold. "Directed
  contracting can also be done for requirements valued below $40K". Pre-qualification "is
  ongoing" through the CPSS supplier module
  ([PSPC ProServices](https://www.canada.ca/en/public-services-procurement/services/acquisitions/proservices/about/how-supply-arrangement-works.html)).
- **ISC Testing Stream:** caps are CAD 1.15M (standard) and CAD 2.3M (military). TS12 targeted
  "late stage development (TRL 7 to 9)" and closed 2025-07-23
  ([TS12](https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-451-4570525)).
  TS13 closed 2026-06-17 [U]. Departments enter as "testers" via `solutions@ised-isde.gc.ca`
  ([ISED roadmap](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/node/107)).
  **Not a six-month route** at planetar's TRL.
- **ACAN:** Transport Canada bought Kpler data (CAD 2,908,842.97, 2026-03-15 → 2027-03-14) by
  Advance Contract Award Notice
  ([CW2433828](https://canadabuys.canada.ca/en/tender-opportunities/award-notice/cw2433828)).
  ACANs can be challenged, but only by a supplier who can meet the requirement, and that one
  needs a data product.

## Incumbents and free tools that cap pricing

| Offer | Who pays / price | Effect on planetar |
|---|---|---|
| **MDA Space Maritime Insights** (DFO Dark Vessel Detection) | DFO; extended 2025-06-30, value not disclosed ([MDA](https://mda.space/article/government-of-canada-extends-mda-space-contract-providing-continuous-space-based-maritime-awareness-and-security)). Started with CAD 7M DFO/DND funding ([QP note DFO-2022-00023](https://search.open.canada.ca/qpnotes/record/dfo-mpo%2CDFO-2022-00023)). DFO said the IP is "owned by MDA" [U]. Expanded to Mexico 2026-07-17 [U] ([Canada in Mexico](https://canadainmexico.com/2026/07/minister-anand-meets-with-mexicos-secretary-of-foreign-affairs-roberto-velasco-announces-projects-advancing-canada-mexico-action-plan/)) | DVD itself is closed to planetar. Its partner countries already receive MDA output |
| **Skylight (AI2)** | Free. Shippy "will be provided at no cost to governments, regional fisheries bodies, and qualifying NGOs" ([Skylight](https://skylight.global/news/shippy-launch)). Uses Sentinel-1/-2, night lights, Maxar, Spire [U] | **Makes paid dark-vessel detection for fisheries agencies and NGOs unrealistic** |
| **Global Fishing Watch** | API licence CC BY-NC 4.0. For commercial use "existing license terms are not sufficient" and no public commercial terms exist ([GFW FAQ](https://globalfishingwatch.org/faqs/can-i-use-global-fishing-watch-apis-for-commercial-purposes/)) | Partner, not supplier. A paid product cannot be built on GFW data |
| **Starboard (NZ)** | NOAA NMFS sole-source intent FD-2026-446, est. USD 1–250,000, 3 users, 1+1 yr, posted 2026-07-08 ([HigherGov](https://www.highergov.com/contract-opportunity/intent-to-award-to-a-single-source-forstarboard-ma-fd-2026-446-s-d632e/)) | Shows what a small agency subscription costs, and that "exclusive licensing" decides it |
| **Kpler** (absorbed Spire Maritime, ~USD 241M, announced 2024-11-13 [U]) | Transport Canada CAD 2.9M/yr (above). Spire's 2024 GoC AIS contract was CAD 1.41M, up to ~4.23M with options [U] | Canada's AIS spend goes to data owners |
| **Windward** | ACV USD 34.5M (FY23). European coastguard €3.2M over 5 years [U] ([Windward IR](https://investors.windward.ai/investors)) | Sanctions/insurance/coastguard analytics: no room for a pre-revenue entrant |

## Not realistic (next 6 months), and why

- **DFO Dark Vessel Detection, directly.** MDA is the incumbent, the IP is MDA's, and the service
  is RADARSAT-based.
- **Sanctions-compliance, commodity-trading and marine-insurance firms.** They buy global
  historical AIS plus ownership data (Windward, Kpler, Lloyd's List, Pole Star). planetar covers
  two areas, owns no data, and its AIS feed rights are unverified. The Hormuz demo area is a
  showcase, not a product.
- **Oceana, WWF and similar NGOs.** They have GFW and Skylight for free. No NGO subscription to a
  paid dark-vessel vendor was found.
- **MDA Space as a buyer.** It builds in-house and owns RADARSAT/CHORUS. No subcontracting signal
  was found.
- **Port of Vancouver (VFPA).** Vessel-traffic scheduling was competitively awarded to DHI (NCOS
  Online), and the final phase was mandatory from 2025-11-24 [U]
  ([DHI](https://dhigroup.com/news/port-authority-partners-with-leading-digital-advisory-company-dhi-seaport-opx)).
  ECHO acoustics are covered by JASCO and ONC.
- **OceanMind.** It is a non-profit *provider* that is itself fundraising ("ZEROinFIVE", 2025)
  [U]. It could be a peer or partner, not a buyer.
- **ISC Testing Stream.** It targets TRL 7–9 and has no open call.
- **EMSA (EU), NATO, UK NDTP, Coast Guard VTMS.** Already screened as ineligible or closed in
  [`08-procurement-scan`](../planetar-brainstorm/08-procurement-scan-2026-10-06.md).
- **Excluded by the scope rule.** Any people-tracking use, e.g. TURQUESA II anti-smuggling (part
  of the same 2026-07-17 Mexico package) [U].

## Before selling anything (applies to every lead)

1. Verify the aisstream.io, webcam and hydrophone terms for commercial redistribution of derived
   products. Sentinel-1 is the only feed whose licence is confidently open.
2. Start ProServices pre-qualification. It is ongoing, quarterly evaluation, and gates
   ≤ CAD 40k federal work.
3. Get a measured detection number (planetar-fusion Stage 1, or a labelled Victoria AIS/SAR
   match-up). Every lead above asks "how good is it?".
4. Add API keys plus bulk export. Hosting customers will expect both.

## Sources (all read 2026-10-22 unless tagged [U])

- MDA Space, DFO contract extension, 2025-06-30 — https://mda.space/article/government-of-canada-extends-mda-space-contract-providing-continuous-space-based-maritime-awareness-and-security
- DFO QP note DFO-2022-00023 — https://search.open.canada.ca/qpnotes/record/dfo-mpo%2CDFO-2022-00023
- Global Affairs Canada Mexico package, 2026-07-17 [U] — https://canadainmexico.com/2026/07/minister-anand-meets-with-mexicos-secretary-of-foreign-affairs-roberto-velasco-announces-projects-advancing-canada-mexico-action-plan/
- Larus IDEaS award CW2409671 — https://canadabuys.canada.ca/en/tender-opportunities/award-notice/cw2409671
- Invest Ottawa on Larus, 2025-10-17 — https://www.investottawa.ca/blog/spotlighting-larus-technologies-ottawa-roots-and-the-opportunity-ahead-for-canadas-defence-innovation-sector/
- exactEarth–Larus alliance [U] — https://geoconnexion.com/publication-articles/exactearth-and-larus-technologies-announce-strategic-alliance
- Transport Canada Kpler award CW2433828 — https://canadabuys.canada.ca/en/tender-opportunities/award-notice/cw2433828
- Spire CAD 1.41M GoC contract, 2024-07-08 [U] — https://www.businesswire.com/news/home/20240708182692/en/
- TC EMSA developer selection, 2019-03-08 — https://www.canada.ca/en/transport-canada/news/2019/03/government-of-canada-and-10-indigenous-coastal-communities-select-developer-for-maritime-awareness-information-syste.html
- TC EMSA program page (mod. 2026-09-23) — https://tc.canada.ca/en/campaigns/protecting-our-coasts-oceans-protection-plan/stronger-partnerships-indigenous-coastal-communities/expanding-enhanced-maritime-situational-awareness-program
- TC OPP news, 2025-02 [U] — https://www.canada.ca/en/transport-canada/news/2025/02/significant-investments-in-marine-safety-and-to-support-indigenous-communities-through-the-oceans-protection-plan.html
- Government Contracts Regulations s.6 — https://laws-lois.justice.gc.ca/eng/regulations/SOR-87-402/section-6.html
- PSPC ProServices — https://www.canada.ca/en/public-services-procurement/services/acquisitions/proservices/about/how-supply-arrangement-works.html
- ISC TS12 — https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-451-4570525 · ISED Testing Stream roadmap — https://ised-isde.canada.ca/site/innovative-solutions-canada/en/node/107
- NOAA NMFS Starboard sole-source FD-2026-446 — https://www.highergov.com/contract-opportunity/intent-to-award-to-a-single-source-forstarboard-ma-fd-2026-446-s-d632e/
- Skylight Shippy launch — https://skylight.global/news/shippy-launch · Skylight sources [U] — https://skylight.global/news/sentinel-2-now-available-in-skylight
- Global Fishing Watch commercial-use FAQ — https://globalfishingwatch.org/faqs/can-i-use-global-fishing-watch-apis-for-commercial-purposes/
- Windward investor relations [U] — https://investors.windward.ai/investors
- aisstream.io home page (no terms page linked) — https://aisstream.io/
- Clear Seas research opportunities [U] — https://clearseas.org/research-opportunities · Clear Seas shore-based tech / Haida Gwaii [U] — https://clearseas.org/?p=22206
- CKPG, TC First Nations vessel-traffic pilot (2018) [U] — https://ckpgtoday.ca/?p=172433
- Coastal First Nations CGW FAQ [U] — https://coastalfirstnations.ca/our-stewardship/cgw-resources/cgw-faq
- MIMRA PROPER MCS&E EOI [U] — https://www.rmimimra.com/images/2026/04/MCS%20%20E%20REOI%20%20TOR.pdf · Tuvalu Fisheries consultants [U] — https://tuvalufisheries.tv/tag/consultant/
- FFA RFP CP01_2627 — https://www.ffa.int/wp-content/uploads/_pda/2026/08/Request-for-Proposal-CP-Electronic-Reporting-Technicians-AFT1.pdf · FFA satellite AIS [U] — https://www.spaceconnectonline.com.au/industry/4397-leveraging-space-to-protect-the-pacific-s-fishing-resources
- Green Marine, JASCO/ECHO [U] — https://green-marine.org/stayinformed/news/jasco-deploys-an-underwater-listening-station-in-the-salish-sea-to-protect-endangered-whales/
- DHI / VFPA [U] — https://dhigroup.com/news/port-authority-partners-with-leading-digital-advisory-company-dhi-seaport-opx
- TC MSOC page [U] — https://tc.canada.ca/en/marine-transportation/marine-security/operations/marine-security-operation-centres
- Kongsberg Geospatial smartEarth [U] — https://www.kongsberggeospatial.com/news/kongsberg-geospatial-receives-funding-from-the-canadian-space-agency-smartearth-initiativee
- OceanMind [U] — https://www.oceanmind.global/home
