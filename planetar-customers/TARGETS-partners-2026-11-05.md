# Partner and early-customer targets beyond maritime buyers (2026-11-05)

**Question:** which real organisations could Zax Analytics (one-person Canadian company, Victoria
BC) approach for an early partnership? There are three groups:
1. Publicly known **Palantir customers outside the US**. The pitch is an open, self-hosted second
   system, backup or exit path.
2. **Eurostars Call 12 partner candidates**: European SMEs that could co-apply with a
   Canadian-led project.
3. **Canadian organisations with an AI or data-governance need** that fit the ISC AI-governance
   build (`../planetar-isc-ai-governance/`).

**Snapshot date: 2026-11-05.** The facts were gathered on 2026-11-05 by three parallel web
research passes. Untagged facts were read on the cited page. **[U]** means the fact came from a
search snippet or a secondary source only. "Not found" means a few targeted searches found
nothing. It does not mean the thing does not exist. I re-read three facts on their primary pages
on 2026-11-05:
- the CORDIS record for Trackwell's TrackIUU;
- the BC Ministry of Health Responsible AI Policy Framework page;
- The Deep Dive's article on DND's Palantir licences.

**Nothing was sent; no one was contacted.** Every contact route below is a suggested channel. No
one has checked that it works.

**Scope rules:** no US buyers or partners. Canada first, then Europe and the UK, then the rest of
the world. No buyer or use aimed at tracking people. Policing deployments of Palantir appear only
as market signals, never as targets.

**Builds on, without repeating:** the maritime buyer files in this directory
([`README.md`](README.md), [`CUSTOMERS-research.md`](CUSTOMERS-research.md),
[`CUSTOMERS-canada-intl.md`](CUSTOMERS-canada-intl.md), [`CUSTOMERS-europe.md`](CUSTOMERS-europe.md))
and [`../planetar-brainstorm/10-scan-europe-2026-11-03.md`](../planetar-brainstorm/10-scan-europe-2026-11-03.md),
which has the Eurostars Call 12 dates.

---

## Headline findings

1. **European defence ministries are publicly leaving Palantir, but they want *European*
   replacements.**
   - The Dutch MoD said in June 2026 that a "fully fledged alternative" must exist within about two
     years.
   - Danish Defence is reportedly building Danish alternatives **[U]**.
   - The Bundeswehr ruled Palantir out of its AI cloud on 2026-04-28 and is evaluating Almato,
     Orcrist and ChapsVision, with an award planned by the end of 2026 **[U]**.
   - The objections are data sovereignty and vendor staff inside national data. A GPLv3,
     self-hosted system with no vendor in the loop answers both. A Canadian sole trader still
     fails the "European" test, so in Europe the realistic role is a component under a European
     integrator, not a prime.
2. **NHS England's Federated Data Platform is the loudest exit debate anywhere, and it has a
   date.**
   - The contract is £330M over 7 years: Palantir with Accenture, PwC, NECS and Carnall Farrar.
   - A break clause is reportedly exercisable in early 2027, and two Commons committees urged the
     government to use it **[U]**.
   - The Register (2026-04-20) reports that only 3–4 of 13 core capabilities have been delivered.
   - Politics and NHS assurance (DSPT, DTAC) favour UK suppliers. This is a watch item and a
     possible subcontract, not a direct sale.
3. **Canada's federal Palantir footprint is almost all DND. One piece of it is on Planetar's
   thesis.**
   - DND plans to spend about **$7.4M a year on two Palantir licences**. DND says they support
     **RCAF search and rescue**, and that it "inadvertently omitted" the deal from disclosure (The
     Deep Dive, 2026-07-13, re-read).
   - Palantir is also on a PSPC TBIPS supply arrangement until 2028-07-04, and Carahsoft resells it
     under the GC SLSA **[U]**.
   - No Palantir contract with a Canadian province, bank or other department was found.
4. **There is one strong, low-risk Eurostars partner: Trackwell (Iceland, SME, associated
   country).**
   - In 2019 it coordinated **TrackIUU**, a Horizon 2020 SME Instrument Phase 1 project on
     "predictive identification of IUU fishing" (CORDIS 867166, re-read).
   - It is in two current Horizon projects, MarineGuardian (2025–29) and MeCCAM (2025–29).
   - Its fisheries-monitoring software is used in 11+ countries.
   - Sinay (FR) and eOdyn (FR) are good second partners.
   - Four obvious names are no longer independent SMEs: Vake (KSAT 70%), EOMAP (Fugro), Quiet-Oceans
     (CLS) and Windward (FTV, Israel).
   - Partners from Israel, Italy and Cyprus (and reportedly Greece) have no Call 12 national budget.
