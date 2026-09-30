# MINERVA Initiative 2026 — six ISC Challenge Stream calls (research note)

Research note for the opportunities forwarded by D. Huang ([`idea.md`](idea.md) carried two of
the six). Verified against the ISED challenge pages, the CanadaBuys notices, and Canada.ca on
**2026-09-23** and re-verified **2026-09-29**. Every fact below is dated; re-verify before acting.

## At a glance — the six calls

| # | Challenge | Solicitation · CanadaBuys | Published | Closes (14:00 ET) | State 2026-09-29 |
|---|---|---|---|---|---|
| 1 | **Arctic Uncrewed Air System** | `EN578-24ISC4/95` · `cb-409-31548836` | 2026-08-13 | 2026-09-24 | closed — **no-bid** ([`DECISION-no-bid.md`](DECISION-no-bid.md)) |
| 2 | Uncrewed Ground System for Surveillance and Reconnaissance | `cb-380-1799399` | — | 2026-09-10 | closed — no-bid |
| 3 | Intelligence Surveillance and Reconnaissance UAS | *(not captured)* | — | 2026-09-21 | closed — no-bid |
| 4 | Uncrewed Ground System for Tactical Cargo Movement | `EN578-24ISC4/97` · `cb-429-57557756` | 2026-08-24 | 2026-09-21 | closed — no-bid |
| 5 | Uncrewed Air System for Cargo/Munition Drop | `cb-979-47075586` | — | **2026-10-05** | open — no-bid (hardware) |
| 6 | **Uncrewed Aircraft System Deconfliction** | **`EN578-24ISC4/94` · `cb-961-40172327`** | **2026-09-23** | **2026-10-21** | **open — the software call; screened in [`FIT.md`](FIT.md)** |

Canada.ca's MINERVA challenge list (modified 2026-09-10) still showed #6 as "Upcoming" with a
placeholder link on 2026-09-29; the ISED page and CanadaBuys notice went live 2026-09-23.

## Terms common to all six (ISC Call 004)

| Field | Value | Source |
|---|---|---|
| Program | **Innovative Solutions Canada — Challenge Stream**, Call for Proposals 004 (`EN578-24ISC4`) | CanadaBuys `cb-331-17030872` |
| Sponsor | Department of National Defence / Canadian Army (MINERVA Initiative) | ISED pages |
| Mechanism | **Contract** (procurement), not a grant | ISED |
| Phase | **Phase 2 only** (prototype development). Direct entry at Phase 2 is allowed for solutions that "have already proven feasibility using sources of funding outside of the ISC program" | ISED Challenge Stream page; Call 004 |
| TRL | **5–9 inclusive** (Phase 1 would be TRL 1–4) | ISED |
| Award | up to **$500,000 CAD** per contract; ~**5** contracts per challenge; up to **15 months** | ISED |
| Demonstration | travel to **Suffield, Alberta**; kick-off, progress, and final reviews by phone/video | ISED |
| One award rule | "Selected companies are eligible to receive one contract per phase per challenge" | CanadaBuys |
| Enquiries | in writing to `TPSGC.PASIC-APISC.PWGSC@tpsgc-pwgsc.gc.ca`, **≥10 calendar days before close**; answers published as CanadaBuys amendments | ISED |
| Apply | ISC portal, "Challenge Stream Submission Form" (login required) | ISED |

### Eligibility (Call 004)

- For-profit; **incorporated in Canada** (federal or provincial); **≤499 FTE** including affiliates
  (parents and subsidiaries count).
- ≥50 % of annual wages/salaries/fees paid to people working mainly in Canada; ≥50 % of FTEs with
  Canada as ordinary place of work; ≥50 % of senior executives (VP and above) resident in Canada;
  R&D performed in Canada.
- **Zax Analytics passes every test** (D1/C1 in `../planetar-brainstorm/DECISIONS.md`). The
  individual-applicant route used for Ocean Startup / EV / NLnet (D4) is **not** available here.
- Secondary sources state 80 % Canadian content of financial-proposal costs and a Phase-1
  subcontracting cap of one-third of the R&D budget; **the Phase 2 cap is unverified** — read the
  Call 004 solicitation before relying on a teaming structure.

### Evaluation grid (published on the Arctic UAS page; the Deconfliction page states the same 65-of-130 pass mark — confirm per-question text on the portal form)

**Part 1 — mandatory, pass/fail**

