# First paying customers for planetar: Europe (2026-10-22)

**Question:** which European organisations (EU, EEA, UK, Norway, Switzerland, and NATO bodies
in Europe) could realistically become a *paying* customer of planetar within about six to nine
months? Planetar is GPLv3 software sold as paid services (support, hosting, integration, pilots
and defence subcontracts; decision D2a) by Zax Analytics, a one-person Canadian company.

**Snapshot date: 2026-10-22.** Every fact was read on the cited page or notice on 2026-10-22
unless tagged **[U]**, meaning a search snippet or secondary source only. "Not found" means one
or two targeted searches found nothing, not that the thing does not exist. TED facts come from
the TED v3 search API (`api.ted.europa.eu/v3/notices/search`), because TED web pages returned
bot challenges. UK Contracts Finder facts come from its REST API. Nothing was sent to anyone,
and no contact was made.

**Scope rule:** vessels only. Buys aimed at people are excluded, including Frontex surveillance
aircraft (TED 515869-2026), the Horizon Europe 2026 border-management topics, and ICMPD's
Tunisia/Maghreb maritime surveillance systems (TED 369431-2026, 305326-2026).

**Builds on, without repeating:** [`CUSTOMERS-research.md`](CUSTOMERS-research.md), the
Canada-heavy first pass whose headline findings (buyers pay for data, which planetar does not
own; free tools undercut paid detection) hold in Europe too. Also
[`08`](../planetar-brainstorm/08-procurement-scan-2026-10-06.md) (EMSA Blue Data Warehouse,
NATO NCIA eAirC2, UK NDTP, NATO DIANA) and [`09`](../planetar-brainstorm/09-platform-benchmark-emsa-bdw.md).
Capabilities and gaps are as listed in [`../planetar-niwc-mda/FIT.md`](../planetar-niwc-mda/FIT.md).

---

## Headline findings

