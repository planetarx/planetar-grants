# Fields 20–22 — Work Plan & Deliverables (2 milestones) + Total — THE ACTUAL FINANCIAL ENTRY

**Form section:** Component 1a → Work Plan and Deliverables → Milestone 1 / Milestone 2 / Total Firm Milestone Price
**Status:** ✅ R8 budget (2026-07-13): **$181,000** total. This 2-milestone form is where SC-1 + PRC-7 are assessed.
**Key rule:** Milestone 1 ≤ 70% of total. Ours = **39.8%** ✅.
**Rates:** both team members **$140/hr fully-loaded** (no separate overhead line — sidesteps §3.7). Hours: PI 900 + IC engineer 330 = 1,230.
**Per-entry cap:** each activity sub-field ≤ **800 characters**; Other-Costs descriptions ≤ 255. No blank lines inside boxes.
**Bucket note:** PRC-7 Table B lumped the $3,800 FPGA board into M2 "other costs"; in the DIP it goes in the **Materials** table (CH13 precedent: the MacBook). Totals unchanged.
**Consistency anchor:** activities mirror field 11's milestone sentences and PRC-4's six increments; the two GBA-Plus deliverables promised in PRC-5 (bias-audit protocol; accessibility + bilingual checklist) appear in M2 activities 3–4.

| Stage | Content | Cost | % |
|---|---|---|---|
| **Milestone 1** (design) | policy model · envelope fields · hook design · demo data · datapath architecture+simulation (CB) | **$72,000** | **39.8%** |
| **Milestone 2** (build + demo) | enforcement engine · WAL record + lineage · planetar.ca demo · overhead benchmark + GBA+ artefacts · FPGA prototype (CB) | **$109,000** | 60.2% |

═══════════════════════════════════════
# MILESTONE 1 — total $72,000

**Total Performance Period (in weeks):** `13`

---
## Activity 1 — "Add Activity"

**Activity:**
```
Design the FCE policy model: map classification guides, release authorities and coalition caveats onto W3C ODRL constructs, defining the disposition vocabulary (permit, restrict, downgrade, segregate) as a decision over each element's classification, domain, source, modality and releasability. Policy sets are versioned data, loadable at runtime (hot-reload, no restart). Author the synthetic Protected-B policy set the demonstration enforces.
```
**Description of Deliverable:**
```
A documented ODRL-based classification/release policy model with the disposition vocabulary, plus the versioned synthetic Protected-B policy set used by the demonstrator.
```
**Estimated Level of Effort (Weeks):** `3`

**Risk(s): Description, probability and impact:**
```
ODRL was designed to express digital rights, and some defence classification semantics (caveats, releasability chains) may not map cleanly onto its core constructs (medium probability). Impact: policy model rework within this activity.
```
**Risk mitigation strategy(ies):**
```
The applicant already ships a working ODRL expression layer (planetar-market, test-covered); extend it with a defence-classification ODRL profile rather than bending core constructs, and anchor the marking vocabulary to NATO STANAG 4774 label syntax so the semantics follow an established standard.
```

---
## Activity 2 — "Add Activity"

**Activity:**
```
Add the classification-marking and domain-of-origin fields to the zmesg typed envelope — structured to NATO STANAG 4774 confidentiality-label syntax, bound to the element per STANAG 4778 — and update the per-service codecs so every message on the bus carries its marking end-to-end, under regression tests.
```
**Description of Deliverable:**
```
A versioned envelope carrying classification-marking and domain-of-origin fields on every message, with all in-repo service codecs updated and regression gates passing.
```
**Estimated Level of Effort (Weeks):** `2`

**Risk(s): Description, probability and impact:**
```
Envelope changes touch every service codec, so an inconsistency could ripple across the pipeline (low-medium probability). Impact: integration rework contained to the codecs.
```
**Risk mitigation strategy(ies):**
```
The fields are additive and the envelope is versioned; every codec is in applicant-controlled open-source repositories, and the change is locked behind the existing regression suites before any downstream work depends on it.
```

---
## Activity 3 — "Add Activity"

**Activity:**
```
Design the synchronous policy-evaluation hook at the broker publish path: evaluation order, fail-safe semantics (default-deny on policy fault), the four disposition actions, and the enforcement-action record type written to the write-ahead log. Define the FCE-on overhead measurement protocol against the measured shared-memory baseline (p50 95-100 ns / p99 1.0-1.6 microseconds, four 1M-message runs, 2026-07-13).
```
**Description of Deliverable:**
```
The enforcement-hook design specification: evaluation semantics, fail-safe behaviour, disposition actions, WAL enforcement-action record schema, and the overhead measurement protocol for Milestone 2.
```
**Estimated Level of Effort (Weeks):** `2`

