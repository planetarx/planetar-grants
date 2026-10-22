# First paying customers: Canada and non-US, non-European markets (2026-10-22)

**Question:** after the first pass ([`CUSTOMERS-research.md`](CUSTOMERS-research.md)), which buyers in
**Canada** and in **non-US, non-European** countries could realistically pay planetar (GPLv3
software + paid support, hosting, integration, pilots, subcontracts; decision D2a) within about
6–9 months? The US and Europe are out of scope; Europe is researched separately.

**Snapshot date: 2026-10-22.** Every fact was read on the cited page on 2026-10-22 unless tagged
**[U]** (search-engine summary, aggregator or secondary source only). "Not found" means one or two
targeted searches found nothing; it does not mean the thing doesn't exist. Nothing was sent to
anyone and no one was contacted.

**Scope rule:** vessels only. People-tracking uses (migrant/asylum-boat interdiction, crew or
passenger analytics) are excluded.

**This pass does not repeat the first one.** Larus, Clear Seas, Transport Canada EMSA, BC First
Nations Guardian programs, World Bank PROP/PROPER, DFO Dark Vessel Detection's MDA contract,
Kpler's Transport Canada AIS contract, the CAD 40k no-bid threshold and ProServices are covered
there and only cross-referenced here.

**What planetar can sell** ([`../planetar-niwc-mda/FIT.md`](../planetar-niwc-mda/FIT.md)): live
AIS ingest (Victoria, Hormuz), Sentinel-1 CFAR ship detection, webcam YOLO "boat" detection, a
hydrophone pipeline, rule-based kinematic dark-vessel re-ID, per-result provenance
(`/trace/:id`), and REST/WebSocket/TCP delivery. **Gaps:** no measured accuracy, no vessel typing,
no S3/bulk export, no API auth, one person, no owned data.

---

## Headline findings

1. **The Canadian Coast Guard is now a defence-funded MDA buyer, and it is new money.** The Coast
   Guard moved into National Defence on 2025-09-02. On 2026-05-22 it received **CAD 816M over
   seven years** for security work: a year-round **MDA Hub in Iqaluit**, 24/7 Marine Security
   Operations Centres, Arctic radar and drones. No contract vehicle for analytics has been posted
   yet. A Coast Guard pilot with Zighra (2024, AIS + GNSS anomaly fusion, Innovative Solutions
   Canada) shows the route a small firm can take. This is the largest *new* domestic pool.
2. **The best near-term Canadian lead is a small Victoria consortium, not a department.** Open
   Ocean Robotics (Victoria) leads the CAD 3.8M Ocean Supercluster **ASOMS** project (2025-03-26),
   which names "maritime domain awareness" and "AI-enabled data services". A private subcontract
   for an open detection, fusion and provenance layer needs no procurement vehicle. **Caveat:**
   Steven's spouse works at OOR (DECISIONS.md C2), so this lead needs disclosure and a founder
   decision first.
3. **Canada's own Dark Vessel Detection program already covers most of Latin America and part of
   Asia, through MDA Space.** Countries named: Colombia, Costa Rica, Ecuador, Panama, Peru, Mexico
   (CAD 7M, announced 2026-07-17), the Philippines (NCWC, 2023), and FFA. In those countries
   planetar competes with a free Canadian government service. The realistic angle is services
   *to DFO* around that program, not sales to partner states.
4. **The Pacific and Australia are locked by Starboard (NZ).** NZ Defence bought a cross-government
   Starboard subscription (2024-07-12). A NZ budget line of NZD 4.5M a year to 2049 [U] also pays
   for Pacific access, and AFMA subscribes too (2022). With Skylight free, there is no room for paid
   analytics there.
5. **Canada's export-support tools mostly don't fit a one-person firm.** CanExport SMEs now
   requires **3 full-time employees and CAD 300k revenue**. The CCC's International Prime
   Contractor route targets deals **over CAD 10M** [U]. What remains is the free Trade Commissioner
   Service and direct registration on UN and development-bank portals (UNGM). The one sized,
   open international tender found is the **IOTC regional VMS pilot**: a published budget of
   about EUR 65–89k to set up plus EUR 132–198k a year recurring, cloud-hosted. It is an
   on-model target but a partial fit.

## Ranked candidates

Score = closable in 6–9 months (1–3) × revenue (1–3) × fits today (1–3). These are judgement calls,
explained in the notes. "Cross-ref" rows are scored in the first pass.