5. **The best documented AI-governance pain in Canada is Ontario's, but the warmest buyer is BC.**
   - Ontario's Auditor General ("Use of Artificial Intelligence in the Ontario Government",
     2026-05-12) found that 11 of 20 approved AI Scribe vendors gave no third-party audit or SOC
     report, and 5 gave no threat risk assessment (TRA) or privacy impact assessment (PIA). All 20
     were approved anyway.
   - BC's Ministry of Health framework (updated 2026-09-24) covers AI "procured from vendors" across
     the full lifecycle, for the Ministry, every health authority and BC Shared Health Services.
     Island Health is in Victoria.
   - **Federal crown corporations are probably outside DADM.** DADM scope is FAA s.2 departments.
     Don't sell a DADM-branded tool to EDC, CMHC, BDC or Canada Post.
6. **Two corrections for the ISC bid** (from the governance pass; verify before citing):
   - Ontario's Bill 194 (EDSTA) has no AI regulation yet **[U]**. Pitch the Responsible Use of AI
     Directive (in force 2024-12-01), not "Bill 194 compliance".
   - The DADM amendment dating is unclear. Snippets mention a 2025 change with a 2026-06-24
     transition date **[U]**. Re-read the TBS directive page before citing a date.

---

## Group 1: Palantir customers outside the US (backup / exit-path pitch)

**The common pitch:** "An open, self-hosted second system beside Palantir that you own outright.
It keeps running if a licence, a price or a policy changes. Every fact carries provenance, so you
can audit it. Pay for services, not seats."

**Realism:** for a one-person vendor, almost every direct sale here is **low**. There are three
realistic routes:
- programmes Zax already uses (IDEaS);
- subcontracting through the integrators in the table at the end of this group;
- becoming visible to buyers who are publicly looking for an alternative.

### Canada

