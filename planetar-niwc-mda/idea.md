# Raw capture — NIWC Pacific CSO N66001-26-S-C036 (verbatim solicitation text)

| Field | Value |
|---|---|
| Buyer | US Navy, Naval Information Warfare Center Pacific (NIWC Pacific), DoDAAC N66001 |
| Reference | CSO announcement N66001-26-S-C036 (SAM.gov solicitation number N6600126SC036) |
| Notice URL | https://sam.gov/opp/8469e11a72a5431abc33990cb3a63e56/view |
| Full solicitation | `N66001_26_S_C036.pdf` (9 pages), the only attachment on the public PIEE notice page: https://piee.eb.mil/sol/xhtml/unauth/search/oppMgmtLink.xhtml?noticeId=N6600126SC036&noticeType=SolicitationNotice |
| Retrieved | 2026-10-06, during the procurement scan ([`../planetar-brainstorm/08-procurement-scan-2026-10-06.md`](../planetar-brainstorm/08-procurement-scan-2026-10-06.md)). PDF downloaded from the PIEE public page with no login and converted with `pdftotext -layout` |

Keep as-is. This is text extraction only: page-break whitespace is as extracted, and the
document's own duplicated section numbers (2.2 / 2.2 / 2.2) are reproduced as published. The
PDF itself is not stored in this Markdown-only repo; re-download it from the PIEE link before
relying on any clause.

---

## Verbatim solicitation text (N66001_26_S_C036.pdf, issued 8 January 2026)