| # | Candidate | Country | What planetar would sell | Route | Score |
|---|---|---|---|---|---|
| 1 | **Open Ocean Robotics / ASOMS consortium** | CA (Victoria) | Subcontract: open AIS + EO detection + fusion/provenance layer for USV and aerial sensor data | Private subcontract | 2×1.5×2.5 = **7.5** |
| 2 | **Larus Technologies** (cross-ref) | CA | Ingest/provenance subcontract under its IDEaS and RCN contracts | Private subcontract | **8** (first pass) |
| 3 | **Canadian Coast Guard security/MDA expansion** (Iqaluit MDA Hub, MSOCs 24/7) | CA | Small pilot: open fusion and provenance for a hub or MSOC picture; later integration | ≤ CAD 40k directed (ProServices) or an ISC Testing Stream pilot | 1.5×2×2 = **6** |
| 4 | **IOTC regional VMS pilot** (Seychelles; volunteers Australia, Seychelles, Philippines) | Intl | Cloud-hosted open VMS platform: ingest, zones, alerts, data distribution, hosting and support | International tender (status not found) | 1×2.5×1.5 = **3.75** |
| 5 | **DFO international DVD program** (for partner states) | CA → LatAm/Asia | Services to DFO: open integration of DVD output with a partner's AIS/VMS picture; Sentinel-1 cross-check; training | ≤ CAD 40k directed DFO contract | 1×1.5×2 = **3** |
| 6 | **Pacific Islands FFA** (RFSC Honiara) | Intl | Platform build or data-visualisation work like RFP CP16_2425 [U] | FFA RFPs by email (`procurement@ffa.int`, first pass) | 1×1.5×2 = **3** |
| 7 | **Inuit marine monitoring** (NTI's IMMP; Iqaluit hub's Inuit partners) | CA (Nunavut) | Community-owned AIS + camera monitoring, self-hosted | Direct services contract | 1×1×2.5 = **2.5** |
| 8 | **IDB / World Bank fisheries-MCS consultancies** (e.g. IDB Grenada RG-T4867) | LatAm/Carib, Pacific | Firm consultancy: digital MCS pilot design and data analytics | Bank-financed consultant selection | 1×1.5×1.5 = **2.25** |
| 9 | **PIER71 Smart Port Challenge** (MPA + NUS Enterprise) | Singapore | Paid pilot with a port or shipping problem owner | Annual challenge (2026 closed 2026-06-15) | 1×1.5×1.5 = **2.25** |
| 10 | **Defence primes via ITB SME credit** (GDMS-Canada, Lockheed Martin Canada, CAE, Boeing P-8A team) | CA | Niche software subcontract that earns the prime ITB credit | Supplier registration + ITB pitch | 0.5×2×1.5 = **1.5** |
| 11 | **Indian Ocean Commission RMIFC/RCOC** (Madagascar/Seychelles) | Intl | Software support or licence renewals | EU-funded "local open tender" | 0.5×1×1 = **0.5** |
| 12 | **YARIS** (Gulf of Guinea information-sharing system) | Intl | Low-cost open hosting after EU funding ends | Not defined | 0.5×1×1 = **0.5** |

**Ordering note:** #2 scores above #1 but is a first-pass cross-reference. #1 and #3 are the only
new leads that can start with a conversation this quarter. #1 is conflict-gated (C2).

## Per-candidate notes

