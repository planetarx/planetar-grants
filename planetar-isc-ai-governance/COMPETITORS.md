# COMPETITORS — scan for Q3b "Advance on state of the art" (2026-11-05)

Q3b is mandatory and worth up to 20 points. It needs **named** competing technologies and **direct,
measurable** comparisons (CFP Att. 2). 20 points = "two or more significant improvements … likely to
create competitive advantages … and could define new market spaces". Claims described "in general
terms but not substantiated with specific, measurable evidence" score 0 and fail. Evaluators read
only the proposal text, not links (CFP §3.3.2).

**Source quality:** a one-session web scan. Vendor claims come from vendor pages, product docs or trade
press, and are labelled as such. The Gartner placements come from vendor pages and LinkedIn posts, not
from Gartner. Re-verify every row against a primary source before it goes into Q3b text.

## What SSC says is missing (challenge notice)

"Despite the availability of AI governance solutions from Canadian companies and international
providers, existing offerings typically require significant manual effort … interpreting evolving AI
governance requirements, applying them to specific AI systems, updating controls and assessments, and
identifying their ecosystem-wide impacts." The comparisons below are organised around that gap.

## Market snapshot

- **Gartner's first Magic Quadrant for AI Governance Platforms (2026, 13 vendors; date given as May or
  16 June 2026).** As reported, not seen: Leaders IBM, ServiceNow, Truyo; Challenger Holistic AI;
  Visionaries OneTrust, ModelOp, Airia, Credo AI, Monitaur; Niche SAP, Relyance AI (spelling
  uncertain), Cranium AI, Saidot. Sources:
  [OneTrust](https://onetrust.com/resources/gartner-magic-quadrant-for-ai-governance-platforms-2026-report/),
  [IBM](https://www.ibm.com/de-de/forms/mkt-whitepaper-94641).
- **The common pattern** (all the leaders): an inventory of AI systems → vendor-curated regulatory
  content (EU AI Act, NIST AI RMF, ISO/IEC 42001) → controls attached to use cases → evidence and
  workflow → dashboards.

## Comparison

| Product | From | How requirement content is kept current | Requirement change → affected systems | GC instruments (DADM, AIA, PSD) | Notes |
|---|---|---|---|---|---|
| **NuEnergy.ai Machine Trust Platform** | Ottawa | Not documented publicly | Not documented; 2022: "evolving to also address the need for conformity assessments" | **Integrates the GC AIA**, "customizable" to other standards | **The GC incumbent, and an ISC graduate.** ISC Testing Stream pilots 2019–2022 (RCMP, then PSPC, ISED; over $2.4M in total); ESDC licence 2024-05-03, $1.3M amended to over $3M. "Machine trust index" with red/yellow/green thresholds over privacy, ethics, transparency and bias. Ricochet (investigative, 2024–25) reports that ESDC withheld 232 of 251 pages of the outputs and that there is no public evidence of what the platform achieved. Sources: [Communitech 2022-08-19](https://communitech.ca/technews/ottawa-expands-use-of-nuenergy.ai-trust-platform.html), [ITBusiness (RCMP)](https://itbusiness.ca/?p=120014), [Journal of Cyber Policy (ESDC)](https://journalofcyberpolicy.com/nuenergy-contracts-as-the-third-party-assessor-of-ai-within-canadas-benefits-delivery-modernization), [Ricochet](https://ricochet.media/politics/inside-the-black-box-reshaping-canadas-benefits-system/) |
| **IBM watsonx.governance** + Compliance Accelerators | US | Curated "data-as-a-service" regulatory content ("Compliance Plans" → "Obligations"), described as "regularly updated"; no cadence stated. Content engine = **Credo AI Policy Packs** (2025-04) | Obligations mapped to AI use cases; "automate applicability"; no documented propagation of a text change | None found (EU AI Act, ISO 42001, NIST AI RMF) | Gartner Leader (reported). Sources: [IBM docs](https://ibm-self-serve-assets.github.io/building-blocks-docs/ai-core/trust/compliance-accelerators), [Credo–IBM](https://www.credo.ai/blog/credo-ai-and-ibm-empowering-trustworthy-ai-through-oem-collaboration) |
| **ServiceNow AI Control Tower** | US | "Authority documents", provided "solely for informational and guidance purposes to assist with the initial setup"; policies updated by the customer | Regulatory alerts, change tasks and impact assessments appear **only with the separate GRC: Regulatory Change Management app** | None found (NIST, EU AI Act) | Gartner Leader (reported). Source: [ServiceNow docs](https://www.servicenow.com/docs/r/intelligent-experiences/ai-control-tower/risk-compliance-tab-aict.html) |
| **Credo AI** | US | In-house policy team monitors regulation; Policy Packs are modular and attached to use cases | Rule-based triggers exist; no documented trigger on a regulation change | None found | Gartner Visionary (reported). Sources: [Credo SDK docs](https://docs.sdk.credo.ai/core-concepts/policy-packs/), [policy intelligence](https://www.credo.ai/policy-intelligence) |
| **Saidot** | Finland | A library that "tracks updates" to regulations; admins activate frameworks; policies auto-assigned by system classification | Not documented; a third-party review says timeliness of updates is "not documented publicly" | None found | Knowledge graph linking systems, models, risks and controls; 260+ risks, 620+ controls. Gartner Niche (reported). Source: [rfp.wiki review](https://www.rfp.wiki/artificial-intelligence/ai-governance-platforms/saidot) |
| **Truyo** | US | NIST AI RMF-based assessments | Not documented | None found | Discovery scans of sites and repositories; AWS Marketplace private offer **$250,000 per 12 months**. Gartner Leader (reported). Sources: [Truyo](https://truyo.com/platform/ai-governance/), [AWS](https://aws.amazon.com/marketplace/pp/prodview-abiak4q5mx4tc) |
| **Fairly AI** | Kitchener | Built-in ISO 42001, NIST AI RMF, EU AI Act, financial regulations | Not documented | None found | Model-risk management; three-lines-of-defence approval workflow; continuous monitoring. Sources: [OECD catalogue](https://oecd.ai/en/catalogue/tools/fairly-ai-fairly-end-to-end-ai-governance-platform), [UK DSIT case study](https://www.gov.uk/ai-assurance-techniques/fairly-ai-fairly-end-to-end-ai-governance-platform) |
| **Armilla AI** | Toronto | — | — | None found | Launched 2021 as automated ML testing, validation and monitoring; current product not checked. Source: [BusinessWire 2021](https://www.businesswire.com/news/home/20211021005422/en/Armilla-AI-Launches-ML-Testing-Platform-to-Eliminate-Bias-Other-Bad-Outcomes) |
| **TBS AIA tool** (GC's own) | GC, open source (MIT) | TBS releases new questionnaire versions (v0.8 → v1.0.1); **question names change between versions** | None: a one-system questionnaire; no cross-system view, no reassessment trigger | Is the AIA | 32 of ~38 published AIAs are machine-readable, spread over 5 tool versions (planetar-govern, 2026-11-05) |
| **compliance-trestle** (OSCAL) | CNCF sandbox, open source | — | — | — | **Not a competitor: a reuse candidate for Essential 2C** (NIST OSCAL 1.1.x tooling). Source: [GitHub](https://github.com/oscal-compass/compliance-trestle) |

### The rest of the Gartner list (second pass, 2026-11-05)

| Product | Change tracking | Notes |
|---|---|---|
| **OneTrust AI Governance** + DataGuidance | **Yes, as research:** DataGuidance covers 300+ jurisdictions, "updated daily", with an AI regulation tracker dashboard and a Copilot that answers regulatory questions (2024-10 release) | Model sync from SageMaker, AzureML and Vertex; automation rules on attributes; AI risk assessments mapped to OECD, ALTAI, UK ICO and NIST AI RMF. Gartner Visionary (reported). Source: [OneTrust 2024-10-16](https://www.onetrust.com/news/onetrust-unveils-the-next-generation-of-dataguidance-regulatory-research/) |
| **Holistic AI** | **Yes, as a "regulation tracker"** (2024); a directory listing claims automated mapping of systems to regulations with scored gap analysis | EU AI Act, NIST AI RMF, ISO 42001, NYC LL144 assessments; discovery and inventory. Gartner Challenger (reported). Sources: [techUK case study](https://www.techuk.org/insights/guest-insights/ai-adoption-case-study-learn-how-holistic-ai-s-ai-governance-platform-enables-enterprises-to-adopt-and-scale-ai-confidently-while-regularly-monitoring-risk), [Holistic AI blog](https://www.holisticai.com/blog/5-essential-features-in-ai-governance-software) |
| **ModelOp Center** | Not documented | An "AI system of record": inventory, drag-and-drop approval workflows, a rules engine for controls, audit-ready documentation; sold to the US public sector via Carahsoft. Source: [ModelOp](https://modelop.com/product) |
| **Monitaur** | Not documented | Model inventory, controls library mapped to requirements, evidence capture; drift and bias detection. Source: [Monitaur](https://monitaur.ai/platform) |
| **Airia** | Not documented | AI security and orchestration; governance dashboard aggregating risk scores and compliance status across agents and models. Source: [Airia product sheet 2025-12](https://airia.com/wp-content/uploads/2026/02/Airia_Governance-_A4-December-2025.pdf) |
| **Cranium** | Not documented | AI security: shadow-AI discovery, red-teaming, automated completion of compliance frameworks. Source: [CyberSecTools](https://cybersectools.com/tools/cranium-ai-governance-platform) |

SAP and Relyance AI were not examined.

**What this changes:** "nobody tracks regulatory change" is **false**. OneTrust and Holistic AI sell
regulatory-change research. The defensible distinction is narrower: theirs is a research and news feed
(or a curated mapping) that people then translate into controls. Ours detects the change at clause
level in the authoritative text and computes the affected controls, assessments and systems. That is
the "manual effort … interpreting evolving requirements … ecosystem-wide impacts" SSC names. Claim 1
below must be worded that way, and its measurement must show the computed step.

### Partnering list on the notice

- **ABEN HUB INC.** = AL BATOOL[S] ENERGY HUB INCORPORATED (operating name ABEN HUB), Toronto: a
  renewable-energy design platform with a small NRC-IRAP contribution (2025-11 → 2026-03). **Not an
  AI-governance competitor.** Source: [Open Government grants record](https://search.open.canada.ca/grants/record/nrc-cnrc%2C172-2025-2026-Q3-1035984%2Ccurrent).
- **Xstal Consulting Limited:** nothing found. Check the Corporations Canada registry if it matters.

## Where we can claim an advance (each needs its measurement before it goes in Q3b)

The **significant** candidates (20 points needs two):

1. **Requirement change computed from the authoritative text, not curated by a vendor.** The vendors
   keep their regulatory content current by hand (an in-house policy team, "authority documents", a
   library), with no published cadence. OneTrust and Holistic AI sell change *research* (news,
   trackers), and ServiceNow puts change alerts in a separate product, so people still translate a
   change into controls. We re-read the official text, detect a change at clause level (hash per
   clause), and compute the affected controls and then the affected systems. *Measure:* time from a TBS amendment to flagged
   systems, and the affected-system set's precision and recall on replayed real amendments (DADM has
   four reviews; TBS published the text changes for the 2024–25 review).
2. **Findings with measured confidence, not asserted scores.** The incumbent reports a red/yellow/green
   "trust index"; the leaders report compliance scores. Essential 4C asks for a confidence score or
   certainty measure; ours is calibrated against an external reviewer's labels. *Measure:* reviewer
   agreement and calibration error on a labelled sample.

The **minor** ones (each worth points as a "minor improvement"):

3. **GC instruments built in.** We found no vendor shipping DADM or PSD content; only NuEnergy states
   AIA integration. planetar-govern already has 32 DADM s.6 controls quoted word for word, and decodes
   published AIAs across all five tool versions. *Measure:* controls per instrument; share of published
   AIAs decoded.
4. **Replayable audit.** Any past assessment reproduced exactly from an append-only journal.
   *Measure:* a replay test (byte-identical findings).
5. **Open and portable.** GPLv3, open exchange formats (OSCAL candidate), no runtime dependencies, so
   on-premises or Canadian-hosted without vendor intervention (Essentials 2C and 3A, Additional 1).
   Compare with $250K per year (Truyo list price) or the $3M ESDC licence.

## Cautions

- **Don't disparage a named competitor in the proposal.** State our measured advantage and name the
  comparison product's documented behaviour, not a press critique of it. The Ricochet points are
  context for us, not proposal text.
- **NuEnergy is a likely bidder,** and it has ISC history with this program. Our Q3b has to show what
  we do that a curated-content trust index does not, in numbers.
- **Re-verify every vendor row** against the vendor's current documentation before quoting it; some
  sources are from 2021–2022.