| Q | Test | Fail condition |
|---|---|---|
| 1a | Scope: solution addresses **all Essential Outcomes** with scientific/technological basis | out of scope, or any Essential unaddressed |
| 2 | Current TRL stated (dropdown) and justified with R&D evidence: methods, feasibility data, validation, environment | **"TRL 4 or below"**, basic research, or unclear justification |
| 3a | Meets an ISC innovation definition (new; significant modification in new application; improvement over state of the art) | incremental / normal product development |
| 3b | Advance on state of the art — mandatory **and** scored 0/5/12/**20** | no demonstrated advantage |

**Part 2 — point-rated, 130 total, 65 to pass**

| Q | Criterion | Points |
|---|---|---|
| 1b | Additional Outcomes addressed (<50 % = 3, ≥50 % = 6, 100 % = **10**) | 10 |
| 3b | Advance on state of the art (from Part 1) | 20 |
| 4 | S&T risks + mitigations | 10 |
| 5 | Project risks (HR, financial, PM, IP, materials, supply chain) | 10 |
| 6 | Project plan (table; concurrent milestones; **exit TRL**; ≤ max duration) | 20 |
| 7 | Implementation team (table) | 20 |
| 8 | Inclusivity (policies + concrete examples = 10; Indigenous Business Directory / Modern Treaty / CLCA registration = 20) | 20 |
| 9 | Financial controls, tracking, oversight | 10 |
| 10 | Commercialization strategy (prior experience, other funding, investment secured) | 10 |

## Challenge 6 — Uncrewed Aircraft System Deconfliction (verbatim, ISED page modified 2026-09-23)

**Problem statement.** "The proliferation of UAS has led to a situation where it has been
increasingly challenging for the CA staff to plan, deconflict, and control UAS operations in
real-time." The CA lacks digitalized means to manage diverse UAS effectively, creating flight
safety risks without real-time planning and control capabilities.

**Essential (mandatory) outcomes — the proposed solution must:**

1. "Be Windows-based."
2. "Allow a user to create and store flight plans, including radio frequency requirements."
3. "Have a flight plan repository (database) that stores the 4D (3D + time) trajectories and
   spectrum requirements of all accepted flight plans."
4. "Enable integration of supplemental data services such as crewed aircraft flight plans and
   weather."
5. "Generate an optimal 4D flight path for UAS based on specific mission goals and physical
   limits."
6. "Be able to check new flight requests against existing flight plans, airspace constraints
   (no-fly zones) and RF spectrum requests to detect conflicts and resolve them (via set
   priorities or a human decision)."
7. "Generate 4D blocks of deconflicted airspace (a 'tunnel' or a 'box') where a UAS is permitted
   to fly."

**Additional (desired) outcomes — the proposed solution should:**

1. "Analyze real-time data from UASs to prevent collisions and automatically adjust flight paths
   for UASs in controlled airspace."
2. "Check in real-time whether a UAS is following its pre-approved, deconflicted trajectory."
3. "Demonstrate capacity in having its critical components produced and sourced in countries
   within the NATO alliance, NATO Partners or Major Non-NATO Allies."

**Background (shared boilerplate across the six).** "The CA is undergoing a generational
modernization effort to address the evolving nature of technology, the changing character of
conflict, and the unravelling of the geopolitical system" (*Inflection Point 2025*); the
transformation includes "integration of emerging technologies, including artificial intelligence
(AI), machine learning, robotics, autonomous and uncrewed systems." The CA "has purchased foreign
robotics and autonomous systems of varying quality and has identified challenges purchasing
systems that meet operational requirements … and that have stable supply chains." Canada's
Defence Industrial Strategy "emphasizes the need to develop a strong domestic industrial capacity
to produce defence materiel."

**Logistics.** $500,000 max; up to 15 months; ~5 contracts; prototype demonstration at Suffield,
AB; all meetings by phone/video. Portal: ISC challenge id `775c12e0-d217-419d-8d5b-e4007d23c218`.
CanadaBuys `cb-961-40172327`: published 2026-09-23, **no amendments or Q&A as of 2026-09-29**.
Enquiry cut-off: **2026-10-11**.

**Businesses that registered "interest in partnering" on the notice (2026-09-29):** Edgeward,
Moon Vault, HiveRadar. (Edgeward and Moon Vault also registered on the Arctic UAS notice, with
Rozvelt, Immervision Inc., A-Arctic Inc., XACT Engineered Manufacturing Solutions, Creaform.)
Unresearched — names only.

### How the Army describes the problem (context beyond the notice)

- Canadian Army Today, 2026-07-08, quoting LCol D'Arcy Lemay (CALWC Chief of Experimentation
  Services Centre): the challenge is "airspace deconfliction when hundreds, or even thousands, of
  drones share the air with tactical helicopters, and how to integrate with air defence and
  counter-UAS systems to avoid friendly fire." The enabling-technology line "underpins" both the
  C2 and training challenges, with "digital twins" named.
- The Maple Leaf, 2026-09-16: "In late September, at Canadian Forces Base Gagetown, the 4th
  Artillery Regiment (General Support) will host a discussion with industry on uncrewed aircraft
  system deconfliction — identifying where new systems could better manage the airspace shared by
  users across the Canadian Armed Forces." No registration route was published; the event has
  likely passed. 4 Regt (GS) RCA is the Army's surveillance-and-target-acquisition regiment,
  operates the CU-172 Blackjack, and provides aerospace coordination centres to brigade groups
  (Wikipedia — *verify against Canada.ca before citing in a narrative*).
- MINERVA capability objective 3 (Canada.ca, modified 2026-08-27): "enabled and sustained
  systems (command/control integration, training, sustainment, additive manufacturing)."

### Landscape note (unverified beyond the cited pages)

**Kongsberg Geospatial** (Ottawa) sells IRIS Terminal / IRIS AM — "an airspace deconfliction
platform," "real-time calculation of aircraft separation, airspace monitoring alerts" — and
already partners into the Canadian defence market. It is the obvious incumbent for this call.
It is a subsidiary of Kongsberg Gruppen; the ISC ≤499-FTE test counts affiliates, so its
eligibility is an open question — *verify, do not assume*.

## The five hardware calls (summary; rationale in [`DECISION-no-bid.md`](DECISION-no-bid.md))

Each requires, as Essential outcomes, a complete air or ground **vehicle** plus sensor payload,
ground control station, radio, battery/charger, and remote antenna, with environmental, range,
endurance, mass, and Johnson-criteria recognition specifications (Arctic UAS: −40 °C to +40 °C,
55 km/h wind, moderate icing, 20 km radius, 90 min, ≤25 kg, 240-litre stowage, 1,000 ft AGL,
glove-operable GCS). Every one lists, under *Additional* outcomes, a GCS with MGRS position,
orientation, camera aim point, full-motion video, battery state, mission-planning simulation,
GNSS waypoint navigation, and a **TAK battle-management interface**, and a component-origin
attachment naming *Software* as a critical component. The software slot is Additional only.

## MINERVA — what it is

- Canadian Army modernization initiative led by the **Canadian Army Land Warfare Centre**;
  launched late 2025 (Canada.ca: December 2025; Canadian Army Today: September 2025). Three
  working groups: general-purpose UAS; ground and littoral systems; **enabling and supporting
  technologies**. Not a procurement project; an experimentation and integration pathway.
- **Two funding channels by maturity:** IDEaS "supports earlier-stage innovation through
  challenges and experimentation" (True North Precision, Drone Surge; "Breacher" upcoming);
  ISC "supports later-stage development toward validation and procurement" (the six 2026 calls).
- Contact: **`MINERVA.Initiative@forces.gc.ca`** — "Organizations interested in participating
  should review active challenge opportunities through ISC and IDEaS and contact the MINERVA
  team for further information." Events page lists 2026 demos at Valcartier (08-10) and Petawawa
  (08-19) and industry sessions; none on deconfliction.

## Sources

- [ISED — MINERVA Initiative – Uncrewed Aircraft System Deconfliction](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/minerva-initiative-uncrewed-aircraft-system-deconfliction) (modified 2026-09-23)
- [CanadaBuys — `cb-961-40172327` (`EN578-24ISC4/94`)](https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-961-40172327) · [MERX abstract 22785014689](https://www.merx.com/public/supplier/solicitations/notice/22785014689/abstract?origin=0)
- [ISED — MINERVA Initiative – Arctic Uncrewed Air System](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/minerva-initiative-arctic-uncrewed-air-system) (modified 2026-09-15; evaluation grid) · [CanadaBuys `cb-409-31548836`](https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-409-31548836)
- [ISED — UGS Surveillance & Reconnaissance](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/minerva-initiative-uncrewed-ground-system-surveillance-and-reconnaissance) · [ISED — ISR UAS](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/minerva-initiative-intelligence-surveillance-and-reconnaissance-uncrewed-air-system) · [ISED — Cargo/Munition Drop UAS](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/minerva-initiative-uncrewed-air-system-cargomunition-drop) · [CanadaBuys — Tactical Cargo UGS `cb-429-57557756`](https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-429-57557756)
- [ISED — Challenge Stream for innovators](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/challenges) (Phase 1/2, TRL bands, Phase 2 entry) · [CanadaBuys — ISC Call 004 `EN578-24ISC4`](https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-331-17030872) (eligibility) · [ISED — Grant Instructions and Procedures – Call 004](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/grant-instructions-and-procedures-call-004)
- [Canada.ca — MINERVA Initiative](https://www.canada.ca/en/army/services/army-modernization/minerva-initiative.html) (modified 2026-08-27) · [MINERVA innovation challenges](https://www.canada.ca/en/army/services/army-modernization/minerva-initiative/innovation.html) (modified 2026-09-10) · [MINERVA events and working groups](https://www.canada.ca/en/army/services/army-modernization/minerva-initiative/event-working-groups.html) (modified 2026-08-27)
- [The Maple Leaf, 2026-09-16 — From the Arctic to the front line](https://www.canada.ca/en/department-national-defence/maple-leaf/defence/2026/09/from-arctic-to-front-line-army-industry-join-forces-minerva.html)
- [Canadian Army Today, 2026-07-08 — The drone initiative](https://canadianarmytoday.com/the-drone-initiative/) · [Canadian Defence Review, 2026-09-21 — Six MINERVA challenges](https://canadiandefencereview.com/canadian-army-launches-six-minerva-challenges-as-dnd-seeks-autonomous-mine-countermeasures-vessel/)
- [Kongsberg Geospatial — IRIS Terminal](https://www.kongsberggeospatial.com/products/iris-terminal) (landscape only)
- [Wikipedia — 4th Artillery Regiment (General Support), RCA](https://en.wikipedia.org/wiki/4th_Artillery_Regiment_(General_Support),_Royal_Canadian_Artillery) (secondary; verify)
