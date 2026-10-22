# CHALLENGE — NIWC Pacific CSO "Data and Analytics for Maritime Domain Awareness" (`N66001-26-S-C036`)

> Verified research note, **2026-10-06**. The solicitation text was read in full (text extraction
> of the 9-page PDF, verbatim in [`idea.md`](idea.md)); `§` numbers cite it. Notice metadata on
> SAM.gov and PIEE was read during the procurement scan
> ([`../planetar-brainstorm/08-procurement-scan-2026-10-06.md`](../planetar-brainstorm/08-procurement-scan-2026-10-06.md))
> and not independently re-read. Dated snapshot: the buyer "can cancel this CSO at any time"
> (§5.2), so re-verify on SAM.gov before acting.

## The call in one paragraph

The US Navy's NIWC Pacific is buying **data and analytics** that help it "detect, locate,
identify, and track all maritime vessels", from self-reporting ships to "non-cooperative 'dark
targets' that try to hide" (§2.1). It wants feeds that "plug into and enhance" its existing
SeaVision system, and says twice that it is **not** buying "a new, all-in-one 'Common
Operational Picture' (COP) or standalone display platform" (§1.2, §2.2). The subject is
vessels; nothing in the call concerns identifying or tracking individual people.

## Facts

| Item | Value | Source |
|---|---|---|
| Buyer | Naval Information Warfare Center Pacific (US Navy) | title page |
| Reference | CSO announcement `N66001-26-S-C036` | title page |
| Instrument | Commercial Solutions Opening: FAR-based fixed-price contracts (10 U.S.C. 3458, DFARS 212.70) or Prototype Other Transactions (10 U.S.C. 4022) | §1.1 |
| Issued | 2026-01-08 | title page |
| Briefs "encouraged by" | 2026-02-20 (**passed**) | title page |
| **Final deadline for solution briefs** | **2027-01-07 16:00 Pacific** | title page, §4.1 |
| Value | No total ceiling; "individual awards are not expected to exceed $100M". No minimum stated | §5.2 |
| Awards | "one or more"; "all, some, or none of the submissions" | §5.1, §5.2 |
| Evaluation | Technical Merit and Relevance (equal weight), together "significantly more important than Price/Cost" | §3 |
| Submission | Step-1 solution brief by e-mail to the contracting point of contact named in §4.1, "preferably as a single PDF" | §4.1 |
| Questions | By e-mail to the same contact "at any time" | §6.11 |
| Set-aside | None (PIEE shows set-aside code "N/A") | PIEE page, scan |

## Process (five steps, §1.3 and §4)

1. **Solution brief** — five pages at 12-point, or 15 slides ("a strong recommendation").
2. **Pitch** — virtual, by invitation; "a live product demo is often the best way".
3. **Proposal** — full written technical and price proposal, by invitation.
4. **Negotiation** — technical, price, schedule, award structure, data rights.
5. **Award** — only a signed contract or agreement authorises work.

The buyer can skip steps 2 and 3. A successful Prototype OT can lead to a follow-on production
award "without the use of competitive procedures" (§5.5).

### What the Step-1 brief must contain (§4.1)

1. Title page: company name, address, point of contact, CAGE code "if available", date (not counted against the page limit).
2. Executive summary.
3. Technology concept: the solution, "what makes it innovative", and how it relates to the area of interest.
4. Price: at least a rough-order-of-magnitude price.
5. Schedule: a delivery schedule "for any products that are not available right away. If the solution is available now, please say so."
6. Intellectual property: a description, and "any limits on how we can use that IP".
7. Company viability: "a short overview of your company and your success in the market".

## Requirements (numbered here for mapping; wording condensed from the notice)