**Risk(s): Description, probability and impact:**
```
A synchronous in-path check could add measurable latency to the fusion path (medium probability). Impact: erodes the no-added-tactical-latency outcome if unmanaged.
```
**Risk mitigation strategy(ies):**
```
Design against the measured nanosecond-scale baseline: policies compile ahead of time to a fast lookup at publish time, with the rare complex case escalated rather than evaluated inline. Overhead is then measured in Milestone 2 and reported conservatively — bracketed measured runs, no post-tuning figures.
```

---
## Activity 4 — "Add Activity"

**Activity:**
```
Set up the two-modality demonstration data: live open AIS and Sentinel-1 SAR detections, with synthetic classification markings applied (AIS unclassified; SAR detections marked Protected B) so the demonstrator exercises a genuine cross-domain-merge decision without touching real classified material. Package the scenario for bit-exact replay from the write-ahead log.
```
**Description of Deliverable:**
```
A replayable AIS + SAR demonstration dataset under synthetic Protected-B markings — the scenario the Milestone 2 demonstrator and evaluation run against.
```
**Estimated Level of Effort (Weeks):** `2`

**Risk(s): Description, probability and impact:**
```
Sentinel-1 scene availability or processing for the chosen operating area could lag (low probability). Impact: demo data setup slips within the milestone.
```
**Risk mitigation strategy(ies):**
```
The SAR pipeline (planetar-sat: fetch, CFAR detect) is already built and validated on a real Sentinel-1C scene; archived scenes are an equivalent fallback, since the compliance decision is driven by the synthetic markings, not scene freshness.
```

---
## Activity 5 — "Add Activity"  *(owner: IC-design engineer)*

**Activity:**
```
Specify the hardware enforcement-datapath architecture: a RISC-V core extended with custom instructions for envelope parse, classification-label match and disposition, targeting two profiles — server offload at the chokepoint and sensor-adjacent enforcement on cameras and uncrewed platforms. Validate the design in cycle-level simulation against recorded bus traffic and define the Milestone 2 FPGA prototyping plan. Owned by the IC-design engineer.
```
**Description of Deliverable:**
```
The datapath architecture specification (instruction set, pipeline, both deployment profiles), cycle-level simulation results against recorded bus traffic, and the Milestone 2 FPGA prototype plan.
```
**Estimated Level of Effort (Weeks):** `4`

**Risk(s): Description, probability and impact:**
```
A fixed custom-instruction set may not cover every policy-match case in hardware (medium probability). Impact: some policy classes would fall back to software evaluation, reducing the offload benefit for those cases only.
```
**Risk mitigation strategy(ies):**
```
Hybrid by design: common-case dispositions execute in hardware; rare or complex policies escalate to the software FCE, which remains the complete reference implementation. The hardware package is scoped to architecture-and-FPGA proof — the software engine never depends on it.
```

