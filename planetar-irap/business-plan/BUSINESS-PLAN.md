# Zax Analytics — Business Plan

**Prepared for:** NRC IRAP (Industrial Technology Advisor engagement)
**Company:** Zax Analytics, Victoria, British Columbia, Canada
**Product:** *planetar* — a learned cross-modal AI fusion model for maritime domain awareness
**Date:** 2026-06-29 · **Draft v0.1** · ⏸️ **PARKED — IRAP on hold until cash flow (see `../DECISION-hold.md`)**

> **Provenance note.** Technical, market, and financial claims in this plan trace to the
> company's existing engineering repositories, peer-reviewed publications, and the submitted
> IDEaS CFP6 Challenge 13 proposal. Items marked **`[CONFIRM]`** require the founder's
> current operating figures and are placeholders until supplied. Both background patents are
> referenced as **named-inventor, Salesforce-assigned background IP** — never as owned by the
> applicant.

---

## 1. Executive summary

Zax Analytics is an **incorporated, for-profit Canadian technology company** (Victoria, BC;
incorporated ~2015) building **planetar** — a **learned cross-modal AI fusion model** for
maritime domain awareness. planetar encodes six heterogeneous data streams (AIS, SAR, EO,
passive acoustic, RF, and textual maritime reports) into a shared spatiotemporal embedding
that resolves a single vessel's observations to one **calibrated, uncertainty-scored,
explainable identity — even when that vessel's AIS beacon is dark.** "Dark vessels" (AIS-off)
are the signature of illegal fishing, sanctions evasion, ship-to-ship transfers, and Arctic
sovereignty incursions, and are a stated capability gap for the Canadian Armed Forces.

The company has **already built the deployable substrate** the model runs on — a real-time,
provenance-tracked data fabric, an entity-resolution graph, four per-modality detectors, and
an analyst shell — as **~13,000 lines of open-source code across nine repositories**. The
**remaining R&D is the learned fusion model itself**, currently **TRL 2**, with a credible
path to **TRL 3 and beyond**. This is exactly the kind of deep-learning R&D NRC IRAP exists to
fund, and it lands squarely in **two of IRAP's priority streams at once**:

- **AI Assist** — the model is a **deep-learning** system (self-supervised cross-modal
  association with propagated uncertainty and conformal calibration).
- **Defence Industry Assist (DI Assist)** — the application is **dual-use surveillance**
  directly addressing CAF maritime-domain-awareness needs; the company has already filed a
  competitive **IDEaS Challenge 13** bid with DND.

**The ask.** IRAP support (cost-shared contribution toward technical-staff salaries) to
advance the planetar fusion model from prototype toward a commercial, dual-use product, with a
phased relationship: a small first project to establish delivery, scaling to a Core
AI/DI-Assist project. Exact scope and budget to be shaped with the assigned ITA; the company
brings a working substrate, a published R&D track record, and a filed DND proposal as evidence
of execution capacity.

---

## 2. Company & management

### 2.1 The company

- **Legal entity:** Zax Analytics — **incorporated for-profit Canadian corporation since
  ~2015** (clears IRAP's structure requirement; sole props / partnerships / LLCs are
  ineligible — Zax Analytics is not one of these).
- **Location & status:** Victoria, BC; Canadian-owned and -controlled; **DUNS number in
  progress** (useful for defence/government and US-facing procurement).
- **Current operations:** an R&D-stage company. Its technical work spans AI for structural
  biology, scientific-literature linking, and the planetar maritime platform.
- **Pre-revenue.** Zax Analytics currently has **no revenue and no active revenue lines** — it
  is a founder-led R&D company building toward its first commercial product (planetar). This
  is a normal profile for an early IRAP applicant, but it has direct consequences for how a
  contribution is structured (see §8 — the working-capital and payroll mechanics are the
  single most important thing to work through with the ITA).
- **A ~10-year incorporated history** is still a real asset for the capacity assessment — it
  shows a stable, properly-administered corporate vehicle able to hold a contribution
  agreement and manage CRA/payroll obligations — even though the company is pre-revenue.

### 2.2 The founder

**Steven Randolph Ness, PhD** — Computer Science, University of Victoria (2013; thesis *The
Orchive*, supervised by George Tzanetakis, founder of Marsyas). Canadian citizen.

