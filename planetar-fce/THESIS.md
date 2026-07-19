# Thesis: compliance-by-design is the science of the 1a (SSOT)

> **This file is the single source of truth all CH14 narratives must match** — the
> CH14 analogue of `planetar/docs/recenter-learned-fusion.md`. If a narrative drifts
> from this framing, fix the narrative. Decision basis: [`FIT.md`](FIT.md) + the CH14
> challenge text [`CHALLENGE.md`](CHALLENGE.md).

## The pivot (read this first)

CH13's thesis was a **learned cross-modal fusion model**, with the provenance substrate
demoted to "enabling infrastructure." **CH14 inverts that.** CH14 asks for a **Fusion
Compliance Engine (FCE)** — a policy-aware gatekeeper between sensor ingestion and the
fusion pipeline. The *fusion* is assumed; the *scored science* is **automated policy
enforcement + provenance + exportable audit lineage, at tactical-edge latency**.

So for CH14, the demoted CH13 substrate (bus + `zmesg` envelope + CRC32 WAL + ontology
lineage + ODRL policy) becomes the **hero**, and the learned fusion model recedes to
background. **Do not reuse the learned-fusion-model-as-thesis framing.**

## New thesis (one sentence)

> **planetar's FCE is a sovereign, Canadian-controlled compliance-by-design engine that
> sits at the single message chokepoint every fused observation crosses — evaluating
> machine-readable classification and release-authority policy in real time to tag,
> permit, restrict, downgrade, or segregate each data element, while emitting an
> immutable, exportable audit-and-lineage record — fast enough (ns-scale chokepoint) to
> add no tactical-decision latency.**

The 1a builds and demonstrates the FCE across **≥2 sensor modalities at Protected B**,
on a live system, advancing it **TRL 2 → 3**.

## Why planetar wins this (the structural advantage)

The FCE's whole design problem is: *insert policy enforcement into the fusion path
without adding latency.* planetar already **is** that path — every observation crosses
one typed bus, already carries provenance (`source`, ns timestamps, correlation/causation
ids), and is already journalled immutably (CRC32 WAL). We are not building a compliance
layer beside a fusion system; we **own the chokepoint** and add enforcement at it.

## Build vs. propose (honesty spine)

**BUILT (the substrate the FCE enforces on):**
- `planetar-broker` — the single chokepoint between ingestion and fusion (the FCE's seat).
- `zmesg` — typed zero-copy envelope: UUIDv7, ns timestamps, topic, `source`, correlation/
  causation ids = native provenance.
- **CRC32 append-only WAL** — immutable journal = the audit-trail + replayable lineage spine.
- `planetar-ontology` — per-edge provenance in the entity graph (lineage through fusion output).
- `planetar-market` — **W3C ODRL machine-readable policy** + provenance manifests = the
  policy language the FCE evaluates.
- 4 modality detectors (`-ais/-sat/-eo/-acoustic`) — the ≥2 modalities to demo across.
- `planetar-ui` — clicks a detection back through its causation chain = explainable
  compliance decisions for free.

**PROPOSE (the genuine R&D of the 1a — the FCE itself):**
- The **policy-evaluation engine** at the chokepoint: machine-readable policy → real-time
  decision (permit / restrict / downgrade / segregate) on each element, no human approval.
- Additive `zmesg` fields: **classification marking** + **domain of origin**.
- A WAL **enforcement-action record type**: rule applied, action taken, disposition.
- **Exportable accreditation/lineage format** (compliance review / forensic / accreditation).
- The **policy model** mapping ODRL → classification guides, release authorities, coalition
  caveats, with hot-reload (no system restart).

## Doctrine hooks to thread (a DND reviewer rewards these)

NORAD modernization · CAF Digital Campaign Plan · DND/CAF AI Strategy · Cyber Forces
mandate · **sovereign Canadian-developed/-controlled IP** (the challenge says Canada lacks
this) · Arctic surveillance · coalition interoperability.

## Cut / demote from the SCORED narratives

- The learned cross-modal fusion model as *thesis* → at most one line of background.
- Dark-vessel re-identification as *the product* → it's now just one fusion use-case the
  FCE governs (Maritime Domain Awareness is a named CH14 example — use it as the demo
  domain, not the pitch).
- Bus latency framing changes role: in CH13 it was "real-time fusion"; here it's the
  **"no added latency to enforcement"** proof — same chokepoint, now measured on
  planetar-broker itself (ring-hop 2026-07-13: p50 95–100 ns / p99 1.0–1.6 µs;
  `benchmark-2026-07-13-ring-hop.md`), different argument.

> **R8 amendment (2026-07-13):** the 1a adds a **subordinate hardware work package** — an FPGA-prototyped
> RISC-V enforcement datapath (custom instructions: envelope parse, label match, disposition; server +
> sensor-adjacent camera/UAS profiles), owned by Colin Broughton (employee, IC-design engineer). It serves
> the FCE thesis (DO3 SWaP, DO1 real-time); it is **not a second thesis** — keep "distributed disruptor"
> framing out of all bid text. Budget $181K per `proposal/PRC-7_budget.md`; decision record `08` R8.

## Per-narrative pivot checklist

| Narrative | CH14 angle |
|---|---|
| MC-1 (TRL) | FCE is TRL 2 → 3; substrate is built evidence, FCE engine is the new build |
| MC-2 (alignment) | map to CH14 Essential outcomes EO1–EO6 (see `01-CHALLENGE.md`) |
| PRC-2 (novelty) | the FCE enforcement-at-the-chokepoint approach + ODRL policy model — NOT the fusion model |
| PRC-4 (feasibility) | own the chokepoint already; additive fields + engine; ns-latency headroom |
| PRC-6 (desired outcomes) | real-time, hot-reload policy, SWaP/edge (C broker), explainable override |