| # | Organisation | Why it fits | Source (what it says) | Friction signals | First contact route | Pitch | Realism |
|---|---|---|---|---|---|---|---|
| 1.1 | **DND / RCAF search and rescue** | SAR picture fusion is Planetar's domain, and the buyer is Canadian | [The Deep Dive 2026-07-13](https://thedeepdive.ca/canada-military-palantir-license-deal/) (re-read): ~$7.4M/yr on two Palantir licences; DND says they support RCAF SAR; "inadvertently omitted" from disclosure; products and term not named. [IJF](https://theijf.org/article/defence-department-palantir-licences) (headline only) | Non-disclosure; contrast with the federal "reduce US dependence" push | IDEaS (CH13/CH14 relationship); CANSEC 2027 exhibitors and contacts; CanadaBuys. Ask through IDEaS which directorate owns the SAR licences | "A Canadian-owned, open SAR fusion picture that keeps working if a US licence or policy changes" | **Med.** Canadian, on thesis, and an existing IDEaS relationship. DND rarely buys from a sole vendor without a programme vehicle |
| 1.2 | **CANSOFCOM** | Largest disclosed Canadian Palantir contract, so it is evidence of dependency | [The Deep Dive](https://thedeepdive.ca/canada-spent-46-8-million-on-secret-palantir-contract-for-special-forces-records-show/): W6399-19KF28/001/XL, awarded 2020-03-27, Gotham, sole-source; grew from $14.36M to $44.38M over 12 amendments; $46.8M spent | Secrecy; sole-source | None | — | **Low.** Intelligence use. A signal, not a target |
| 1.3 | **PSPC supply vehicles** (TBIPS, SLSA) | Any department can call up Palantir through these. A competitor needs to be on the same vehicles | [CanadaBuys CW2344624](https://canadabuys.canada.ca/en/tender-opportunities/contract-history/cw2344624-000): TBIPS SA with Palantir Technologies Canada, 2024-01-17 to 2028-07-04. [Carahsoft 2024-01-25](https://www.carahsoft.com/news/palantir-carahsoft-expand-partnership-to-deliver-mission-critical-software-to-canadian-public-sector-2024) **[U]**: sole GC SLSA distributor | Vehicles expire 2028 | Supplier registration on CanadaBuys; target the next TBIPS/SLSA refresh, directly or through a reseller. Ties to ProServices in the README's prerequisites | — | **Med**, as a channel task |
| 1.4 | **Integrity Tool & Mold** (Windsor ON) | A Canadian mid-size manufacturer on Foundry, so a possible commercial reference | Dec 2022 multi-year Foundry release, via mirrors only ([StockTitan](https://www.stocktitan.net/news/PLTR/integrity-tool-mold-selects-palantir-to-support-its-sizgzdv3bj69.html)) **[U]** | None public | Company contact form; WEtech Alliance (Windsor) | "An open second system for plant data at service-company cost" | **Low–med.** Reachable, but off thesis and with no friction |

### UK

| # | Organisation | Why it fits | Source (what it says) | Friction signals | First contact route | Pitch | Realism |
|---|---|---|---|---|---|---|---|
| 1.5 | **NHS England Federated Data Platform** | Most public exit debate. Lock-in and audit are the complaints | [The Register 2026-04-20](https://www.theregister.com/2026/04/20/palantir_nhs_break_clause/): £330M / 7 yr; consortium of Accenture, PwC, NECS and Carnall Farrar; 3–4 of 13 core capabilities delivered; ~half of ~200 trusts live; NHS keeps no software after the subscription ends. [Digital Health 2026-03](https://www.digitalhealth.net/2026/03/government-considers-use-of-break-clause-in-palantir-nhs-contract/) **[U]** | Two select committees urge the break clause (early 2027) **[U]**; ministerial decision expected by Dec 2026 **[U]**; BMA opposition; IQVIA's privacy-enhancing-technology (PET) contract ends 2027-02-15 **[U]** | Via an integrator (see the integrator table); written evidence to a committee inquiry; G-Cloud listing later | "An NHS-hostable open substrate with per-fact provenance: no subscription cliff, and the code stays yours" | **Low.** UK health assurance and UK-supplier politics. Watch the Dec 2026 decision |
| 1.6 | **UK Ministry of Defence** | Large enterprise agreement with a fixed renewal date | [The Register 2026-01-28](https://www.theregister.com/2026/01/28/mod_palantir_deal/): £240.6M, 3 years from 2026-04-01, direct award under the defence and security exemption; Find a Tender 2026/S 000-006344 **[U]** | Direct award without competition; parliamentary questions (PQs) on it **[U]**; ends 2029-03-31 | UK Defence Innovation (formerly DASA) open calls; UK–Canada defence-industry channels | "An open fallback picture for readiness data before the 2029 renewal" | **Low** |
| — | Financial Conduct Authority | Trial named in the select-committee critique **[U]** | [Fintech Global 2026-03-24](https://fintech.global/2026/03/24/fca-hands-palantir-sensitive-data-in-ai-fraud-push/) **[U]** | — | — | — | **Excluded.** Transaction and people surveillance |

### Europe

| # | Organisation | Why it fits | Source (what it says) | Friction signals | First contact route | Pitch | Realism |
|---|---|---|---|---|---|---|---|
| 1.7 | **Netherlands Ministry of Defence** | Official policy to replace Palantir, so the buyer is actively looking | [Euronews 2026-06-05](https://euronews.com/next/2026/06/05/why-are-european-governments-reevaluating-their-agreements-with-us-defence-tech-contractor): Staatssecretaris Boswijk says a "fully fledged alternative" is needed within two years; Palantir in use since 2010. Dutch IT Channel 2026-10-28 **[U]**: sovereign system slips to mid-2028 at the earliest | PvdA, NSC and D66 parliamentary questions; a Volt motion rejected **[U]** | DMO market consultations on TenderNed; NIDV (Dutch defence-industry association), through a Dutch integrator | "The open-source core of your sovereign alternative, owned outright under GPLv3, with no vendor staff in the data" | **Low–med.** Real demand, but "European" is a criterion. Needs a Dutch partner |
| 1.8 | **Danish Defence** | Holds Maven and Foundry; looking for local replacements | Euronews (above); [ing.dk](https://ing.dk/artikel/politiker-og-tekniker-om-dansk-palantir-satsning-deler-vandene-i-ekstrem-grad) **[U]** | Conflicting reports on a further Maven purchase **[U]** | Through the Danish firms building the alternative | as 1.7 | **Low** |
| 1.9 | **Ukraine, Ministry of Economy (humanitarian demining)** | Civilian geospatial fusion; values fit | [Ukrinform](https://ukrinform.net/rubric-society/3835143-ukrainian-economy-ministry-signs-agreement-with-palantir-to-use-ai-in-humanitarian-demining.html) **[U]**: agreement signed 2024-03-03 in London; digitises the National Mine Action Strategy to 2033 | Donor-funded; unclear what happens after the agreement | Donor mine-action programmes; Canada funds Ukrainian mine action through Global Affairs Canada **[U]** | "An open demining data layer that Ukraine owns permanently, fundable by donors" | **Low–med** |
| 1.10 | **NATO / NCIA (Maven Smart System NATO)** | Every ally cites interoperability with it | [DefenseScoop 2025-04-14](https://defensescoop.com/2025/04/14/nato-palantir-maven-smart-system-contract/) **[U]**: finalised 2025-03-25 for Allied Command Operations (ACO) | Value undisclosed | NSPA supplier file (already a README prerequisite); NATO DIANA | — | **Low**. A signal |
| — | Airbus Skywise, BP, Stellantis, Ferrari | Large commercial Foundry users | Airbus extension 2026-02-10 **[U]**; BP 5-yr deal 2024 **[U]**; Stellantis renewal **[U]** | All recently renewed | — | — | **Low.** Note only for their integrators |
| — | Signals, not targets: **Bundeswehr** veto ([cio.de](https://www.cio.de/article/4164117/veto-gegen-palantir-bundeswehr-verbannt-us-software-aus-ki-cloud.html) **[U]**); **Swiss Army** internal report warning of US data access (presented Dec 2024; [Cybernews](https://cybernews.com/tech/swiss-army-palantir/) **[U]**); **Spain**, reported informal no-new-deals instruction for state-controlled companies **[U]**; German state police (Gotham/VeRA) and Danish police POL-INTEL, **excluded as people-tracking**, though their "European alternative" debates feed the same market | | | | | | |

### Elsewhere (no US)

| # | Organisation | Source (what it says) | Friction | Realism |
|---|---|---|---|---|
| 1.11 | **New Zealand Defence Force** | Palantir customer since at least 2012 **[U]**; [NZDF OIA 2026-5868 on Palantir costs](https://www.nzdf.mil.nz/assets/Uploads/DocumentLibrary/OIA-2026-5868-Palantir-costs.pdf) exists (figures not extracted) | The Ombudsman forced disclosure of spending **[U]** | **Low–med.** A small buyer that suits self-hosting. Earlier passes judged the NZ maritime market closed (Starboard plus free Skylight) |
| 1.12 | **Australian Department of Defence** | [Defence Connect 2026-02-17](https://www.defenceconnect.com.au/industry/17697-palantir-secures-7-6-million-defence-contract-to-supply-ict-system-platform): A$7.6M, 1 year, limited tender (AusTender 2026-02-11) | A senator criticised the limited tender **[U]**; Maven used sandboxed **[U]** | **Low** (heavy accreditation) |
| — | SOMPO (JP; co-owns Palantir Japan), Rio Tinto | multi-year deals **[U]** | none | **Very low** |

### Integrators that could subcontract an open-source component

| Integrator | Serves | Source | Note |
|---|---|---|---|
| Accenture, PwC, NECS, Carnall Farrar | NHS FDP consortium | [The Register 2026-04-20](https://www.theregister.com/2026/04/20/palantir_nhs_break_clause/) | If the break clause is used, the consortium needs a successor stack |
| IQVIA | NHS PET contract (£28.0M, 2023-11-28 to 2027-02-15) | Find a Tender 037821-2023 **[U]** | Ends the same quarter as the FDP break |
| Carahsoft Canada | Sole GC SLSA distributor of Palantir; also holds Ontario and Alberta vehicles **[U]** | [Carahsoft 2024-01-25](https://www.carahsoft.com/news/palantir-carahsoft-expand-partnership-to-deliver-mission-critical-software-to-canadian-public-sector-2024) **[U]** | A route to a reseller listing in Canada. Carahsoft is US-headquartered with a Canadian arm. The founder must decide whether that breaks the no-US rule |
| ChapsVision (FR), Almato, Orcrist (DE) | Bundeswehr shortlist **[U]** | cio.de **[U]** | Competitors to Palantir. Could take a maritime-ingest or provenance component |
| Capgemini, Sopra Steria | Airbus Skywise partners **[U]** | Airbus 2019-06 release **[U]** | Low priority |

I found no source tying CGI to Palantir in Canada.

---

## Group 2: Eurostars Call 12 partner candidates

**Rules, from snippets of the Eureka eligibility guidelines** (the official PDF was behind a
Cloudflare check, so treat these as **[U]**; confirm before writing the proposal):
- **Lead and countries:** an innovative SME may lead. The consortium needs ≥2 independent entities
  from ≥2 Eurostars countries, and at least one partner must be from an EU Member State or a
  Horizon-associated country. Canada can lead but cannot satisfy that requirement itself.
- **Budget and term:** SMEs carry ≥50% of the budget, no partner carries more than 70%, the project
  runs at most 36 months, and it must be civil use only.
- **UK and Switzerland count as associated:** the UK since 2024-01-01; Switzerland since
  2025-01-01, per Innosuisse's 2026 funding conditions.
- **Countries with no Call 12 national budget:** Israel, Italy and Cyprus
  ([Hezelburcht](https://hezelburcht.com/en/news/eurostars-call-12-opens-on-17-december-2026-for-international-sme-collaborations/));
  hellodarwin adds Greece and Brussels-Capital **[U]**. Partners there join only if they fund
  themselves.
- **Canadian side:** funded by NRC IRAP. The commonly quoted terms are up to 50% of eligible costs,
  capped at CAD 500k **[U]**. Register as an IRAP client at least 4 weeks before 2027-03-04
  **[U]**.

**Prior Eurostars participation could not be verified for anyone.** The Eureka project database is
behind Cloudflare. The Horizon records below come from CORDIS.

| # | Company | Country | SME? | Why it fits | Source (what it says) | Horizon record (CORDIS) | First contact | Joint-project pitch | Realism |
|---|---|---|---|---|---|---|---|---|---|
| 2.1 | **Trackwell hf** | Iceland (EEA, associated) | CORDIS `sme=true` | Fisheries monitoring (fIMS) for authorities in 11+ countries. Brings VMS data and government customers | [trackwell.com](https://www.trackwell.com/) | **TrackIUU** [867166](https://cordis.europa.eu/project/id/867166) (2019, coordinator, H2020 SME Instrument Phase 1, "predictive identification of IUU fishing"; re-read); MarineGuardian 101212608 (2025–29); MeCCAM 101181571 (2025–29) | trackwell.com contact form; an EEN partnering profile | "Fuse your VMS with Sentinel-1 SAR and AIS to flag fishing vessels that go dark, with per-fact provenance usable as evidence" | **High.** Same problem, already pursued; Horizon-experienced; civilian |
| 2.2 | **Sinay SAS** | France | `sme=true`; ~65–100 staff **[U]** | Maritime data hub: passive acoustics, collision risk, fisheries monitoring. Brings acoustic and AIS data and offshore-wind customers | [sinay.ai](https://sinay.ai/en/) | AIMS 775854 (2017, coordinator); DigiWaves 101289878 (2026–30, fisheries monitoring and surveillance) | [sinay.ai contact page](https://sinay.ai/en/contact-en/) | "Cross-modal hydrophone + AIS + SAR vessel re-identification around offshore-wind sites, with an auditable evidence chain" | **High–med.** Close overlap with planetar-acoustic. May prefer its own platform |
| 2.3 | **eOdyn** | France (Brest) | `sme=true`; small **[U]** | Derives ocean currents from AIS tracks. Deep AIS signal expertise | press on the method **[U]** | AI4COPSEC [101190021](https://cordis.europa.eu/project/id/101190021) (2024–27) | e-odyn.com contact form (site fetch failed); EEN Bretagne | "AIS-kinematics features as a fusion modality, plus an AIS-plausibility (spoofing) check" | **Med–high.** AI4COPSEC also covers migration detection. Keep any joint scope strictly to vessels and environment |
| 2.4 | **Awake.AI Oy** | Finland | `sme=true` | Port and voyage-prediction platform (3,000+ ports). Brings port-call data and port customers | [awake.ai](https://www.awake.ai/) | Six projects incl. iNGENIOUS 957216, ADMIRAL 101104163, eFTI-CONNECT 101318856 (2026) | awake.ai contact page | "Identity-anomaly detection near ports: AIS gaps or identity changes cross-checked against SAR and webcams" | **Med.** Very grant-active, but its focus is logistics |
| 2.5 | **Saidot Oy** | Finland | `sme=true` | AI-governance system of record (EU AI Act, ISO 42001). The AI-governance half of a project | [saidot.ai](https://www.saidot.ai/) | ELISE 951847; AISym4MED 101095387 | saidot.ai intro or demo booking | "EU AI Act-ready governance for a learned fusion model: Planetar's provenance and trace API feed Saidot's record" | **Med.** A good second partner. Not maritime |
| 2.6 | **Skytek Ltd** | Ireland | `sme=true` | Satellite and AI intelligence for marine hull and war-risk insurers. Brings commercial pull | [skytek.com](https://www.skytek.com/) | POLARIS 651823 (2014–15, coordinator) | skytek.com contact page | "Provenance-tracked dark-activity scores for marine underwriting" | **Med.** Old Horizon record; independence unverified |
| 2.7 | **Drift+Noise Polar Services** | Germany (Bremen) | ~8 staff **[U]**; Alfred Wegener Institute (AWI) spin-off | IcySea sea-ice navigation from SAR. A natural Canadian Arctic link | Copernicus Marine use case **[U]**; ESA Polar Route study lead (06/2026–02/2027) **[U]** | none found | icysea.app; EEN Bremen | "Arctic traffic awareness: AIS + Sentinel-1 ship and ice detection for polar shipping safety" | **Med.** Small and civilian. Own site did not resolve |
| 2.8 | **sarmap SA** | Switzerland (associated) | `sme=true` | SAR processing (SARscape) with oil-spill detection | [sarmap.ch](https://www.sarmap.ch/) | STEADY 752363 (coordinator); HERCULES 778360 | contact listed on sarmap.ch; EEN Switzerland | "A calibrated Sentinel-1 chain feeding the learned detector, extended to oil-spill attribution" | **Med.** Strong in SAR, weak in maritime. (Gamma Remote Sensing AG, CH, is a land-focused alternative) |
| 2.9 | **Unseenlabs** | France | likely an SME, ~70 staff **[U]**; VC-backed (check autonomy) | RF geolocation of uncooperative vessels. A unique modality | [unseenlabs.com](https://www.unseenlabs.com/) | none found | [unseenlabs contact page](https://unseenlabs.com/en/contact/) | "A learned RF↔SAR↔AIS association model with open provenance for EEZ and fisheries monitoring" | **Med–low.** A data seller with a defence lean |
| 2.10 | **Aistech Space** | Spain | `sme=true` | Thermal smallsat constellation: a night-time vessel modality | [aistechspace.com](https://aistechspace.com/) | AI4COPSEC 101190021; LEONSEGS 101082493 | contact page on aistechspace.com | "Thermal as a fusion modality" | **Low–med.** Leans towards security |

**Cross-reference:** OceanMind (UK), the #1 target in [`README.md`](README.md), might double as a
UK partner. Its legal form (it is a not-for-profit) and Eurostars eligibility were not checked.

**Excluded:**
- **Not independent SMEs any more:** Vake (KSAT 70%, 2024 **[U]**), EOMAP (Fugro, 2025-02-05
  **[U]**), Quiet-Oceans (part of the CLS group, per its own site).
- **No Call 12 national budget:** Windward (Israel; also owned by FTV), MarineTraffic (Greece),
  Planetek Italia (Italy).
- **Too large in practice:** ICEYE.
- **Also considered, lower:** SATIM (PL, defence), Geollect (UK, no current data), Catchwise (NO,
  on MarineGuardian, not profiled), Lobelia Earth (ES, climate rather than vessels), Ubotica (IE).

**Partner-search tools:**
- [EEN Partnering Opportunities](https://een.ec.europa.eu/partnering-opportunities) has about 5,800
  profiles and lists Canada as a target country. A profile is published through an EEN contact
  point; how a Canadian does that was not verified.
- **No Call 12 brokerage event before 2027-03-04 was found.** Past calls had Eureka/EEN b2match
  brokerage events, so check the Eureka events page and b2match from 2026-12-17.

---

## Group 3: Canadian organisations with an AI / data-governance need

These fit the ISC SSC AI-governance build: an assessor against DADM, AIA, the Policy on Service and
Digital and the GC AI Strategy, built on Planetar provenance. The pitch everywhere is the same
shape: "turn your AI rules into versioned checks, each citing dated evidence, so every approval can
be replayed."

| # | Organisation | Province | Why it fits | Source (what it says) | First contact | Pitch | Realism |
|---|---|---|---|---|---|---|---|
| 3.1 | **BC Ministry of Health + health authorities** (incl. Island Health, Victoria) | BC | New framework covering vendor AI across the lifecycle, with no tooling behind it | [Framework page](https://www2.gov.bc.ca/gov/content/health/practitioner-professional-resources/responsible-artificial-intelligence-policy-framework) (re-read): applies to the Ministry, the health authorities and BC Shared Health Services, incl. AI "procured from vendors"; full lifecycle; updated 2026-09-24. [Framework PDF (June 2026)](https://www2.gov.bc.ca/assets/gov/health/practitioner-pro/responsible_ai_policy_framework_final_2026_06.pdf): continuous monitoring, an accountability matrix with a lead system owner, vendor and system assessment before procurement | The framework's published program inbox (on the page); BC Bid | "Your framework requires monitored, accountable vendor AI. We turn it into an evidence trail per system. Start with one procured tool" | **Med–high.** Local, new, explicit about vendors. Health procurement is slow |
| 3.2 | **Ontario MPBSDP + Supply Ontario** | ON | Owns the Responsible Use of AI Directive. The Auditor General found approvals with no evidence | [Directive](https://www.ontario.ca/page/responsible-use-artificial-intelligence-directive): in force 2024-12-01; risk assessment, monitoring, records, annual reporting. [AG report 2026-05-12](https://www.auditor.on.ca/en/content/specialreports/specialreports/en26/2026_AI_EN.pdf): 11 of 20 AI Scribe vendors gave no audit or SOC report; 5 gave no TRA or PIA; all approved; 10 recommendations, with a follow-up in about 2 years. AI Scribe vendor-of-record refresh opened 2026-01-15 **[U]** | Ontario Tenders Portal; [Supply Ontario three-year outlook](https://www.supplyontario.ca/three-year-outlook/); ontario.ca contact form | "Your Auditor General found approved AI vendors with no evidence on file. We make each Directive requirement a check with dated evidence" | **Med.** Documented pain; out-of-province sole vendor; vendor-of-record gatekeeping |
| 3.3 | **BC Public Service: CSBC Digital Government / OCIO** | BC (Victoria) | Its responsible-AI principles are still a draft, with no assessment process | [Draft principles](https://digital.gov.bc.ca/ai/draft-responsible-use-principles/) (updated 2024-11-26): six principles incl. accountability and monitoring. [Generative-AI policy](https://digital.gov.bc.ca/ai/gen-ai-policy) (2025-05-09): staff use only, no assessment | [BC Digital Marketplace](https://digital.gov.bc.ca/marketplace/) (Code With Us, Sprint With Us; caps of ~C$70k and C$2M are from older sources **[U]**); the program inbox on digital.gov.bc.ca | "When the principles become policy, you'll need evidence each system meets them. Here's an open assessor built in Victoria" | **Med.** Local; no current mandate to buy |
| 3.4 | **Digital Governance Council (DGSI)** | national (Ottawa) | Runs CAN/DGSI 101 validation, so it is a channel or partner | [AIReady validation](https://dgc-cgn.org/product/aiready-validation-to-can-dgsi-1012025/): CAN/DGSI 101 validation or audit for C$250–750; a pass earns a Trustmark | [dgc-cgn.org/contact](https://dgc-cgn.org/contact/); buy a self-assessment of Zax as the way in | "Machine-readable, replayable CAN/DGSI 101 evidence, so your assessors verify faster" | **Med.** Cheap to start; partner terms unknown |
| 3.5 | **City of Toronto** | ON | Public AI Register; systems reviewed against IPC/OHRC principles | [AI Register](https://www.toronto.ca/city-government/data-research-maps/ai-register/): three systems, assessed and monitored with human oversight | City bids portal; the register's feedback link | "Each register entry backed by a replayable record of what was checked, against what, and when" | **Low–med.** No buying office identified |
| 3.6 | **Quebec Ministère de la Cybersécurité et du Numérique** | QC | Most formal provincial regime: ministerial orders and annual AI declarations | [quebec.ca page](https://www.quebec.ca/gouvernement/numerique/intelligence-artificielle-administration-publique/utilisation-responsable-intelligence-artificielle): Arrêté 2024-01, Arrêté 2025-02 (10 principles), guides; updated 2026-07-27 | The program inbox listed on that page; SEAO | "Your 10 principles and annual declaration, as versioned controls with evidence" | **Low–med.** French delivery and a Quebec presence needed. Phase 2 |
| 3.7 | **Asenion (formerly Fairly AI)**, Kitchener | ON | Canadian AI GRC firm focused on the EU AI Act and ISO. A DADM/GC pack would extend it | [fairly.ai](https://www.fairly.ai/): "fast-track to the EU AI Act"; merged with Anch AI to form Asenion **[U]** | Discovery-call link on fairly.ai | "DADM, AIA and Ontario Directive control packs plus a replay journal for your platform. Open source; we integrate" | **Low–med.** May see it as competition |
| 3.8 | **Armilla AI**, Toronto | ON | AI liability insurer, so it needs verifiable evidence for underwriting | [armilla.ai](https://armilla.ai/): affirmative AI liability cover, Lloyd's-backed, broker programme | armilla.ai contact page | "Pre-bind evidence: a replayable compliance record per insured AI system" | **Low.** Worth one conversation |
| 3.9 | **Alberta public bodies (POPA)** | AB | Since 2025-06-11, notice is required when personal information feeds an automated system **[U]** | [Blakes](https://www.blakes.com/insights/alberta-s-new-public-sector-privacy-and-access-to-information-legislation-what-businesses-need-to-k/) **[U]**; OIPC call for an AI law (Aug 2025) **[U]** | Alberta Purchasing Connection | "An automated-system inventory with notice evidence, ready before an Alberta AI law" | **Low.** Watch item |

**Dropped:**
- **No published AI governance found:** WorkSafeBC, ICBC, BC Hydro.
- **No council AI policy found:** City of Vancouver, Edmonton, Calgary.
- **Probably outside DADM, and no AI framework found:** federal crown corporations. BDC is
  advertising for an AVP, Data and AI Governance **[U]**, but it has no DADM obligation.
- **Not a fit:** Private AI (a redaction product).
- **Excluded:** Toronto Police Services Board (policing).

**Events:** FWD50's Ottawa executive cohort (2026-11-09/10) is for public servants only **[U]**.
No 2027 #BCTECH Summit dates were found.

---

## Ranked top 5 (first steps for the founder)

| # | Who | Group | Why first | First step (founder) | Gate |
|---|---|---|---|---|---|
| 1 | **Trackwell hf** (Iceland) | 2 | The cleanest Eurostars partner: an associated country, an SME, already worked on IUU dark-fishing prediction, Horizon-active. Call 12 closes 2027-03-04 | A two-paragraph joint-project note through trackwell.com's contact form. In parallel, register as an IRAP client and publish an EEN partnering profile. Do this before 2026-12-17, when the call opens | IRAP registration ≥4 weeks before close **[U]** |
| 2 | **BC Ministry of Health / Island Health** | 3 | Local; new framework explicitly covers vendor AI; directly reuses the ISC build | Short note to the framework's policy inbox offering a no-cost assessment of one procured AI tool against the framework. Send after the 2026-12-15 TRL gate, so there is a demo to show | ISC TRL gate (2026-12-15) |
| 3 | **DND / RCAF SAR** | 1 | The only Canadian Palantir use on Planetar's thesis; reachable through IDEaS | Ask the IDEaS contact named on the CH13/CH14 submission records which directorate owns the RCAF SAR licences, and whether a sovereign fallback picture fits a future challenge. Frame it as continuity, not replacement | CH13/CH14 outcomes; don't cross-pollinate the two bids' theses |
| 4 | **Sinay or eOdyn** (France) | 2 | A second EU partner strengthens the consortium (acoustic or AIS-kinematics modality) and gives a fallback if Trackwell declines | Contact form at sinay.ai; for eOdyn, go through EEN Bretagne. Same note as #1 | Keep scope to vessels and environment (eOdyn's AI4COPSEC covers migration) |
| 5 | **Digital Governance Council** | 3 | A cheap, concrete way into the Canadian governance channel; it produces a credential for the ISC bid | Buy the AIReady CAN/DGSI 101 self-assessment for Zax/Planetar (C$250–750), then ask about evidence-pack partnering | None (a founder spending decision) |

**Watch, no action yet:**
- **NHS FDP break-clause decision** (expected by Dec 2026 **[U]**). If it is exercised, approach
  the consortium integrators.
- **Dutch MoD sovereign-alternative consultations**, through a Dutch partner.
- **PSPC TBIPS refresh** before 2028-07-04.
- **Ontario AI Scribe vendor-of-record** follow-ups.

## Could not verify

- **Eurostars:** any company's prior Eurostars participation; the official Call 12 eligibility text,
  including the UK's status for Call 12; Canada's Call 12 rate and cap (the NRC page returned 404);
  any Call 12 brokerage date.
- **DND:** the names, start date and term of the RCAF SAR Palantir licences (the IJF article body
  was not retrievable).
- **NHS FDP:** the break-clause date and decision timing (the parliament.uk pages returned 403).
- **Netherlands and Denmark:** the Dutch 2028 slip (source returned 403); Denmark's contract terms
  (one English source).
- **UK MoD:** whether a £750M / 5-year deal exists beyond the £240.6M / 3-year notice.
- **No Palantir contract found** with any Canadian province, bank, CBSA, RCMP or the Coast Guard.
  Health Canada denied any Palantir work in 2020 **[U]**.
- **Ontario EDSTA:** whether any regulation under it imposes AI duties (secondary source only).
- **DADM:** the amendment date and the internal-services transition date.
- **BC Digital Marketplace:** current caps.
- **Partners:** Asenion's public-sector work; the independence of Unseenlabs and Skytek; the
  websites of eOdyn, Geollect and Drift+Noise (fetches failed).

## Status: RESEARCHED, no outreach (2026-11-05)

Every step above is a founder contact. Nothing was sent; no one was contacted.