- **Research standing:** h-index 15, ~1,300 citations, i10-index 21 (per applicant).
- **Directly relevant R&D track record** (the evidence the proposed model is achievable):
  - **Semi-supervised deep learning on continuous hydrophone archives** — Sattar, Driessen,
    Tzanetakis, Ness, Page (IEEE PacRim 2011): **95% accuracy on NEPTUNE Canada / Ocean
    Networks Canada operational hydrophone data**. A public, peer-reviewed bond to Canada's
    national ocean-observatory infrastructure.
  - **ORCA-SLANG** (Interspeech 2021) — multi-stage **semi-supervised deep learning** at
    archive scale.
  - **Auditory sparse coding** with Google Research co-authors (Walters, Lyon — the CARFAC
    cochlear-model lineage), and a body of fusion/classification work.
- **Industry & IP:** Salesforce (to 2021); **named inventor on US 10,936,582 B2 (2021,
  "Integrated entity view across distributed systems") and US 11,442,952 B2 (2022)** — both
  **Salesforce-assigned background IP**. The entity-resolution architecture from that work is
  implemented twice in the company's own code (the doibio POC and the shipping
  `planetar-ontology`); the **new fusion model is novel, separately patentable foreground IP.**

### 2.3 The solo-founder capacity question (answered directly)

IRAP's central concern for a single-founder company is execution capacity. planetar is better
positioned than most early-stage applicants:

- **A decade-old incorporated company** with operating history (not a brand-new shell).
- **A working, shipped software substrate** — ~13k LOC, nine repos, tests passing,
  open-sourced and audit-tagged — proving the founder ships production systems, not slideware.
- **A filed, competitive DND IDEaS bid** — independent evidence the technology maps to a
  real government capability need.
- **A published, peer-reviewed R&D record** in exactly the methodology the project requires.

**This is a single-founder project.** The founder *is* the technical hire; there are no other
employees and no near-term hiring planned. The single-threaded-founder concern is therefore
met not by pointing to a team but by the evidence above — a decade-old company, a shipped and
tested software substrate, a filed competitive DND bid, and a directly-relevant published R&D
record. Named **subcontractors** for discrete components remain available if a specific piece
warrants it (IRAP funds up to 50% of subcontract costs), but the base case is solo execution.

---

## 3. Technology & product

### 3.1 What planetar is

A **learned cross-modal fusion model** for maritime domain awareness. The flagship capability
is **dark-vessel detection**: when a vessel disables its AIS transponder it disappears from
the default maritime picture; planetar re-identifies it from the modalities that *persist*
after the beacon goes dark — SAR, EO, acoustic, RF, text — and returns a single calibrated,
explainable identity with a human analyst in the loop.

The six modalities mirror the way modern maritime ISR actually arrives — AIS (kinematic +
text), SAR (Sentinel-1), EO (electro-optical), passive acoustic (hydrophone), RF emissions,
and textual reports/notices-to-mariners/OSINT.

### 3.2 Already built (the deployable substrate) vs. the R&D

**Built — TRL 3–4, shipped as open-source code at ~13k LOC / 9 repos:**

| Layer | Service | What it does |
|---|---|---|
| Bus | `planetar-broker` (C, ~1.2k LOC) | Real-time provenance-tracked data fabric; **SHM p50 80–140 ns / p99 400–900 ns**; append-only WAL with CRC32 |
| Envelope | `zmesg` (C, ~260 LOC) | Typed binary message format; UUIDv7, ns timestamps, full provenance chain |
| Ingest: AIS | `planetar-ais` (Node) | Live Victoria AIS → per-vessel channels |
| Detector: SAR | `planetar-sat` (Python, 1,583 LOC) | Sentinel-1 → CFAR ship detection → tracking |
| Detector: EO | `planetar-eo` (Python, 1,786 LOC) | Public webcams → YOLO11 vessel detection |
| Detector: Acoustic | `planetar-acoustic` (Python, 2,621 LOC) | Hydrophone → CAR-FAC cochlear model → classifier |
| Entity graph | `planetar-ontology` (TS, 2,323 LOC, 30 tests) | Identity resolution + merge incl. dark-vessel kinematic re-ID |
| Data model | `planetar-registry` (JS, 710 LOC) | Canonical-schema codegen |
| Shell | `planetar-ui` (React 19 / TS) | Explainable analyst decision surface |