1. **No European public buyer is closable within six to nine months by a pre-revenue Canadian
   sole trader.** EU agencies are closed to Canadian bidders. National buyers are open in law
   but require a working, referenced system. The realistic first euro or pound comes through a
   **private subcontract** (OceanMind, #1) or an **ESA contract funded by Canada's own
   subscription** (InCubed, #2).
2. **The buyer whose need matches planetar best already exists, and it shows what is missing.**
   Norway's Coastal Administration (Kystverket) is buying a NOK 15,000,000, one-year service for
   "detection of vessels that do not send AIS" from Sentinel-1/2 plus AIS (TED 587752-2026). That
   is planetar's stack. But tenderers had to prove the system was "operative" for "at least one
   customer" before the deadline. Planetar's first European sale depends on a first customer
   somewhere else.
3. **EU agencies (EMSA, EFCA, SatCen) are effectively closed.** ESMA states that agency
   procurement is not covered by the WTO GPA and that third-country tenderers have no right to
   take part unless a procurement agreement grants it. CETA's EU-level coverage is reported to be
   three EU-wide entities only [U]. EMSA's own €400/day expert database admits only nationals of
   the EU/EEA and IPA/ENP countries.
4. **Defence money is the hardest to reach from Canada, except NATO's.** The European Defence
   Fund lets consortia cooperate with non-associated third-country firms, but "the costs related
   to those activities shall not be eligible for support". UK authorities may disregard non-UK
   suppliers in defence and security buys. NATO is the exception: Canada is a member nation, so
   NSPA source-file registration and NCIA Declarations of Eligibility (via the Canadian Joint
   Delegation) are available.
5. **Free and incumbent services cap prices for detection.** EMSA runs Copernicus Maritime
   Surveillance (CMS) for member states and EU bodies, and Skylight and GFW cover fisheries.
   Incumbents hold the paid niches: OceanMind (MMO), Kongsberg Norcontrol (UK coastguard, to
   2028-03-31), Gatehouse (Irish Lights, 7 years), Satlink (Malta) and LuxSpace (EMSA T-AIS). The
   sellable gap is **integration and provenance around their data**, not more detections.

## Ranked candidates

Score = closable in six to nine months (1–3) × revenue (1–3) × fits today (1–3). The scores are
judgement calls, and the notes give the reasons. "Sub" means subcontract.

| # | Candidate | What they'd buy from planetar | Route / eligibility | Size signal | Score |
|---|---|---|---|---|---|
| 1 | **OceanMind** (UK non-profit, Harwell; MMO's prime) | Sub: Sentinel-1 SAR processing and detection QA, AIS correlation, provenance per detection | Private sub (no procurement rules) | MMO award £1.5M, 2024-08-01 → 2026-07-31, **57% subcontracted to five suppliers** (35% "SAR data processing, QA of vessel detected") | 2×1.5×2 = **6** |
| 2 | **ESA InCubed** (with Canada's subscription) | Co-funded ESA contract to productise open dark-vessel fusion with provenance | Continuous pitch via ESA ORBIT portal; Canada subscribed **€8M** | ~80% of Canada's ESA money returns to Canadian industry | 1.5×2×2 = **6** (co-funded, not a customer) |
| 3 | **Kystverket** (Norwegian Coastal Administration) | Dark-vessel detection service: Sentinel-1/2 + AIS | Negotiated with call; Norway and Canada are both GPA parties | NOK 15,000,000, 12 months + extension option | 1×2×2.5 = **5** (watch the next round) |
| 4 | **UK Hydrographic Office** software DPS 2.0 | Maritime/geospatial software development and support call-offs | Dynamic purchasing system (join, then mini-competitions); UK–Canada TCA gives treaty-state status for covered contracts; UKHO is MoD (defence discretion) | DPS valued £4,000,000 | 1.5×1.5×1.5 = **3.4** |
| 5 | **NATO NSPA / NCIA** (and ACT's Task Force X Baltic) | Small COTS/services buys around maritime data fusion | NSPA source-file registration; NCIA DoE from the Canadian Joint Delegation, per opportunity | Not found for maritime analytics | 1×2×1.5 = **3** |
| 6 | **Horizon Europe Pillar II consortia** | Paid partner (beneficiary) work package: open fusion and provenance | Canada associated to Pillar II [U: signed 2024-07-03] | 2026 CL3 border topics are people-centric (excluded); next relevant deadlines are 2027 | 1×2×1.5 = **3** (grant, not customer) |
| 7 | **Offshore-infrastructure operators** (cable and wind TSOs) | AIS geofence plus SAR check around cable corridors; hosted pilot | Utilities procurement or private contract | Ørsted CTV-monitoring award (8 years) went to four EU/UK SMEs; RTE buys guard vessels | 1×1.5×1.5 = **2.25** |
| 8 | **EFCA expert list** EFCA/2026/CEI/0007 | Individual expert days in "Fisheries data and control technologies" | Call for expression of interest, open until 2031-04-10; **nationality rule not found** | Not found (EMSA's analogous rate is €400/day) | 1×1×2 = **2** |
| 9 | **European data vendors as partners** (Kpler/MarineTraffic/Spire, KSAT/Vake, CLS, e-GEOS) | Sub or licence: open ingest and provenance layer | Private | Kpler paid ~USD 241M for Spire Maritime [U] | 1×1.5×1 = **1.5** |
| 10 | **UK HM Coastguard (MCA)** vessel-traffic transformation | Future MDA platform component | Open procedure when re-tendered | C-Scope bridge contract £4,215,572 to Kongsberg Norcontrol until 2028-03-31 | 0.5×3×1 = **1.5** |

**On the order:** #1 and #2 tie. OceanMind ranks first because it can start with a conversation
and pays commercially. InCubed money is co-funded and arrives at ESA's contracting pace.
Kystverket ranks third despite the best fit, because its own entry rule (an operational system
with a customer) cannot be met before the next round.

## Per-candidate notes

### 1. OceanMind: subcontract under the MMO surveillance framework
- **What is bought today:** the Marine Management Organisation (MMO) awarded "International
  Maritime Surveillance Services" to OceanMind Limited, £1,500,000, 2024-08-01 → 2026-07-31
  (Contracts Finder 04d772a7). The Find a Tender OCDS record for 025029-2024 shows the procedure
  was **covered by the GPA** and the work was 57% subcontracted: 35% "Plan/collect satellite
  imagery, SAR data processing, QA of vessel detected", 9% RF detections, plus imagery and data
  supply. OceanMind also won Defra's "Vessel pressure analysis from remote sensing and AIS",
  £114,999, 2024-11-18 → 2025-03-31 (Contracts Finder 54493b29). The 2021–2023 predecessor was
  £2.4M [U].
- **Follow-on:** the contract ended 2026-07-31. A 2026 re-procurement or extension was **not
  found** on Contracts Finder.
- **Fit:** Sentinel-1 CFAR detection, AIS correlation and `/trace/:id` provenance map onto the
  35% SAR-processing and QA share. Planetar would be one of several small subcontractors, which
  is plausible for an open-source shop.
- **Blocker:** no measured detection accuracy (FIT.md). The xView3 run must land first. OceanMind
  already has data partners, including Spire [U].
- **First step:** after the xView3 numbers exist, use OceanMind's public website contact form
  (oceanmind.global) to propose a costed SAR-processing/QA pilot on one Overseas Territory AOI.
  Separately, watch Find a Tender for an MMO notice.

### 2. ESA InCubed, funded by Canada's subscription
- **Facts:** the CSA FAQ (modified 2026-06-02) says "Canada subscribed €8 M to InCubed" and that
  "approximately 80% of Canada's ESA investments return to Canadian industry" (geo-return).
  InCubed says entities "can apply at any time" by submitting a Proposal Part 1 outline through
  ESA's ORBIT portal. The national delegation must support the idea, and co-funding is
  "zero-equity", with the IP kept by the company. Co-funding percentages were **not found**.
- **Fit:** EO-exploiting product development: dark-vessel re-identification on Sentinel-1 with
  provenance. It is ESA money, but it is co-funding and a development contract, not a customer.
- **Blocker:** company co-funding share; the CSA must back the pitch; ESA contracting time.
- **First step:** email the CSA Canada–ESA Program Office (`esa_programme-esa_program@asc-csa.gc.ca`,
  listed on the FAQ) to ask whether a one-person company fits Canada's InCubed envelope, then
  pitch via ORBIT.

### 3. Kystverket (Norway): the clearest dark-vessel buyer in Europe
- **Notices:** competition 2026/2237, "Procurement of satellite based and optical SAR" (TED
  369106-2026, open procedure), was **cancelled 2026-08-14** (award-stage notice 567701-2026). A
  new competition replaced it (TED 587752-2026): a negotiated procedure with a qualification phase
  closing 2026-09-23, **NOK 15,000,000**, 12 months with an extension option. Purpose:
  "verification of AIS data", "detection of vessels that do not send AIS (so-called 'dark
  vessels')". Kystverket tested Vake AS's system (vake.ai) on Sentinel-1/2 and its own AIS in
  2025. Vake is majority-owned by KSAT since 2024-03 [U]. **Entry rule:** "Developments in this
  procurement cannot be included", plus documentation of "operative use for at least one customer
  or final user". The winner was **not found**.
- **Eligibility:** Norway and Canada are both WTO GPA parties (WTO parties list). Whether this
  notice is GPA-covered was not read.
- **Fit:** the strongest match in this note (Sentinel-1 detection plus AIS discrepancy). The gaps
  are optical (Sentinel-2) detection, the operational reference and the vessel typing it implies.
- **First step:** none to send now. Watch Doffin/TED for the extension or re-tender (about
  2027-Q3 at the earliest, if the 12-month term starts around 2026-Q4). Use the notice as the
  acceptance checklist for planetar's first customer pilot elsewhere.

### 4. UK Hydrographic Office: "Maritime/Geospatial Software Development and Support Services – DPS 2.0"
- Contracts Finder 8fb3b552 (published 2022-10-14): £4,000,000, SME-suitable. A correction notice
  changes the duration from 48 to **76 months**, but the listed end date is still 2026-11-17.
  **Whether it still admits new suppliers is not verified.** Scope: support existing software and
  "design, build and support new software and cloud-based capabilities … primarily in the
  maritime/geospatial sector".
- **Eligibility:** the UK–Canada Trade Continuity Agreement and the CPTPP are both in Procurement
  Act 2023 Schedule 9 (legislation.gov.uk), so Canadian suppliers are treaty-state suppliers for
  covered contracts. Below-threshold contracts may be reserved for UK suppliers, and in defence
  and security contracts authorities may disregard non-UK suppliers (gov.uk treaty-state
  guidance). UKHO is part of the MoD [U].
- **First step:** check the DPS status on Find a Tender and the UKHO supplier portal before
  anything else.

### 5. NATO (NSPA, NCIA; ACT Task Force X Baltic; MARCOM; Baltic Sentry)
- **Eligibility, primary (DND pages):** NSPA requires a one-time registration in its source file
  ("approximately two weeks"). For NCIA, the Canadian Joint Delegation nominates companies through
  a Declaration of Eligibility, "repeated for each NOI". The First Secretary Investment at the
  delegation issues DoEs.
- **Demand:** Baltic Sentry (launched 2025-01) promised "enhanced partnerships with the private
  sector" [U]. ACT's Task Force X Baltic trialled Saildrone USVs, 2025-06-16 → 06-27 [U, vendor
  release]. The UK-led JEF "Nordic Warden" AIS risk-scoring system was activated 2025-01 with no
  vendor named (Breaking Defense, 2025-01-07). No NATO notice for maritime analytics was found.
- **First step:** register in the NSPA source file (no cost), then watch PSPC/CanadaBuys for NATO
  NOIs. Already-covered NATO items: DIANA and eAirC2 (see 08).

### 6. Horizon Europe Pillar II (paid partner role, not a customer)
- Canada is associated to Pillar II, signed 2024-07-03 [U: horizon-europe.gouv.fr]. Canadian
  entities can be funded beneficiaries [U: ISED slides].
- Cluster 3 2026 border-management call (deadline 2026-11-05, REA page): its three topics
  (border monitoring, travel, age checks) concern people, so they are excluded. The maritime
  "efficient border surveillance and maritime security" topic was in 2025 (closed 2025-11-12). An
  open BM topic has a deadline of 2027-11-04 [U].
- **First step:** none in the window. Track the Cluster 4/6 2027 topics (space downstream, ocean)
  for consortia that need an open fusion partner.

### 7. Offshore critical-infrastructure operators
- Ørsted's "Vessel Monitoring System" tender (TED 690696-2025; award 520999-2026, 8 years) went
  to Cetasol (SE), Mocean Forecast (NL), Reygar (UK) and Marfle (FI). That buy is onboard
  crew-transfer-vessel logging, **not a planetar fit**. It does show that energy majors award
  vessel-data work to SMEs. RTE (France) tendered "Marine Surveillance Services (Guard vessel)"
  for subsea cables (TED 814785-2025). No AIS/SAR cable-corridor analytics tender was found.
- **First step:** none to send. A demo around a public Baltic cable corridor would be the asset.

### 8. EFCA call for expression of interest EFCA/2026/CEI/0007
- TED 486674-2026 (published 2026-07-14): lists of experts for "Capacity building and coastguard
  related functions and Fisheries data and control technologies"; 60 months; deadline 2031-04-10;
  place of performance "Anywhere"; contact `procurement@efca.europa.eu`. The documents sit on the
  EU Funding & Tenders portal, **not read** (JavaScript-only); efca.europa.eu returned 403.
- **Eligibility caution:** EMSA's comparable CEI (EMSA/CEI/1/2026; documents downloaded and read)
  admits only "Nationals of EU Member States, Iceland, Liechtenstein, Norway, and of the countries
  benefiting from … IPA and … ENP". It pays €400/day, caps payments at €140,000, and includes
  profiles 28 "Maritime digital services" and 34 "Maritime surveillance". If EFCA's rule is
  similar, a Canadian national is ineligible.
- **First step:** read the EFCA call documents on the portal for the nationality clause.

### 9 and 10. Vendors and the UK coastguard
- European data vendors (Kpler, which owns MarineTraffic and Spire Maritime, closing reported
  2025-04 [U]; KSAT/Vake; CLS; e-GEOS) are possible licensees of an open provenance layer but
  have no evident need. CLS holds EMSA's LRIT maintenance (€1,100,000, TED 155563-2025) and e-GEOS
  holds the COSMO-SkyMed licence (TED 57819-2025).
- MCA's C-Scope award says services continue "until such a time a new solution is sought in line
  with a technical transformation programme" (Contracts Finder 4f5c2a9e). That makes it a
  2027–2028 watch, not a 2026 sale.

## Eligibility for a Canadian supplier

| Buyer type | Verdict | Basis |
|---|---|---|
| EU institutions and agencies (EMSA, EFCA, SatCen, EDA) | **Effectively closed** | ESMA: agency procurement is "not covered by the WTO … GPA"; "Tenderers established in third countries … do not have the right to participate" unless an agreement grants it. CETA's EU-level coverage is reported as three EU-wide entities [U]. EMSA BDW excluded Canada (see 08). EMSA expert CEI is nationality-restricted |
| EU member-state central and sub-central buyers | **Open in law for covered, non-defence contracts above thresholds** | Canada and the EU are GPA parties (WTO list). CETA ch. 19 adds sub-central coverage; EU central threshold from 130,000 SDR [U]. CJEU C-652/22 (Kolin): non-agreement bidders lack equal-treatment rights [U] |
| Norway, Switzerland | Open for GPA-covered contracts | GPA parties (WTO list); per-notice coverage not checked |
| UK | **Open for covered contracts above threshold**; below-threshold may be reserved; defence and security discretionary | Procurement Act 2023 Sch. 9 lists the UK–Canada TCA and CPTPP; gov.uk treaty-state guidance |
| Defence (EDF, national defence) | **Closed to funding** | EDF Reg. 2021/697 Art. 9(6): cooperation with third-country entities allowed but "costs … shall not be eligible for support". GPA excludes most defence. Canada–EU SAFE participation concluded 2025-12-01 [U], but it concerns common procurement of defence products |
| NATO (NSPA, NCIA) | **Open** (member nation) | DND guide and FAQ: NSPA source file; NCIA DoE via the Canadian Joint Delegation |
| ESA | **Open to the extent Canada subscribes** | Canada subscribed €8M to InCubed; about 80% geo-return to Canadian industry (CSA FAQ) |
| Horizon Europe | Pillar II open as a beneficiary | Association signed 2024-07-03 [U] |
| Private European firms (subcontracts) | **Open** | No procurement rules apply. OceanMind's MMO contract is the documented case of public money flowing to subcontractors |

**Bottom line:** the routes legally open to a Canadian firm are national and UK covered
contracts, NATO, ESA (InCubed), Horizon Pillar II and private subcontracts. EU agencies and EU
defence funding are not open. For a one-person company the practical route is private
subcontracting, because every open public route also demands references, turnover or an
operational customer.

## Not realistic (next six to nine months), and why
- **EMSA CMS / CleanSeaNet satellite services.** Tender EMSA/2026/OP/0002 (TED 306092-2026):
  €66M in two lots, €38M SAR and €28M VHR optical, 48 months, closed 2026-06-23. These buy
  imagery and licences, and the buyer is an EU agency, so it is closed to Canada. EMSA delivers
  CMS products to member states and EU bodies (EMSA Copernicus page), which undercuts selling
  detections to EU coastguards.
- **EMSA T-AIS** (awarded to LuxSpace, €1,860,000, TED 674569-2026); **EMSA SAT-AIS** (Spire,
  €8.4M framework [U]); **EMSA expert database** (nationality rule above).
- **Commissioners of Irish Lights.** A voluntary ex-ante transparency (VEAT) notice for direct
  award of an AIS traffic analysis/MDA platform to Gatehouse Maritime, 7 years (5+2), €340,000
  (TED 500760-2026). Locked until about 2031–2033.
- **Malta Fisheries Integrated Information System.** Competitive dialogue awarded to Satlink SL
  (TED 806666-2025). **Sweden HaV VMS concession** (TED 743346-2025) needs onboard trackers.
- **UK JMSC.** Airbus supplies satellite vessel-detection reports [U, 2021 release]; defence
  discretion applies.
- **French MoD prospective study** "Maritime domain awareness …" (TED 659778-2026, €40,000,
  closes 2026-10-23). French-language defence policy study, closes tomorrow, and outside
  planetar's competence.
- **Denmark DALO "Maritime Domaine Awareness kontrakt"** (TED 472313-2026, DKK 1.63bn).
  Aircraft operation.
- **EDF consortia** (no fundable role; see the eligibility table). **Frontex**: excluded by the
  scope rule.
- **Fisheries agencies and NGOs** (EFCA, national fisheries control): Skylight and GFW access is
  free for selected governments [U], and EMSA CMS covers EU users. Sell integration, not
  detections.
- **Windward** (Israeli), **Kpler**, **Lloyd's List**, **S&P**: these companies own the sanctions
  and shadow-fleet analytics market for insurers, banks and traders, built on paid data planetar
  lacks. Not a market for a pre-revenue entrant.

## Before selling anything in Europe
1. Land the xView3 benchmark. Every candidate above needs a measured detection number.
2. Get one operational reference user anywhere (Canada first: see `CUSTOMERS-research.md`).
   Kystverket's entry rule shows why.
3. Resolve AIS redistribution rights (aisstream.io terms not found; see the first pass). In
   Europe, quote prices only on customer-supplied AIS.
4. Free registrations that keep doors open: the NSPA source file; a Find a Tender supplier
   account for UK notices.

## Sources (read 2026-10-22 unless tagged [U])
- TED v3 search API, notices: 587752-2026, 567701-2026, 369106-2026 (Kystverket); 306092-2026,
  674569-2026, 155563-2025, 57819-2025 (EMSA); 486674-2026 (EFCA CEI; HTML at
  https://ted.europa.eu/en/notice/486674-2026/html); 500760-2026 (Irish Lights); 520999-2026,
  690696-2025 (Ørsted); 806666-2025 (Malta); 743346-2025 (HaV); 659778-2026 (French MoD);
  472313-2026 (DALO); 814785-2025 (RTE); 515869-2026 (Frontex, excluded) — https://api.ted.europa.eu/v3/notices/search
- EMSA calls page — https://www.emsa.europa.eu/procurement/calls.html
- EMSA/CEI/1/2026 notice and profiles (zip) — https://www.emsa.europa.eu/procurement/calls/item/5649-emsa-cei-1-2026.html
- EMSA Copernicus page — https://www.emsa.europa.eu/copernicus.html
- ESMA procurement (GPA and third-country statement) — https://www.esma.europa.eu/interact-with-esma/procurements
- EDF Regulation 2021/697, Art. 9 (consolidated text via lawplayer mirror) — https://lawplayer.com/eu/act/32021R0697
- WTO GPA parties — https://www.wto.org/english/tratop_e/gproc_e/memobs_e.htm
- Procurement Act 2023 Sch. 9 — https://www.legislation.gov.uk/ukpga/2023/54/schedule/9
- Treaty-state guidance — https://www.gov.uk/government/publications/procurement-act-2023-guidance-documents-define-phase/guidance-treaty-state-suppliers-html
- Contracts Finder API notices 04d772a7-028c-4dbb-a1d9-86bb5c21dc6b (MMO), 54493b29-c753-4a7a-9d2d-7474605e6bce (Defra), 4f5c2a9e-4ba5-4d28-bc34-fc25151dca91 (MCA), 8fb3b552-5188-4d62-a330-0e90daa3be50 (UKHO DPS) — https://www.contractsfinder.service.gov.uk/api/rest/2/get_published_notice/json/{id}
- Find a Tender OCDS 025029-2024 (MMO subcontracting, GPA) — https://www.find-tender.service.gov.uk/api/1.0/ocdsReleasePackages/025029-2024
- CSA Canada–ESA FAQ (mod. 2026-06-02) — https://www.asc-csa.gc.ca/eng/funding-programs/canada-esa/webinar-faq-canada-investments-esa.asp
- InCubed — https://incubed.esa.int/how-to-apply ; https://incubed.esa.int/
- DND NATO guide and FAQ — https://www.canada.ca/en/department-national-defence/services/doing-business-with-foreign-defence-markets/guide-navigating-nato-procurement.html ; …/frequently-asked-questions-doing-business-with-nato.html
- REA Cluster 3 border management — https://rea.ec.europa.eu/funding-and-grants/horizon-europe-cluster-3-civil-security-society/effective-management-eu-external-borders_en
- Nordic Warden (2025-01-07) — https://breakingdefense.com/2025/01/joint-expeditionary-force-launches-russian-shadow-fleet-undersea-cable-ai-tracking-system/
- Finland maritime surveillance hub (about 2026-01-26) — https://news.err.ee/1609922204/finland-to-launch-maritime-surveillance-hub-together-with-baltic-allies
- [U] CETA EU-wide entities — https://langlois.ca/?p=11297 ; CETA thresholds — https://www.infobusiness.bcci.bg/content/file/Canadian_Government_PRocurement_Acess_to_EU_and_CETA.pdf
- [U] Kolin C-652/22 — https://www.nortonrosefulbright.com/en/knowledge/publications/f79ec950/ecj-confirms-public-tenders-restrictions-for-companies-from-third-countries
- [U] Canada–SAFE — https://www.squirepattonboggs.com/insights/publications/canadian-companies-to-be-allowed-preferential-access-under-eu-safe-defence-investment-program/
- [U] Horizon association signing — https://www.horizon-europe.gouv.fr/association-du-canada-horizon-europe-37541
- [U] Vake/KSAT — https://app.dealroom.co/companies/vake ; Kpler/Spire — https://www.ship-technology.com/news/kpler-acquisition-spire-maritime/
- [U] Spire EMSA SAT-AIS — https://smallsatnews.com/2024/02/21/spire-global-awarded-millione-by-the-european-maritime-safety-agency/
- [U] Task Force X / Saildrone — https://www.saildrone.com/news/unmanned-unmatched-saildrone-boosts-allied-awareness-in-nato-task-force-x-baltic-demo ; Baltic Sentry — https://maritime-executive.com/article/nato-agrees-to-enhance-baltic-surveillance-by-air-and-sea
- [U] JMSC/Airbus (2021-06-28) — https://airbus.com/en/newsroom/press-releases/2021-06-airbus-to-provide-satellite-based-maritime-surveillance-services
- [U] Skylight/GFW free access — https://www.seafoodsource.com/news/environment-sustainability/global-fishing-watch-forms-collaboration-with-vulcan-inc
- Not reachable: efca.europa.eu (403), EU Funding & Tenders portal documents (JavaScript-only),
  EUR-Lex (empty response), TED HTML for most notices (bot challenge), find-tender.service.gov.uk
  HTML (403).