### 1. Open Ocean Robotics / ASOMS consortium (Victoria)
- **Evidence:** CAD 3.8M Air Sea Ocean Monitoring System project, of which CAD 1.4M is Ocean
  Supercluster money. Announced 2025-03-26. Lead: Open Ocean Robotics (Victoria). Partners:
  Seahawk Robotics, ASL Environmental Science (Saanichton), Rockland Scientific (Victoria), Glas
  Ocean Electric. Scope: gaps in "maritime domain awareness", MPA monitoring and offshore-energy
  surveillance, "robotic ocean and aerial observing platforms with AI-enabled sensing", and "new
  AI-enabled data services". No named data platform; duration not stated
  ([OSC](https://oceansupercluster.ca/project/canadas-ocean-supercluster-announces-3-8m-air-sea-ocean-monitoring-system-asoms-project/)).
  The Supercluster signed an MoU with DND on marine sensing (pilots, testing, demonstrations;
  undated [U]) ([Ocean News](https://oceannews.com/news/defense/canadas-ocean-supercluster-signs-mou-with-department-of-national-defence-to-advance-marine-sensing/)).
- **Incumbent:** not found. Each partner sells hardware or sensing, and no fusion or software
  integrator is named.
- **Fit:** high. planetar-eo (camera detection), planetar-ais and the provenance trail match "AI
  data services" for USV/drone feeds. The company is in the same city as the live demo.
- **Blockers:** unknown budget left for subcontracts. They may build in-house. IP terms: GPLv3 vs
  a hardware vendor's closed stack. **Conflict of interest:** Steven's spouse works at Open
  Ocean Robotics (`../planetar-brainstorm/DECISIONS.md` C2). Any approach must disclose this up
  front and follow OOR's own conflict rules. Supercluster co-funding rules may also restrict
  related-party subcontracts (not checked). Founder decision before any contact.
- **First step:** after the C2 decision, use the Open Ocean Robotics public contact form. Offer a 30-minute demo of
  planetar.ca in Victoria, framed as the open data layer for ASOMS outputs. Also check whether
  Ocean Supercluster membership (needed to join future project consortia) is free for a
  one-person firm.

### 2. Larus Technologies
Cross-reference only; see the first pass (#1 there).

### 3. Canadian Coast Guard: new security and MDA mandate
- **Evidence:** the Coast Guard moved to National Defence by Order in Council on 2025-09-02
  ([DND transition page](https://www.canada.ca/en/department-national-defence/campaigns/transition-of-the-canadian-coast-guard-into-national-defence.html)).
  On 2026-05-22 Minister McGuinty, at Iqaluit, announced **CAD 816M over seven years**: an "MDA
  Hub in Iqaluit … for collecting and analyzing maritime intelligence", four Arctic long-range
  radar sites, and aerial, surface and subsurface drones
  ([release](https://www.canada.ca/en/canadian-coast-guard/news/2026/05/minister-mcguinty-announces-816-million-investment-to-strengthen-canadas-maritime-security.html)).
  The backgrounder says MSOC operations "will be expanded to 24/7, year-round monitoring". It also
  says partners will "integrate and analyze data in real time", and that the 2026 Act lets the
  Coast Guard "collect, receive, share, and analyze information"
  ([backgrounder](https://www.canada.ca/en/canadian-coast-guard/news/2026/05/delivering-on-the-canadian-coast-guards-expanded-security-responsibilities.html)).
  A June 2026 Public Safety release adds a 24/7 MSOC in Niagara and up to 11 Great Lakes / St.
  Lawrence radar sites [U] (page did not load).
- **Precedent for a small firm:** Zighra (Ottawa) got a Coast Guard pilot for GenesysInsights.
  It fuses GNSS signal data with terrestrial and satellite AIS to flag anomalies, "part of the
  Innovative Solutions Canada program" (2024-04-04, value not disclosed)
  ([GPS World](https://www.gpsworld.com/canadian-coast-guard-awards-contract-to-zighra/)).
- **What they buy today:** no analytics contract was found on CanadaBuys. Notices found were
  vessel and coatings RFIs only [U].
- **Fit:** good for a provenance-first fusion layer ("collect, receive, share" with partners is
  an audit-trail problem). Arctic AIS + Sentinel-1 is buildable.
- **Blockers:** no posted requirement. Security screening is likely for intelligence work
  (unverified). The ISC Testing Stream wants TRL 7–9 (first pass). **Scope check:** the Coast
  Guard's new powers came through an immigration and borders act. Offer vessel-picture work only,
  never person-focused analysis.
- **First step:** pre-qualify on ProServices (first pass). Then use the Coast Guard's public
  media and general enquiry channels to ask which directorate owns the Iqaluit MDA Hub and
  whether it is taking industry briefings. Watch CanadaBuys for "maritime domain awareness" and
  "Iqaluit".

### 4. IOTC regional VMS pilot (Indian Ocean Tuna Commission, Seychelles)
- **Evidence:** the consultant's implementation plan (2025-02-01, Renascentia CS) sets a 3-month
  bidding phase, 6–9 months of setup and 2 years of operation. It recommends a cloud environment
  hosted "in the IOTC Secretariat headquarters' country or in any CPC country". Budget table:
  set-up items total about **EUR 65–89k** (cloud, application, customisation, up to five
  interconnections, training). Monthly fees for hosting, SaaS, support and maintenance total
  **EUR 7–10.5k**, i.e. EUR 132–198k over two years. A 1-FTE operator (USD 60k a year) is staffed
  by IOTC, not the vendor ([IOTC plan PDF](https://iotc.org/sites/default/files/documents/2025/01/Implementation_plan_IOTC_VMS_pilot_Project.pdf)).
  The key-decisions note (2025-03-24) lists volunteer CPCs **Australia, Seychelles, Philippines**.
  Mandatory specs include NAF/XML/JSON/CSV over HTTPS/REST/SOAP with two-way SSL, MTU event
  codes, zones, and admin/operator/viewer roles
  ([IOTC key decisions](https://iotc.org/sites/default/files/documents/2025/03/IOTC-2025-CoC22-11_Add3-IOTC_VMS_Pilot_Project_Key_decisions.pdf)).
- **Tender status:** **not found** (no notice located for 2025 or 2026). A comparable FAO tender
  for a GFCM VMS platform ran 2026-07-22 → 2026-09-02 via UNGM only
  ([UNGM 308161](https://www.ungm.org/Public/Notice/308161)). The GFCM is Mediterranean, so it is
  shown only as a precedent for how these are bought.
- **Incumbents:** commercial VMS vendors such as Trackwell (AFMA's VMS) [U]
  ([World Fishing](https://www.worldfishing.net/vms-to-help-afma-ensure-compliance/1025197.article)).
- **Fit:** partial. The architecture is planetar's (ingest bus, REST, alerts, zones, provenance,
  hosting under GPLv3), but **VMS formats (NAF), MCSP connectors, roles/auth and ISO-certified
  hosting are all unbuilt**. Bidder eligibility rules are unknown.
- **First step:** register on UNGM (free basic registration). Use the IOTC Secretariat's public
  contact to ask whether and when the VMS pilot tender will be published. Don't bid until auth
  and NAF ingest exist.

### 5. DFO Dark Vessel Detection international program
- **Evidence:** Global Affairs Canada (2026-07-17): a CAD 7M contribution so Mexico can "access
  Canadian satellite technology" through "the Dark Vessel Detection program at Fisheries and
  Oceans Canada". The release says it "is currently being implemented in Colombia, Costa Rica,
  Ecuador, Panama and Peru"
  ([Canada in Mexico](https://canadainmexico.com/2026/07/minister-anand-meets-with-mexicos-secretary-of-foreign-affairs-roberto-velasco-announces-projects-advancing-canada-mexico-action-plan/)).
  The Philippines' National Coast Watch Center signed a DVD arrangement with DFO on 2023-10-12
  ([DFA PH](https://dfa.gov.ph/dfa-news/news-from-our-foreign-service-postsupdate/33492-philippines-and-canada-sign-arrangement-on-the-dark-vessel-detection-system) [U]).
  The Shared Ocean Fund (Indo-Pacific Strategy, CAD 84.3M over 5 years) funds DVD deployment and
  CAD 6.5M for the Joint Analytical Cell [U]
  ([TMT](https://www.tm-tracking.org/post/canada-and-uk-announce-partnership-with-joint-analytical-cell-to-combat-iuu-fishing)).
  MDA Space holds a 2023 DFO Indo-Pacific contract (2 years + up to 3 option years) [U]
  ([Undercurrent](https://www.undercurrentnews.com/2023/07/04/canadian-firm-to-use-satellites-to-track-indo-pacific-iuu-fishing/)).
- **Implication:** in these partner countries a direct sale competes with a free Canadian
  service. Any opening is a services contract **with DFO** (domestic procurement): open
  integration, a provenance trail for evidence, or training material.
- **Blockers:** MDA owns the platform IP (first pass). DFO may see no gap to fill.
- **First step:** after ProServices, ask DFO's International Fisheries / IUU program, through the
  DFO public enquiries channel, whether DVD partners need integration support that MDA's contract
  doesn't cover.

### 6. Pacific Islands Forum Fisheries Agency (FFA)
- **Evidence:** FFA's tender archive lists CP16_2425, a "data collection and visualization
  platform" for its Regional MCS Strategy 2024–2029, and a feasibility study for a "centralised
  asset tracking hub" [U] (ffa.int returned 403). Operation Kurukuru 2026 (5–16 October) logged
  over 27,000 satellite detections at the RFSC [U]
  ([Wikipedia](https://en.wikipedia.org/wiki/Operation_Kurukuru)). Operation Tui Moana 2026 used
  the FFA Regional Surveillance Picture and Starboard [U]
  ([FFA](https://www.ffa.int/2026/05/pacific-nations-unite-to-strengthen-fisheries-surveillance-through-operation-tui-moana-2026/)).
  A new RFSC building is estimated at over USD 7.1M [U].
- **Fit:** dashboard and data-platform work suits planetar's stack better than analytics, which
  are saturated (Skylight, Starboard, DVD, the Australia-funded aerial programme).
- **First step:** watch the FFA tender page. If CP16-type work reappears, bid as a small
  platform-build firm.

### 7. Inuit marine monitoring (Nunavut)
- **Evidence:** NTI's Inuit Marine Monitoring Program put its first community AIS receiver near
  Cambridge Bay in 2017. Marine monitors in Kimmirut, Clyde River and Cambridge Bay log vessels
  that AIS misses ([IMMP](https://immp.tunngavik.com/) [U]; sources date from 2017–2019; current
  funding not found). The Coast Guard's 2026 backgrounder stresses "ongoing collaboration with
  Inuit" around the Iqaluit hub.
- **Fit:** strong technically (AIS + camera fusion, self-hosted, community-owned data under
  GPLv3). Budgets are small and grant-funded, and trust comes first. **Scope check:** vessels
  only.
- **First step:** use NTI's public IMMP contact to offer a no-cost demo. A paid pilot comes only
  if NTI asks.

### 8. Development-bank MCS consultancies (Latin America, Caribbean, Pacific)
- **Evidence:** an IDB notice (RG-T4867, Grenada) sought a **consulting firm** to design, procure
  and run a digital fisheries pilot, starting with VMS and electronic-monitoring hardware. It
  closed 2026-07-11 [U]
  ([ConnectAmericas](https://connectamericas.com/node/590254)). World Bank PROPER EOIs are covered
  in the first pass. No ADB match was found.
- **Fit:** low to medium. These calls favour fisheries-MCS track records and hardware
  procurement.
- **First step:** register on the IDB and World Bank consultant portals and set alerts for "MCS"
  and "vessel monitoring". Consider teaming as the software partner of an established MCS
  consultancy.

### 9. PIER71 Smart Port Challenge (Singapore)
- **Evidence:** 10th edition launched 2026-04-22, applications closed 2026-06-15
  ([MPA](https://www.mpa.gov.sg/media-centre/details/10th-smart-port-challenge-expands-support-to-scale-maritime-start-ups)).
  Grants up to SGD 100k for proof-of-concept or pilot and up to SGD 250k for product development;
  an MVP and incorporation are required [U]. Whether foreign companies are eligible is **not
  confirmed**.
- **Fit:** only if a 2027 problem statement asks for port-area vessel situational awareness.
- **First step:** watch pier71.sg for the 2027 call and check whether a Singapore entity is
  required.

### 10. Defence primes through ITB SME credits
- **Evidence:** ISED credits highly valued R&D investments, "including those with small and
  medium-sized businesses", at **5×–9×** ([ITB FAQ](https://www.ised-isde.canada.ca/site/industrial-technological-benefits/en/faqs)).
  The Defence Industrial Strategy (February 2026) promises ITB reform and "stronger incentives
  for direct work with Canadian SMBs" [U]
  ([Gowling](https://gowlingwlg.com/insights-resources/articles/2026/industrial-and-technological-benefits-policy)).
  GDMS-Canada claims 250+ Canadian suppliers [U]
  ([GDMS-C](https://gdmissionsystems.ca/about-us/why-choose-us)). Boeing made a 100% ITB
  commitment on the CAD 10.4B P-8A buy [U]
  ([Naval News](https://www.navalnews.com/naval-news/2022/06/boeing-set-to-offer-p-8a-poseidon-to-canadas-multi-mission-aircraft-project/)).
  Lockheed Martin Canada is the River-class combat-systems integrator; its subcontracts go to
  established firms (Thales, Ultra, CAE, SEA) [U].
- **Blockers:** primes buy proven products, and supplier onboarding takes longer than 9 months.
  Kongsberg Geospatial: no Canadian MDA subcontracting signal beyond the first pass.
- **First step:** low priority. Register on GDMS-Canada's supplier page only once there is a
  measured detection result to show.

### 11–12. Indian Ocean Commission RMIFC and YARIS
- IOC tender COI/SSA/AO/2025/001 renewed licences and support for RMIFC (Madagascar) and RCOC
  (Seychelles). It was EU-funded (Safe Seas Africa), labelled a **"local open tender"**, and
  closed 2025-05-13 [U] ([IOC](https://www.commissionoceanindien.org/?p=66005)).
- YARIS (links more than 160 centres in 19 countries) was built under EU GoGIN. Meetings have
  discussed its "transfer … and continued funding" as GoGIN ends [U]
  ([Expertise France](https://www.expertisefrance.fr/en/projects/gogin-gulf-guinea-inter-regional-network)).
  A sustainability gap like this suits open-source hosting, but no buyer or route exists.
- **First step:** none now. Revisit if planetar gets an Africa partner.

## Routes for a Canadian vendor selling abroad

| Route | What it is | Fits Zax today? | Evidence |
|---|---|---|---|
| **Trade Commissioner Service (TCS)** | Free market intelligence, B2B matchmaking, Canada pavilions (INDOPAC Sydney 2025, Indo Defence Jakarta 2024) | **Yes, the only one usable now.** Register as a TCS client and ask the Australia, Singapore, Philippines and Mexico posts for buyer introductions | [TCS INDOPAC 2025](https://www.deleguescommerciaux.gc.ca/en/trade-events-training/2025/indo-pacific-international-maritime-exposition.html); defence exports contact `tdo-defence@international.gc.ca` [U] |
| **Sell to Canada's own international programmes** | DFO's DVD and GAC's Shared Ocean Fund deliver Canadian tech to partner states | **Yes, indirectly.** A domestic ≤ CAD 40k services contract that reaches export buyers | #5 above |
| **UNGM / UN-system tenders** | FAO, IOTC-type, UNODC tenders. Bids only via the UNGM portal | **Yes.** Basic registration is free | [UNGM 308161](https://www.ungm.org/Public/Notice/308161) |
| **Development-bank procurement** | World Bank, IDB, AfDB, ADB consultant selection by the borrower | Yes for registration; wins need an MCS track record or a teaming partner | #8; first pass #5 |
| **CanExport SMEs** | Up to 50% of export-marketing costs (CAD 10–50k); defence projects prioritised; non-US markets favoured | **No.** Minimum is now **3 FTE and CAD 300k revenue** (2026-27) | [TCS what's new](https://www.tradecommissioner.gc.ca/en/our-solutions/funding-financing-international-business/canexport-smes/new-2026-2027.html) |
| **Canadian Commercial Corporation (IPC, G2G)** | CCC contracts with the foreign government as prime, for a fee | **No.** Aimed at opportunities "exceeding $10M" [U]; precedent is GDMS-C's CAD 24M Portugal P-3C upgrade [U] | [hellodarwin (updated 2026-07-06)](https://hellodarwin.com/business-aid/programs/ccc-international-prime-contractor); ccc.ca returned 403 |
| **Export Development Canada** | Export credit insurance, guarantees, financing | Not researched. Useful only once there is a foreign contract to insure | — |

**Best route now:** domestic contracts with departments that run international programmes
(DFO's DVD), plus free UNGM registration for the IOTC tender, with TCS posts for introductions.
CCC and CanExport become relevant only after revenue and staff exist.

## Not realistic (next 6–9 months), and why

- **New Zealand (MPI, NZDF, NMCC):** Starboard won a cross-government subscription after an
  "extensive international search" (2024-07-12; NZD 14.6M project funding)
  ([NZ Defence](https://www.defence.govt.nz/news/improving-maritime-awareness/)). Budget line
  NZD 4.5M a year to 2049, including Pacific access [U]
  ([NZ Transport doc](https://www.transport.govt.nz/documents-and-publications/download/8974)).
- **Australia, AFMA:** subscribes to Starboard (2022-02-09)
  ([Starboard](https://www.starboardintelligence.com/news-afma-subscription)). Trackwell runs its
  VMS [U]. Its 2025 EM panel tender (AFMA25-26-1) is for hardware [U].
- **Australia, Border Force / Maritime Border Command:** excluded by the scope rule (a
  people-smuggling mission is central). **ASCA/DSTG:** eligibility of foreign firms not confirmed,
  and its P2ISR RFPs suit established defence suppliers [U]. **Pacific Maritime Security Program
  aerial surveillance:** a 10-year aircraft-services tender (closed 2025-03-31) [U].
- **Indonesia (KKP):** Skylight is provided "at no cost" through UNODC
  ([UNODC](https://unodc.org/roseap/en/indonesia/2024/02/fisheries-crime/story.html) [U]). A G2G
  Danish satellite constellation launched 2024 [U].
- **Philippines (NCWC, BFAR, PCG):** already a DVD partner, plus Canadian aerial patrols (2024)
  [U].
- **Mexico, Colombia, Costa Rica, Ecuador, Panama, Peru:** DVD partners (#5). Sell to DFO, not to
  them.
- **Chile (DIRECTEMAR):** a reported USD 300M in-house capability plan, prime-scale [U]
  ([defensa.com](https://www.defensa.com/chile/armada-chile-planea-nuevo-proyecto-satelital-para-proteger-aguas)).
  OceanMind already supplies analysis [U].
- **Argentina (Prefectura):** runs its own "Guardacostas" platform with AI fishing inference [U]
  ([La Capital](https://www.lacapitalmdp.com/custodios-del-mar-argentino-soberania-rescate-y-defensa-de-los-recursos/)).
  The 201-mile line is monitored but foreign vessels there are legal.
- **Singapore Information Fusion Centre:** a navy-hosted liaison centre with its own IRIS system;
  no commercial analytics vendors named [U].
- **Japan and Korea coastguards:** no foreign analytics contracts found. Japan is pursuing
  domestic systems (MHI AIRIS) [U].
- **Gulf states and India (IFC-IOR):** prime- and offset-driven defence markets with local-content
  rules. Not researched further; out of reach for a one-person firm.
- **FISH-i Africa / Stop Illegal Fishing / African MCS bodies:** no buy found. Analysis comes from
  NGOs (TMT) and free tools.
- **Canadian Space Agency:** STDP AO 10 excluded "Earth observation data processing" and closed
  2026-03-13 [U]. The smartEarth Enabler call (due 2026-10-30 [U]) is for universities only; a
  university partner could name Zax, but that is a grant, not a customer.
- **IDEaS:** Persistent Maritime Surface Sensor System has been awarded (page modified
  2025-10-06) ([IDEaS](https://www.canada.ca/en/department-national-defence/programs/defence-ideas/element/competitive-projects/challenges/persistent-maritime-surface-sensor-system.html)).
  Multi-modal AI challenge closed 2026-06-02
  ([SpaceQ](https://spaceq.ca/dnd-issues-6-75m-ideas-challenge-for-multi-modal-ai-to-fuse-space-and-terrestrial-data/)).
  These are grant-like and are tracked in `planetar-grants`.
- **Port authorities (Halifax, Montreal, Prince Rupert):** no RFPs found [U]. Vancouver is covered
  in the first pass.
- **Spire / exactEarth, MDA Space, Kpler:** data owners, not buyers (first pass).

## Before selling anything (adds to the first pass's list)

1. **API auth plus roles** (admin/operator/viewer). Both IOTC and any Coast Guard pilot assume it.
2. **One measured detection number** (planetar-fusion Stage 1 on xView3).
3. **A VMS/NAF ingest adapter**, only if IOTC publishes its tender.
4. **ProServices and UNGM registrations.** Both are free and gate leads #3, #4 and #5.

## Sources (read 2026-10-22 unless tagged [U])

- DND, Coast Guard transition — https://www.canada.ca/en/department-national-defence/campaigns/transition-of-the-canadian-coast-guard-into-national-defence.html
- Coast Guard CAD 816M release, 2026-05-22 — https://www.canada.ca/en/canadian-coast-guard/news/2026/05/minister-mcguinty-announces-816-million-investment-to-strengthen-canadas-maritime-security.html
- Coast Guard backgrounder, 2026-05 — https://www.canada.ca/en/canadian-coast-guard/news/2026/05/delivering-on-the-canadian-coast-guards-expanded-security-responsibilities.html
- Public Safety Great Lakes release, 2026-06 [U] — https://www.canada.ca/en/public-safety-canada/news/2026/06/minister-anandasangaree-announces-investment-to-strengthen-canadas-maritime-security-in-the-great-lakes.html
- GPS World, Zighra Coast Guard pilot, 2024-04-04 — https://www.gpsworld.com/canadian-coast-guard-awards-contract-to-zighra/
- Ocean Supercluster ASOMS, 2025-03-26 — https://oceansupercluster.ca/project/canadas-ocean-supercluster-announces-3-8m-air-sea-ocean-monitoring-system-asoms-project/
- Ocean News, OSC–DND MoU [U] — https://oceannews.com/news/defense/canadas-ocean-supercluster-signs-mou-with-department-of-national-defence-to-advance-marine-sensing/
- IOTC VMS pilot implementation plan, 2025-02-01 — https://iotc.org/sites/default/files/documents/2025/01/Implementation_plan_IOTC_VMS_pilot_Project.pdf
- IOTC VMS key decisions, 2025-03-24 — https://iotc.org/sites/default/files/documents/2025/03/IOTC-2025-CoC22-11_Add3-IOTC_VMS_Pilot_Project_Key_decisions.pdf
- UNGM / FAO GFCM VMS tender 308161 — https://www.ungm.org/Public/Notice/308161
- World Fishing, AFMA–Trackwell [U] — https://www.worldfishing.net/vms-to-help-afma-ensure-compliance/1025197.article
- GAC/Canada in Mexico, DVD Mexico, 2026-07-17 — https://canadainmexico.com/2026/07/minister-anand-meets-with-mexicos-secretary-of-foreign-affairs-roberto-velasco-announces-projects-advancing-canada-mexico-action-plan/
- DFA Philippines, DVD arrangement 2023-10-12 [U] — https://dfa.gov.ph/dfa-news/news-from-our-foreign-service-postsupdate/33492-philippines-and-canada-sign-arrangement-on-the-dark-vessel-detection-system
- TMT, Joint Analytical Cell / Shared Ocean Fund [U] — https://www.tm-tracking.org/post/canada-and-uk-announce-partnership-with-joint-analytical-cell-to-combat-iuu-fishing
- Undercurrent, MDA Indo-Pacific DFO contract 2023 [U] — https://www.undercurrentnews.com/2023/07/04/canadian-firm-to-use-satellites-to-track-indo-pacific-iuu-fishing/
- Operation Kurukuru [U] — https://en.wikipedia.org/wiki/Operation_Kurukuru · FFA Tui Moana 2026 [U] — https://www.ffa.int/2026/05/pacific-nations-unite-to-strengthen-fisheries-surveillance-through-operation-tui-moana-2026/
- NTI IMMP [U] — https://immp.tunngavik.com/
- IDB Grenada RG-T4867 [U] — https://connectamericas.com/node/590254
- MPA, PIER71 SPC 2026 — https://www.mpa.gov.sg/media-centre/details/10th-smart-port-challenge-expands-support-to-scale-maritime-start-ups
- ISED ITB FAQ — https://www.ised-isde.canada.ca/site/industrial-technological-benefits/en/faqs · Gowling on ITB 2026 [U] — https://gowlingwlg.com/insights-resources/articles/2026/industrial-and-technological-benefits-policy
- GDMS-Canada suppliers [U] — https://gdmissionsystems.ca/about-us/why-choose-us · Naval News P-8A ITB [U] — https://www.navalnews.com/naval-news/2022/06/boeing-set-to-offer-p-8a-poseidon-to-canadas-multi-mission-aircraft-project/
- IOC tender COI/SSA/AO/2025/001 [U] — https://www.commissionoceanindien.org/?p=66005 · Expertise France GoGIN [U] — https://www.expertisefrance.fr/en/projects/gogin-gulf-guinea-inter-regional-network
- TCS CanExport SMEs 2026-27 changes — https://www.tradecommissioner.gc.ca/en/our-solutions/funding-financing-international-business/canexport-smes/new-2026-2027.html
- TCS INDOPAC 2025 [U] — https://www.deleguescommerciaux.gc.ca/en/trade-events-training/2025/indo-pacific-international-maritime-exposition.html
- CCC IPC criteria via hellodarwin (updated 2026-07-06) [U] — https://hellodarwin.com/business-aid/programs/ccc-international-prime-contractor · CCC–GDMS Portugal [U] — https://www.ccc.ca/en/announcements/ccc-helps-gdms-canada-win-24-million-contract-with-portugal/
- NZ Defence, Starboard contract, 2024-07-12 — https://www.defence.govt.nz/news/improving-maritime-awareness/ · NZ Transport budget doc [U] — https://www.transport.govt.nz/documents-and-publications/download/8974
- Starboard, AFMA subscription, 2022-02-09 — https://www.starboardintelligence.com/news-afma-subscription
- UNODC Indonesia / Skylight [U] — https://unodc.org/roseap/en/indonesia/2024/02/fisheries-crime/story.html
- defensa.com, Chile Navy satellite project [U] — https://www.defensa.com/chile/armada-chile-planea-nuevo-proyecto-satelital-para-proteger-aguas
- La Capital MdP, Prefectura Guardacostas [U] — https://www.lacapitalmdp.com/custodios-del-mar-argentino-soberania-rescate-y-defensa-de-los-recursos/
- IDEaS Persistent Maritime Surface Sensor System — https://www.canada.ca/en/department-national-defence/programs/defence-ideas/element/competitive-projects/challenges/persistent-maritime-surface-sensor-system.html
- SpaceQ, IDEaS multi-modal AI challenge, 2026-04-24 — https://spaceq.ca/dnd-issues-6-75m-ideas-challenge-for-multi-modal-ai-to-fuse-space-and-terrestrial-data/