**The R&D — TRL 2 today, the IRAP-fundable work:** the **learned cross-modal fusion model** —
per-modality encoders → shared embedding → **self-supervised association head** (using
AIS-on co-occurrence as a free training signal) → **propagated uncertainty + conformal
calibration** → re-identification of AIS-off vessels, with **native explainability** (attention
over modalities + click-through causal provenance). Plus the new **text** and **RF** encoders.

> **The substrate is done; the science is the model.** The research question is not "can this
> be built" — it is "can the cross-modal dark-vessel head be trained on the existing spine to
> produce calibrated, explainable outputs on public data." That is a well-scoped, fundable
> advance, de-risked by everything already shipped.

---

## 4. The R&D project (for the ITA / AI Assist / DI Assist)

### 4.1 The innovation (why it's novel R&D, not integration)

The key insight: **an intermittent strong identifier (AIS) self-supervises the rest.** During
AIS-on periods, a broadcasting vessel's identity *labels for free* the concurrent
SAR/EO/acoustic/RF/text observations in its space-time neighbourhood. The model learns the
cross-modal association from this signal, then applies it to re-identify AIS-off vessels. This
**dissolves the scarce-label barrier** that blocks supervised maritime fusion and is, to the
company's knowledge, novel. It generalizes ("intermittent strong identifier self-supervises
the rest" transfers to Arctic, airborne, and land/edge multi-domain settings).

### 4.2 Why it fits both IRAP priority streams

- **AI Assist (deep learning):** self-supervised contrastive / joint-embedding learning
  (CLIP / I-JEPA / set-transformer lineage), evidential uncertainty heads, conformal
  calibration — core deep-learning R&D, plus the testing/validation AI Assist targets.
- **DI Assist (defence & dual-use):** maritime **surveillance** addressing **CAF**
  domain-awareness needs; genuinely dual-use (same model serves commercial maritime analytics
  and defence). The **filed IDEaS CH13 bid** is direct evidence of the CAF capability pull
  that DI Assist looks for.

### 4.3 TRL trajectory & indicative milestones

TRL 2 → 3 (and onward). The IDEaS proposal scopes the model work as six internal milestones
(adaptable for an IRAP project plan):

| Phase | Work |
|---|---|
| Substrate + text/RF ingest hardening | Promote RF stub to real; add text ingest |
| Per-modality encoders → shared embedding | Encoders + AIS co-occurrence training set |
| Self-supervised fusion training | The primary R&D — train the association model |
| Uncertainty + conformal calibration; dark-vessel eval | Calibrated, evaluated re-ID |
| Explainable + human-in-the-loop surface | Operator-trust decision surface |
| Integrated demo + live deployment | End-to-end demonstrable system |

> The specific IRAP project will be a scoped slice of this, shaped with the ITA. **`[CONFIRM:
> exact IRAP project scope & budget to propose.]`**

---

## 5. Market & opportunity

planetar is deliberately **dual-use**, giving three reinforcing market paths:

### 5.1 Defence & maritime domain awareness (beachhead)

- **Buyer:** DND/CAF and allied (NATO / Five-Eyes) maritime forces; aligned to the DND/CAF AI
  Strategy and Force Capability Plan priorities for ISR and C2.
- **Entry:** the filed **IDEaS CFP6 Challenge 13** bid is the first wedge; **DI Assist** is the
  R&D-funding complement. Positioning is an **"Anduril-shaped" defence company** with maritime
  domain awareness as the beachhead, then expansion (maritime → land/ISR → space/RF → allied
  MDA).

### 5.2 Commercial maritime (dual-use)

High-trust commercial buyers for whom provenance and auditability are worth a premium: **port
security, fisheries enforcement, marine insurance, and sanctions / dark-vessel compliance.**
These share the exact capability (resolve a vessel's identity from heterogeneous, intermittent
signals) and validate the technology outside a single government buyer.

### 5.3 Provenance-native data marketplace (adjacent venture)

The same provenance-native substrate underpins **planetar-market** — a data marketplace where
every listing ships with verifiable provenance and a machine-readable (W3C ODRL) license,
seeded by the company's own maritime data. This monetizes the substrate's per-message
provenance and entity-graph metering as a second, software-margin business line. (Adjacent;
not the IRAP project, but evidence the platform has commercial legs beyond defence.)

---

## 6. Competition & moat