```text
                                 COMMERCIAL SOLUTIONS OPENING (CSO)

                                                          FOR

                               Data and Analytics for Maritime Domain Awareness

CSO ANNOUNCEMENT NUMBER: N66001-26-S-C036

ISSUED BY: Naval Information Warfare Center Pacific (NIWC Pacific)

DATE ISSUED: 8 January 2026

SOLUTION BRIEFS ENCOURAGED BY: 20 February 2026

FINAL DEADLINE FOR SOLUTION BRIEFS: 7 January 2027 at 1600 Pacific Time

ABSTRACT

We are seeking data and analytics to improve our awareness of activity at sea (maritime domain awareness). This
Commercial Solutions Opening (CSO) describes our efficient, five-step competitive process to find and buy
commercial solutions. Successful companies may receive FAR-based, fixed-price commercial contracts or Other
Transaction agreements for prototypes (Prototype OTs). This is a focused announcement for this single topic only.

SECTION 1: OVERVIEW

1.1. Authorities

We may award FAR-based, fixed-price contracts under the authority of 10 U.S.C. 3458, as implemented by Defense
Federal Acquisition Regulation Supplement (DFARS) 212.70, which authorizes the Department of Defense to
acquire innovative commercial products and services through a competitive process.

We may also award Prototype OTs under the authority of 10 U.S.C. 4022.

We will make all awards based on the competitive procedures established in this solicitation.

1.2. Goal

Our goal is to acquire data and analytics to improve our awareness of activity at sea (maritime domain awareness).
We are looking for solutions that help us detect, locate, identify, and track vessels, and we are open to raw data,
processed data, or end-to-end analytics. We are mainly interested in solutions that can plug into and enhance a
system we already use, called SeaVision (https://info.seavision.volpe.dot.gov/#overview). We are not looking to buy
a new, all-in-one “Common Operational Picture” (COP) or standalone display platform.

1.3. Process Summary

We will follow an efficient five-step process:

    •    Step 1: Solution Brief: You submit a brief overview of your solution.

    •    Step 2: Pitch: If invited, you give a virtual pitch.

    •    Step 3: Proposal: If invited, you submit a full written proposal.

    •    Step 4: Negotiation: We will invite companies with selectable submissions to negotiate the final terms of a
         potential award.

    •    Step 5: Award: Following a successful negotiation, we will issue a contract or Prototype OT.

Based on our evaluation, we can skip Step 2 and/or Step 3 if we think those steps are unnecessary.

1.4. Definitions

    •    Commercial Product or Service: See Federal Acquisition Regulation (FAR) 2.101.

    •    Innovative pursuant to 10 U.S.C. 3458(e): (1) any technology, process, or method, including research and
         development, that is new as of the date of submission of a proposal; or (2) any application that is new as of
         the date of submission of a proposal of a technology, process, or method existing as of such date.

    •    Nontraditional Defense Contractor: As defined in 10 U.S.C. 3014, an entity that is not currently
         performing and has not performed, for at least the one-year period preceding the solicitation of sources by
         the Department of Defense for the procurement or transaction, any contract or subcontract for the
         Department of Defense that is subject to full coverage under the cost accounting standards (CAS)
         prescribed pursuant to section 1502 of title 41 and the regulations implementing such section. Small
         businesses are not subject to CAS, so all small businesses are nontraditional defense contractors.

    •    Small Business: See the criteria and size standards in Title 13, Code of Federal Regulations, Part 121 (13
         CFR 121).

    •    Prototype Project pursuant to 10 U.S.C. 4022(e)(5): A project that addresses:

             o     a proof of concept, model, or process, including a business process;

             o     reverse engineering to address obsolescence;

             o     a pilot or novel application of commercial technologies for defense

             o     agile development activity;

             o     the creation, design, development, or demonstration of operational utility; or

             o     any combination of the above.

SECTION 2: AREA OF INTEREST

2.1. Our Challenge

We need to detect, locate, identify, and track all maritime vessels. We need data solutions that can follow all types of
vessels, from cooperative ships that report their location (self-reporting vessels) to non-cooperative "dark
targets" that try to hide. Dark targets may be involved in illegal, unreported and unregulated fishing, illicit drug
trafficking, illegal arms trafficking, terrorism activities, or piracy.

2.2 Focus

We are mainly interested in solutions that can plug into and enhance a system we already use, called SeaVision
(https://info.seavision.volpe.dot.gov/#overview). We are not looking to buy a new, all-in-one “Common Operational
Picture” (COP) or standalone display platform.

2.2. Delivery Mechanism

All data must be delivered via one of the following three automated machine-to-machine processes: AWS S3,
RESTful API, or TCP/IP stream. Your solution must also support bulk downloads and real-time streaming.

2.2. Minimum Technical Data Requirements

We think we will need the following technical data to meet our operational needs:

    •    The Analytical Result: The direct output of the solution (e.g., a vessel's position, type, and predicted track).

    •    Source Identification: A clear identification of all data sources used to generate the analytical result (e.g., a
         specific SAR image, AIS data feed, or RF signal).

    •    Methodology Description: A high-level description of the analytic process or algorithms used. This
         information must be sufficient for us to understand the methodology, verify its legitimacy, and assess
         effectiveness during operational use. We do not require proprietary source code.

2.3. Examples of What We’re Looking For

The lists below are just examples of potential solutions and attributes of interest. They are not requirements. We
encourage you to propose any solution that helps us with our challenge, even if it's not on these lists. We welcome
new and creative solutions.

    •    Example Data Sources:

             o    Automatic Identification System (AIS) data and transponder signals

             o    Radio Frequency (RF) data (internals/externals)

             o    Synthetic Aperture Radar (SAR) data

             o    Electro-Optical (EO) data

             o    Infrared (IR) data

             o    Hyperspectral imagery with automated vessel detection and analytic data

             o    Data from maritime domain awareness sensors and networks

             o    Smart container and cargo tracking systems data

             o    Coastal and maritime radar systems data

             o    Acoustic/sonar detection systems data

             o    Data from Unmanned/Uncrewed Vehicles and surveillance platforms (UxV, UxS)

             o    Internet of Things (IoT) maritime sensors data

             o    Data from machine learning-enhanced detection platforms

             o    Vessel registry data

             o    Vessel prediction algorithms data

             o    Vessel analytics data

        o   Vessel anomaly detection data

        o   Crowd-sourced maritime tracking data

        o   Port and harbor monitoring systems data

•   Example Analytics Functions:

        o   Vessel classification

        o   Automated vessel identification (Fingerprinting)

        o   Anomaly and Deception Detection, including AIS/RF Spoofing analytics, Dark Target analytics,
            and behavioral analytics

        o   Automated alerting on bunkering / ship-to-ship transfer events

        o   Detection and alerting on military radars or other high-risk vessel radars emissions

        o   Geolocation of AIS-spoofing vessel to determine true positions

        o   Dark target identification and broader anomaly detection

        o   Activity-based alerts and behavior classification

        o   Route prediction based on cargo schedules and historical patterns of similar vessels

        o   Pattern-of-life analysis to characterize typical vessel behavior

•   Solution Attributes of Interest:

        o   Resolution

        o   Revisit rates

        o   Collection frequency

        o   Latency from collection to delivery

        o   Data/analytics processing time

        o   Geographic coverage areas

        o   Propriety of data formats

        o   Ease of integrating (e.g., via a well-documented API)

        o   Use of novel technologies and methodologies

        o   Use of advanced analytics, artificial intelligence, and machine learning approaches

        o   Ease of ability to share the data between multiple USG agencies and with U.S. partner nations

        o   Breadth of historical data archive

        o   Ability to handle ad-hoc/on-demand collection requests

        o   Ability to handle machine-to-machine requests

        o   Technical support

             o    User training packages

             o    Ability to support multiple security classification levels

SECTION 3: EVALUATION FACTORS

We will evaluate proposals during Steps 1-3 using the following factors:

    1.   Technical Merit

    2.   Relevance

    3.   Price/Cost

Technical Merit and Relevance are of equal importance to each other. When combined, these technical factors are
significantly more important than Price/Cost.

We will evaluate these factors to the extent appropriate, based on the information requested and provided by the
company at each step. We will notify you if your submission is not selected for further consideration.

SECTION 4: SUBMISSION AND EVALUATION PROCESS (DETAILED)

4.1. Step 1: Solution Brief

    •    Content: Your solution brief should include, at a minimum:

             1.   Title Page (not counted against page limit): Company Name, Address, Point of Contact, CAGE
                  Code (if available), Date.

             2.   Executive Summary: A short, high-level summary of your solution.

             3.   Technology Concept: A description of your solution, what makes it innovative, and how it relates
                  to the Area of Interest.

             4.   Price (Rough Order of Magnitude (ROM) Price or Proposed): You must give us at least a
                  ROM price, which is a high-level estimate of the price or cost. If known, you may give us the
                  proposed price(s).

             5.   Schedule: A rough estimated delivery schedule for any products that are not available right away.
                  If the solution is available now, please say so.

             6.   Intellectual Property (IP): A description of your intellectual property (IP) and an explanation of
                  any limits on how we can use that IP.

             7.   Company Viability: A short overview of your company and your success in the market.

    •    Formatting: Please keep your solution brief to five (5) pages (using 12-point font) or, alternatively, fifteen
         (15) slides. This is a strong recommendation. Please don’t send unnecessarily elaborate brochures. If we
         think your brief is too long, we might have to ask you to shorten and resubmit it before we evaluate.

    •    Submission Instructions and Deadline: Submit your solution brief via e-mail to Bryan Mansfield
         (bryan.f.mansfield.civ@us.navy.mil), preferably as a single “PDF” file. We encourage you to submit by 20
         February 2026. However, you may submit until the final deadline of 7 January 2027 at 1600 Pacific Time.
         If you submit after the final deadline, your submission will be late and we will not consider it.

    •    Result: Based on our evaluation, we may invite you to Step 2 or directly to Step 3 or Step 4.

4.2. Step 2: Pitch

    •    Content: The pitch is a chance to showcase your solution. A live product demo is often the best way to do
         this, but it is not a formal requirement. Our invitation to pitch will include further details (e.g., instructions,
         any additional content, and any of our advanced questions regarding your solution).

    •    Result: Based on our evaluation, we may invite you to Step 3 or directly to Step 4.

4.3. Step 3: Proposal

    •    Content: The full written proposal covers your proposed solution in much greater detail. Our invitation to
         submit a proposal will include further details (e.g., instructions, any additional content, and any of our
         advanced questions regarding your solution). A full written proposal would typically include the following:

             o       Technical Proposal: A detailed description of your proposed products, services, and/or prototype
                     project.

             o       Price/Cost Proposal: A pricing structure that aligns with your commercial practices and the
                     nature of your solution. While fixed-price arrangements are strongly preferred, we are open to
                     discussing other structures for complex prototype projects. Your price/cost proposal should include
                     all information necessary for us to assess your price/cost. For example:

                         ▪    Single or annual purchase: Propose a fixed-price for the defined product/service, or for
                              each year of a multiple year effort.

                         ▪    "Menu" type pricing model (e.g., an indefinite-delivery, indefinite-quantity (IDIQ) type
                              arrangement): If you offer a catalog of products or services that we can order from as
                              needed, please provide a complete price list, including the unit of measure (e.g., price per
                              user, per report, per gigabyte), and any volume discounts.

                         ▪    Development through milestones: If you are proposing a development project, provide
                              the total cost. You must break this cost down into a schedule of "payable milestones,"
                              where we release payments as you complete specific goals. You must detail the
                              completion criteria and cost associated with each milestone. (Note: Traditional defense
                              contractors must also address the 1/3 cost-share requirement.)

    •    Result: Based on our evaluation, we may invite you to Step 4.

4.4. Step 4: Negotiation

    •    Invitation: If we determine that your submission is selectable at any previous step, we may invite you to
         negotiate a contract with us. An invitation to negotiate does not constitute a commitment or guarantee an
         award. If we cannot reach mutual agreement on all terms, we can end the negotiation.

    •    Scope of Negotiation: This is a collaborative step where we work together to refine the terms of a potential
         award. We can negotiate any aspects of your proposal, for example:

             o       Technical: Adjustments to performance characteristics, features, or data formats to better align
                     with our requirements.

             o       Price/Cost: Finalization of the pricing structure, including the price list/catalog, unit prices,
                     volume discounts, cost-sharing arrangements, payable milestone, schedules and other related
                     terms. For FAR-based contracts, this negotiation is the basis for our Contracting Officer's final
                     determination that the agreed-upon price is fair and reasonable.

             o   Schedule: Refinement of the delivery schedule, period of performance, and key milestones.

             o   Award Structure: Final determination of the most appropriate award instrument. This may
                 include:

                     ▪    A FAR-based fixed-price contract type (e.g., stand-alone Firm-Fixed-Price (FFP)
                          contract, Indefinite-Delivery, Indefinite-Quantity (IDIQ) contract, or Purchase Order)

                     ▪    A Prototype OT

             o   Terms and Conditions: Negotiation of data rights, license agreements, payment terms, and other
                 relevant contractual terms.

             o   Teaming Opportunities: We may identify and share perceived teaming opportunities with or
                 between companies that we have determined selectable. Any such suggestion is for the company's
                 consideration only and is not a mandate. Companies are solely responsible for initiating,
                 negotiating, and formalizing any new teaming arrangements.

    •   Process: Our warranted Contracting Officer (for FAR-based contracts) or Agreements Officer (for
        Prototype OTs) will lead the negotiation.

    •   Result: After a successful negotiation, we may issue a FAR-based contract award or a Prototype OT.

4.5. Step 5: Award

    •   Award Decision: The final award decision is at our sole discretion.

    •   Execution: Your award is official only when it is signed by our authorized Contracting Officer or
        Agreements Officer. Do not begin work, incur costs, or assume you have an award based on any other
        communication. The signed award is the only thing that authorizes you to start.

SECTION 5: INFORMATION ABOUT POTENTIAL AWARDS

5.1. Award Types and Structure

We plan to issue one or more FAR-based contracts or Prototype OTs from this competition. We will determine the
specific award instrument and structure during each negotiation based on the nature of the proposed solution and
Government requirements. All FAR-based awards will be fixed-price in nature, and may include instruments such as
stand-alone FFP contracts, purchase orders under FAR Part 13, or IDIQ contracts under FAR Part 16.5 against which
fixed-price delivery or task orders may be placed.

5.2. Other Award Notes

    •   Submission of a solution brief, pitch, or proposal does not guarantee an award.

    •   We can cancel this CSO at any time.

    •   We can award to all, some, or none of the submissions received.

    •   Awards may vary widely in scope, duration, and price/cost.

    •   We have not established a total ceiling for this solicitation. However, at this time, individual awards are not
        expected to exceed $100M in value.

5.3. Technology Integration and Future Enhancements

Our strategy is to foster a “best-of-breed” ecosystem. After award, we may encourage integration efforts between
awardees of this CSO or with other Government-selected technology providers. For example, we might encourage a
company with a great analytics platform to integrate a data feed from a different awardee. If necessary, we would
negotiate the details and cost with you separately and capture it in writing (e.g., modification to existing agreement
or a new order).

5.4. Iterative Prototyping

Prototype OTs awarded under this CSO will allow for an iterative development process. This approach allows us to,
by mutual agreement, modify the work being performed to adapt or modify the technology to meet evolving
Government requirements or new, discrete mission sets discovered during the prototyping effort.

5.5. Potential for Follow-On Production

Upon the successful completion of a Prototype OT, we may award a follow-on production contract or transaction
without the use of competitive procedures. 10 U.S.C. 4022(f) allows for this, and this document serves as the
required official notice. We will also state this possibility in any Prototype OT.

5.6 Successful Completion of Prototype OT

A Prototype OT is complete upon the written determination of the appropriate approving official (Agreement
Officer) for the matter in question that efforts conducted under a Prototype OT: (1) met the key technical goals of a
project; (2) satisfied success metrics incorporated into the Prototype OT; or (3) accomplished a particularly
favorable or unexpected result that justifies the transition to production. Furthermore, successful completion can
occur prior to the conclusion of a prototype project to allow us to transition any aspect of the prototype project
determined to provide utility into production while other aspects of the prototype project have yet to be completed.
If we award a Prototype OT, it will describe the criteria for successful completion.

SECTION 6: GENERAL INFORMATION

6.1. System for Award Management (SAM)

Before we can give you an award, you must be registered in the System for Award Management (SAM) at sam.gov.
We must also determine that you are a responsible party, which means you are not currently debarred, suspended, or
otherwise ineligible for award.

6.2. Wide Area Workflow (WAWF) Registration

We pay through the WAWF system, so you will need to register in WAWF to get paid for performance.

6.3. Security

All submissions you send us must be unclassified.

6.4. Cybersecurity

Awards may require the handling of sensitive but unclassified government data (known as Controlled Unclassified
Information (CUI)). If so, you must meet specific cybersecurity standards required by Department of War
regulations (like NIST Special Publication (SP) 800-171). We can finalize these requirements with you during
negotiations.

6.5. Teaming Arrangements

We encourage you to team up with other companies if it leads to a better or more efficient solution. For example, a
data analytics company could serve as a prime and team up with other companies that provide data feeds. This is just
an example, not a requirement. You are free to propose any team structure you think is best.

6.6. Protection of Proprietary Data

If your submission contains data that is not to be disclosed to the public for any purpose or used by the Government
except for evaluation purposes, your submission's cover page must include the following legal notice: “This [select
one: solution brief, pitch, or proposal] includes data that shall not be disclosed outside the Government, except to
non-Government personnel for evaluation purposes, and shall not be duplicated, used, or disclosed -- in whole or in
part -- for any purpose other than to evaluate this submission. If, however, an agreement is awarded to this
Company as a result of -- or in connection with – the submission of this data, the Government shall have the right to
duplicate, use, or disclose the data to the extent agreed upon by both parties in the resulting agreement. This
restriction does not limit the Government's right to use the information contained in this data if it is obtained from
another source without restriction. The data subject to this restriction are contained in sheets [insert numbers or
other identification of sheets]”

6.7. Comptroller General Access to Records

Please be aware of a specific rule for large Other Transaction (OT) agreements. By law (10 U.S.C. 4022(l)), for any
OT agreement that provides for payments in a total amount in excess of $5,000,000, the Comptroller General of the
United States shall have the right to examine the records of any party to the agreement or any entity that participates
in the performance of the agreement.

6.8. Procurement Integrity and Conflict of Interest

You are required to disclose any and all relevant facts that may give rise to an actual or potential Conflict of Interest
(COI), or even the appearance of a COI, in your submission. We will review all submissions for COIs. If we find a
COI that cannot be adequately avoided or mitigated, we may have to reject your submission.

6.9. Participation by Foreign-Owned Entities

Companies owned by foreign entities are welcome to participate. However, to receive an award, you must be able to
get all the security clearances, facility approvals, and/or licenses needed to perform the work.

6.10. Submission Handling

We will not return your submission. We will keep one electronic copy for our official records and destroy any others.
If you want written confirmation that extra copies were destroyed, you must request it within 5 days of being
notified that your solution was not selected.

6.11. Questions If you have any questions, please email Bryan Mansfield (bryan.f.mansfield.civ@us.navy.mil) at
any time.
```