| # | Requirement | Strength | Source |
|---|---|---|---|
| R1 | Detect, locate, identify and track maritime vessels, both self-reporting and non-cooperative "dark targets" | Core challenge | §2.1 |
| R2 | Plug into and enhance SeaVision; not a standalone COP or display platform | Stated focus, repeated | §1.2, §2.2 |
| R3 | Deliver all data by an automated machine-to-machine process: AWS S3, RESTful API, or TCP/IP stream | "must" | §2.2 Delivery Mechanism |
| R4 | Support bulk downloads **and** real-time streaming | "must" | §2.2 Delivery Mechanism |
| R5 | The analytical result: "a vessel's position, type, and predicted track" | Minimum technical data | §2.2 Minimum Technical Data |
| R6 | **Source identification**: "all data sources used to generate the analytical result (e.g., a specific SAR image, AIS data feed, or RF signal)" | Minimum technical data | same |
| R7 | **Methodology description** "sufficient for us to understand the methodology, verify its legitimacy, and assess effectiveness during operational use. We do not require proprietary source code." | Minimum technical data | same |
| R8 | Example data sources: AIS, RF, SAR, EO, IR, hyperspectral, coastal radar, acoustic/sonar, uncrewed vehicles, IoT sensors, vessel registry, crowd-sourced tracking, port monitoring | Examples, "not requirements" | §2.3 |
| R9 | Example analytics: vessel classification, fingerprinting, AIS/RF spoofing and dark-target analytics, ship-to-ship transfer alerting, true-position geolocation of spoofers, activity alerts, route prediction, pattern-of-life of vessel behaviour | Examples, "not requirements" | §2.3 |
| R10 | Attributes of interest: resolution, revisit, latency from collection to delivery, processing time, coverage, openness of data formats, ease of integration "via a well-documented API", novelty, AI/ML, **ease of sharing between US agencies and partner nations**, breadth of historical archive, ad-hoc and machine-to-machine requests, technical support, training, **"ability to support multiple security classification levels"** | Evaluation colour | §2.3 |
| R11 | Evaluation weights Technical Merit and Relevance far above price | Evaluation | §3 |

## Eligibility and administration

- **Foreign-owned companies "are welcome to participate"**, provided they can get "all the security clearances, facility approvals, and/or licenses needed to perform the work" (§6.9).
- **SAM.gov registration is required before award** (§6.1), not before the Step-1 brief. Payment needs WAWF registration (§6.2).
- Submissions must be unclassified (§6.3).
- If the award involves Controlled Unclassified Information, NIST SP 800-171 applies (§6.4).
- Teaming is encouraged, and the buyer may itself suggest teaming between selectable companies (§4.4, §6.5). After award it may ask awardees to integrate with each other in a "best-of-breed ecosystem" (§5.3).
- Proprietary material needs the cover-page legend quoted in §6.6.
- Conflicts of interest must be disclosed in the submission (§6.8).

## What the notice does not say (unknowns, as of 2026-10-06)

- SeaVision's ingest interface and accepted formats. The notice gives only the public overview URL.
- How much budget remains, how many awards have been made, and whether briefs sent late in the window are evaluated on a rolling basis. The encouraged-by date passed in February.
- Whether a pre-revenue company can satisfy "success in the market" (§4.1 item 7), and whether a Prototype OT is realistically available to a first-time foreign vendor.
- Data-rights expectations beyond "negotiation of data rights, license agreements" (§4.4).

These are all askable by e-mail under §6.11.

## Not read on a primary source (verify before relying on them)

- SAM.gov registration mechanics for a Canadian company (unique entity identifier, and whether an NCAGE code must be obtained first).
- Export-control and Controlled Goods implications of a Canadian company delivering defence analytics to a US Department of Defense customer.
- Any interaction with the terms of the two IDEaS bids under evaluation (CH13, CH14).

## Sources

- Solicitation PDF `N66001_26_S_C036.pdf`, via the PIEE public notice page (link in [`idea.md`](idea.md)); verbatim text in [`idea.md`](idea.md).
- SAM.gov opportunity page: https://sam.gov/opp/8469e11a72a5431abc33990cb3a63e56/view
- SeaVision overview (linked from the notice, not read for this note): https://info.seavision.volpe.dot.gov/#overview