The defensible position is a **real-time entity-resolution layer that incumbents are
architecturally locked out of**, on top of a genuinely novel fusion model:

- **Earned secret.** The founder worked on Salesforce's "Magic Bus" + Canonical Data
  Architecture for Customer 360 — saw it fail to be real-time at the largest possible scale,
  and built the real-time version. Non-copyable credibility.
- **Architecture lock-out (counter-positioning vs. Palantir).** Foundry/Gotham's ontology
  sits on batch semantics; making it real-time is a breaking change to their product and
  customer base — they *won't*, not can't. Against funded startups, the moat is the
  **integrated vertical + head start** (bus + envelope + ontology + five detectors + shell,
  co-designed, plus a filed defence bid).
- **Ontology as system-of-record** (defence customers don't rip these out), a **dark-vessel
  re-ID data flywheel** (each confirmed re-ID is a labeled example — *designed in, small at
  this stage*), and an **accreditation-readiness** head start (a time moat in defence).
- **IP:** the new fusion model is novel, separately patentable foreground IP; the two
  background patents (named-inventor, Salesforce-assigned) establish an entity-resolution
  track record but are *not* owned by the company.

---

## 7. Commercialization plan

- **Near term (the IRAP project window):** advance the fusion model to a demonstrable,
  calibrated dark-vessel capability on public data; stand up a live demonstration. Pursue the
  IDEaS evaluation outcome in parallel.
- **Design partners:** land additional non-DND maritime design partners (port authority,
  Transport Canada, a fisheries body) to prove modality-onboarding speed and seed a second
  data corpus — blunting single-buyer risk.
- **Revenue paths:** (1) defence contracts / programs; (2) commercial maritime
  subscriptions/licenses for provenance-sensitive buyers; (3) data-marketplace take-rate.
- **Capital strategy:** the venture follow-on is a **raise on deliverables (late 2026 /
  early 2027)** — the live dark-vessel demo is the headline proof point; warm investors now.
  IRAP (and IDEaS) provide **non-dilutive runway** that de-risks the round and improves terms.
- **Benefit-to-Canada / commercialization-in-Canada** is clean: Canadian company, Canadian IP,
  Canadian jobs, sovereign capability.

---

## 8. Financials

> The cost model below is **anchored to the submitted IDEaS CH13 budget** (a real, costed
> 6-month plan). The defining financial fact is that **Zax Analytics is pre-revenue with no
> payroll yet** — which makes the *mechanics* of an IRAP salary contribution the central
> thing to solve with the ITA, ahead of any number.

### 8.1 Cost model (from the costed IDEaS plan)

- **Labour rate:** **$140/hr fully-loaded** (PhD CS/ML founder; below the ~$200/hr
  top-of-market) — a defensible technical-salary basis for an IRAP wage-subsidy calculation.
- **6-month reference project:** **$157,924** total — labour $129,500 (925 hrs), cloud/GPU
  compute $18,000 (bottom-up modeled + contingency), software $1,500, datasets $1,000,
  one dev/training laptop $7,924.
- **Compute** is modeled bottom-up (Sentinel-1 fetches free via Copernicus; detector
  fine-tunes on A10/L4-class GPUs; live hosting) — defensible under audit.

### 8.2 The pre-revenue mechanics — the key thing to solve with the ITA

IRAP is a **reimbursement of *paid* technical salaries** (up to 80%; up to 50% of
subcontractors; ~75% total-assistance cap). That mechanism creates two linked requirements
that a pre-revenue, no-payroll, founder-only company must address head-on:

1. **A salary must actually be paid to be claimed.** The founder is **not yet on payroll** and
   plans to go on a **T4 salary once there is revenue.** For IRAP, the sequence is the reverse:
   the company would need to **establish T4 payroll for the founder to perform the funded R&D**,
   pay that salary, and then claim the IRAP share against it. (Owner/founder salaries are
   eligible when paid as arm's-length-equivalent T4 compensation, but are an area the ITA will
   scrutinize — confirm treatment.)
2. **Working capital to fund the gap.** IRAP reimburses *after* cost is incurred, and never
   100%. So the company needs cash to (a) float payroll until reimbursement lands and (b) fund
   its own ~20–25% share. With no revenue and no cash today, **the source of that working
   capital is the open question.** Realistic options to discuss with the ITA:
   - **The IDEaS award**, if won (~$157K, pending evaluation) — note IRAP and IDEaS **cannot
     fund the same work twice**, so they would have to cover **different scope or different
     time periods**; sequencing matters.
   - **Founder capital / shareholder loan** into the company to seed payroll.
   - **A small angel / pre-seed bridge** (already contemplated in the venture plan as a
     runway option).
   - Asking the ITA directly **how IRAP structures contributions for pre-revenue startups** —
     this is a common situation and ITAs have standard ways to handle it (e.g. milestone
     timing, claim frequency).

> **Bottom line:** the model R&D is well-scoped and de-risked; the *financing structure for a
> pre-revenue founder-only company* is the real work item. Resolve it with the ITA before
> sizing the ask. This also argues for a **small first project** (lower absolute cash float)
> over a large one as the entry point.

### 8.3 Stacking with IDEaS and SR&ED

IRAP can coexist with the IDEaS award and with SR&ED tax credits, but the **same eligible
dollar cannot be funded twice** and the ~75% total-government-assistance cap applies — to be
managed transparently with the ITA. SR&ED is largely moot while pre-revenue/pre-tax-liability
but becomes relevant once the company has income.

### 8.4 Company financial position

**Pre-revenue; no revenue lines; no payroll yet.** The ~10-year-old corporation will have
CRA-filed (likely nil/low-activity) financial statements available — **gather the latest set
for the ITA**, and be ready to state the current cash position and the intended working-capital
source from §8.2. **`[CONFIRM: current cash on hand; whether founder will inject capital /
seek a bridge to seed payroll.]`**

---

## 9. Benefit to Canada

- **Sovereign AI capability** for a hard, operationally costly problem (dark-vessel detection)
  affecting fisheries, sanctions enforcement, and Arctic sovereignty.
- **Canadian-owned IP** (the novel fusion model) and **open-source reference code** that
  outlast the project window.
- **Made-in-Canada defence industrial base** contribution (the DI Assist objective) — a
  Victoria, BC company contributing to CAF capability.
- **A highly-qualified-personnel role** sustained in BC (the PhD founder doing frontier
  deep-learning R&D); the project keeps advanced AI capability and IP being developed in Canada.
- **Interoperable with allies** (NATO / Five-Eyes MDA) — a sovereign capability that is not a
  black box.

---

## 10. Risks & mitigations

| Risk | Mitigation |
|---|---|
| **Financial capacity — pre-revenue, no payroll, no cash** (IRAP's reimbursement model needs paid salary + working-capital float) | **The top item.** Establish T4 payroll for the project; secure working capital (IDEaS award if won / founder capital / small bridge); start with a *small* first project to minimize cash float; ask the ITA how IRAP structures pre-revenue startups (§8.2) |
| **Solo-founder execution capacity** | 10-yr incorporated history + shipped, tested code + filed competitive DND bid + published semi-supervised-ML record; subcontractors available for discrete pieces |
| **Model R&D risk** (can the fusion model hit calibrated, explainable outputs?) | Built substrate removes integration risk; AIS self-supervision removes the label barrier; founder's published semi-supervised-ML track record |
| **Single-buyer (defence) concentration** | Dual-use commercial maritime paths + data marketplace; pursue non-DND design partners |
| **Canadian-controlled status vs. US capital / ITAR** | An asset for Canadian defence contracts; decide capital strategy early |
| **Data-moat overclaim** | Pitch the flywheel as "designed in, first data points collected," never "we have a data moat today" |

---

### Appendix — verifiable spine (for ITA / audit)

- **Open-source repos** (GitHub, audit-tagged `submission-2026-05-30`): planetar-broker,
  zmesg, planetar-ais, planetar-sat, planetar-eo, planetar-acoustic, planetar-ontology,
  planetar-registry, planetar-ui.
- **Benchmark:** `planetar/docs/benchmark-2026-04-27.md` (SHM p50 80–140 ns / p99 400–900 ns).
- **Publications:** Sattar et al. 2011 (IEEE PacRim); ORCA-SLANG (Interspeech 2021); Ness,
  Walters, Lyon (2012); and others (full list: `planetar/04-PORTFOLIO.md`).
- **Background patents (named-inventor, Salesforce-assigned):** US 10,936,582 B2; US 11,442,952 B2.
- **Filed DND proposal:** IDEaS CFP6 Challenge 13, CP6-132484 (2026-06-01), TRL 2→3.
