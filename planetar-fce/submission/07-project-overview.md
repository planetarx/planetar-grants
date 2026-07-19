# Field 07 — Project Overview

**Form section:** Component 1a → 2 - Project Description → C · **Cap:** 3,000 characters
**Field label:** *"Provide a project overview, which is a synopsis of project's S/T Merit, Novelty and Innovation, Impact, Feasibility and Approach."*
**Audience:** reviewer's first detailed read before the PRC fields. Each paragraph maps to a PRC; citations stay in the PRCs.
**Status:** ✅ READY.

--- PASTE THIS BELOW ---
The Fusion Compliance Engine (FCE) is a modular, AI-enabled component that enforces classification and release-authority policy in real time during multi-sensor fusion. It sits at the single message chokepoint between sensor ingestion and the fusion pipeline, evaluates machine-readable policy against each data element, and decides — permit, restrict, downgrade or segregate — before a cross-domain merge occurs, while emitting an immutable, exportable audit-and-lineage record. The supporting real-time, provenance-tracked platform is already built and open-source.
Scientific and Technical Merit (PRC-1): the science is per-element policy enforcement inside the fusion path, at the chokepoint, fast enough to add no tactical latency. It rests on recognised standards (W3C ODRL policy; NATO STANAG 4774/4778 classification markings; W3C PROV lineage), an attribute-based decision over each element's classification, domain, source, modality and releasability, and a built, measured nanosecond-scale message bus with an immutable write-ahead log.
Novelty and Innovation (PRC-2): compliance for fusion is enforced today by manual review or by perimeter cross-domain guards that screen at a network boundary. The FCE instead renders per-element dispositions in-path, during fusion — inherently always-invoked and non-bypassable because every element crosses one bus — and repurposes a civil machine-readable rights standard (ODRL) as sovereign defence classification policy. Accreditation-grade lineage is a structural property of the substrate, not a bolt-on report.
Impact (PRC-3): the FCE closes a stated sovereign capability gap, removing the manual-review bottleneck so cross-domain fusion is both faster and audit-safe. It is a reusable building block for every future fusion system — from Arctic surveillance to coalition interoperability — built on the applicant's own open-source code and net-new, Canadian-owned IP, aligned to NORAD modernization, the CAF Digital Campaign Plan, and the DND/CAF AI Strategy.
Feasibility and Approach (PRC-4): the work runs over two milestone stages on public data, adding enforcement to a chokepoint the applicant already owns. Milestone 1 builds the policy model, the additive classification and domain fields, the demonstration data setup, and the architecture of a hardware enforcement datapath. Milestone 2 builds the enforcement engine, the write-ahead-log enforcement record, the exportable lineage, an evaluator-operable live planetar.ca demonstration on two modalities under synthetic Protected-B markings, the enforcement-overhead benchmark, and an FPGA prototype of the datapath (a RISC-V core with custom policy-check instructions) for edge and server profiles. A two-person Zax Analytics team (founder + IC-design engineer); no government-furnished property, no field deployments, no real classified content.
--- END PASTE ---

## Notes
- A synopsis — asserts the claims; the PRC fields carry the citations.
- If over 3,000: trim the trailing deliverable list in the Feasibility paragraph first.