*(Level-of-effort note: activities 1–4 are the Principal Investigator's track (≈400 h); activity 5 runs in parallel (IC engineer, ≈100 h). Effort-weeks 3+2+2+2+4 = 13 within the 13-week period.)*

---
## Milestone 1 — Financials

### Labour — "Add Labour" (two rows)
| Field | Row 1 | Row 2 |
|---|---|---|
| Category | `Principal Investigator (PhD, Computer Science / Machine Learning)` | `IC-Design Engineer (hardware enforcement datapath)` |
| Labour (h) | `400` | `100` |
| Rate ($/h) | `140.00` | `140.00` |
| Total ($) | `56000.00` | `14000.00` |

→ Total Labour: **$70,000**

### Materials — skip → $0.00 · ### Travel — skip → $0.00

### Other Costs — "Add Other Costs" (two rows)
**Row 1**
- Other cost: `Cloud compute`
- Description: `Cloud compute for Sentinel-1 scene fetching and processing, policy-evaluation test runs, and hosting the live planetar.ca system. No model training.`
- Cost ($): `1500.00`

**Row 2**
- Other cost: `Software / tools`
- Description: `Development and operations tooling: continuous-integration runner minutes, observability/monitoring, and ancillary paid developer services. RTL work uses open-source toolchains.`
- Cost ($): `500.00`

→ Total Other Costs: **$2,000**
### TOTAL FIRM MILESTONE 1 PRICE: **$72,000** (39.8% of $181,000 — ≤70% ✅)

═══════════════════════════════════════
# MILESTONE 2 — total $109,000

**Total Performance Period (in weeks):** `13`

---
## Activity 1 — "Add Activity"

**Activity:**
```
Build the FCE enforcement engine at the broker chokepoint: the synchronous policy-evaluation hook from the Milestone 1 design, rendering a permit, restrict, downgrade or segregate disposition for every element before any cross-domain merge, with live policy hot-reload (a policy-set swap mid-session with enforcement continuing uninterrupted).
```
**Description of Deliverable:**
```
The working enforcement engine at the chokepoint: per-element dispositions on live AIS + SAR traffic under the synthetic Protected-B policy set, with demonstrated mid-session policy hot-reload.
```
**Estimated Level of Effort (Weeks):** `5`

**Risk(s): Description, probability and impact:**
```
The enforcement engine is the project's central new build (medium probability of design-to-build friction). Impact: schedule pressure on the demonstration activities later in the milestone.
```
**Risk mitigation strategy(ies):**
```
The engine lands on a built, benchmarked substrate the applicant owns end-to-end — the hook is additive at one well-understood point, not a rebuild. The Milestone 1 design specification, fail-safe semantics and pre-compiled policy lookup bound the build risk, and demo scope is cut before the timeline extends.
```

---
## Activity 2 — "Add Activity"

**Activity:**
```
Implement the enforcement-action record type in the CRC32 append-only write-ahead log — rule applied, action taken, resulting disposition, journalled immutably for every decision including operator overrides — and deliver the exportable ingestion-to-output lineage format modelled on W3C PROV, reconstructable by replay for compliance review, forensic analysis or accreditation.
```
**Description of Deliverable:**
```
Immutable enforcement-action audit records in the WAL for every disposition and override, plus the exportable W3C-PROV-modelled lineage format with a demonstrated ingestion-to-output reconstruction.
```
**Estimated Level of Effort (Weeks):** `2`

**Risk(s): Description, probability and impact:**
```
Lineage export could grow large or slow on long scenarios (low probability). Impact: slower export runs; no effect on in-path enforcement, which never waits on export.
```
**Risk mitigation strategy(ies):**
```
Export is an offline replay over the WAL, decoupled from the enforcement path by design; scenario-scoped exports and the existing bit-exact replay machinery keep it bounded.
```

---
## Activity 3 — "Add Activity"

**Activity:**
```
Deliver the evaluator-operable live demonstration at planetar.ca: the Technical Authority can drive the running system during evaluation — change a policy and watch enforcement hot-reload, and click any disposition back through its governing rule and the element's provenance, with override as a logged, attributable action. Built against the operator-accessibility and English/French readiness checklist (keyboard navigation, screen-reader compatibility, colour-vision-safe disposition encoding), delivered as a project artefact.
```
**Description of Deliverable:**
```
The live, evaluator-operable planetar.ca FCE demonstration (two modalities, synthetic Protected-B markings) plus the documented accessibility and bilingual-readiness checklist.
```
**Estimated Level of Effort (Weeks):** `3`

**Risk(s): Description, probability and impact:**
```
Demonstrator scope could overrun (medium probability). Impact: less time for the evaluation and benchmark activity at the end of the milestone.
```
**Risk mitigation strategy(ies):**
```
The analyst shell, live feeds and provenance drill-down already exist (planetar-ui); this activity adds the disposition surface and policy controls. Non-essential viewer polish is cut before the schedule slips.
```

---
## Activity 4 — "Add Activity"

**Activity:**
```
Measure and evaluate: (a) FCE-on enforcement overhead against the no-enforcement baseline on the shared-memory path, reported conservatively (bracketed measured runs, no post-tuning figures) with the FCE-on compute/memory envelope for edge deployment; (b) policy-decision correctness on the labelled synthetic Protected-B set; (c) lineage-export fidelity against ground truth; (d) the disposition bias-audit protocol — enforcement decisions stratified by source, modality and region to surface uneven handling (the GBA-Plus artefact).
```
**Description of Deliverable:**
```
The measurement report: enforcement overhead vs baseline, edge compute/memory envelope, policy-decision correctness, lineage-export fidelity, and the stratified disposition bias audit.
```
**Estimated Level of Effort (Weeks):** `2`

**Risk(s): Description, probability and impact:**
```
Measured enforcement overhead could exceed expectations for complex policy sets (low-medium probability). Impact: the reported overhead bracket is wider than hoped; results remain honest and useful.
```
**Risk mitigation strategy(ies):**
```
The same conservative discipline as the existing benchmark: report the measured bracket whatever it is, stratify by policy complexity so the common case is visible, and use the pre-compiled-lookup design from Milestone 1 to keep the common path fast.
```

---
## Activity 5 — "Add Activity"  *(owner: IC-design engineer)*

**Activity:**
```
Implement the hardware enforcement datapath from the Milestone 1 architecture: RTL for the RISC-V core with the custom envelope-parse, label-match and disposition instructions; verification against the cycle-level simulation; and an FPGA prototype demonstrated on live bus traffic in both target profiles (server offload; sensor-adjacent for cameras and uncrewed platforms). Owned by the IC-design engineer.
```
**Description of Deliverable:**
```
The FPGA-prototyped enforcement datapath running against live bus traffic, with verification results and a measured comparison against the software gate — the silicon-ready proof for the Component 1b tape-out path.
```
**Estimated Level of Effort (Weeks):** `6`

**Risk(s): Description, probability and impact:**
```
RTL verification is the dominant hardware cost and could compress the FPGA demo (medium probability). Impact: the prototype demonstrates fewer policy classes in hardware than planned.
```
**Risk mitigation strategy(ies):**
```
The hybrid escalation design makes partial hardware coverage safe — anything not proven in hardware runs through the software FCE, so the project deliverables never depend on hardware completeness. Verification reuses the recorded-traffic test vectors from Milestone 1 simulation.
```

*(Level-of-effort note: activities 1–4 are the Principal Investigator's track (≈500 h); activity 5 runs in parallel (IC engineer, ≈230 h). Effort-weeks total 18 across the two parallel tracks within the 13-week period.)*

---
## Milestone 2 — Financials

### Labour — "Add Labour" (two rows)
| Field | Row 1 | Row 2 |
|---|---|---|
| Category | `Principal Investigator (PhD, Computer Science / Machine Learning)` | `IC-Design Engineer (hardware enforcement datapath)` |
| Labour (h) | `500` | `230` |
| Rate ($/h) | `140.00` | `140.00` |
| Total ($) | `70000.00` | `32200.00` |

→ Total Labour: **$102,200**

### Materials — "Add Materials" (one row)
| Field | Value |
|---|---|
| Description | `FPGA development board and prototyping sundries (RISC-V-capable, for the hardware enforcement-datapath prototype)` |
| Quantity | `1` |
| Unit Cost ($) | `3800.00` |
| Total ($) | `3800.00` |

### Travel — skip → $0.00

### Other Costs — "Add Other Costs" (three rows)
**Row 1**
- Other cost: `Cloud compute`
- Description: `Cloud compute for enforcement-overhead benchmark runs, policy-correctness and lineage-fidelity evaluation, Sentinel-1 processing, and hosting the live evaluator-operable planetar.ca demonstrator.`
- Cost ($): `2000.00`

**Row 2**
- Other cost: `Software / tools`
- Description: `Development and operations tooling: continuous-integration runner minutes, observability/monitoring, and ancillary paid developer services. RTL flow on open-source toolchains.`
- Cost ($): `500.00`

**Row 3**
- Other cost: `Datasets / licences`
- Description: `Reserve for paid data access if a public source proves insufficient; core demonstration data (AIS, Sentinel-1) are public and free.`
- Cost ($): `500.00`

→ Total Other Costs: **$3,000**
### TOTAL FIRM MILESTONE 2 PRICE: **$109,000** ($102,200 labour + $3,800 materials + $3,000 other)

═══════════════════════════════════════
## TOTAL FIRM MILESTONE PRICE

- Milestone 1: **$72,000** (39.8%)
- Milestone 2: **$109,000** (60.2%)
- **TOTAL: $181,000** — 72.4% of the $250K cap · SC-1 passes with a 30.2-pp margin.

**Reconciliation:** Labour $172,200 (PI 900 h + IC 330 h, both × $140 fully-loaded) + Materials $3,800 (FPGA board, M2) + Other $5,000 (compute $3,500 + software $1,000 + datasets $500) = **$181,000**. Travel $0. Keep both Labour Category strings identical across milestones.
