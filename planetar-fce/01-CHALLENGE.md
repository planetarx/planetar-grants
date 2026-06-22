# 01 — CH14 outcomes → planetar mapping (the rubric)

> Authoritative outcome text: [`CHALLENGE.md`](CHALLENGE.md) (verbatim from the CH14 PDF).
> This file is the traceability spine for `MC-2_alignment.md` and `PRC-6_desired_outcomes.md`
> — keep all three consistent (the CH13 analogue is `planetar/docs/cfp6-alignment-matrix.md`).

## Essential Outcomes (MUST — pass/fail, drive MC-2)

| ID | CH14 Essential (paraphrased) | planetar built asset | Net-new in the 1a | Demo evidence |
|---|---|---|---|---|
| **EO1** | Modular AI component enforcing classification/policy during ≥2-sensor fusion | broker chokepoint; ≥2 detectors publishing | policy-eval hook at publish/subscribe | live enforce on AIS+SAR (or +EO) |
| **EO2** | Machine-readable policy across ≥2 modalities, ≥Network-security domain, ≥Protected B | `planetar-market` ODRL policy + manifests | ODRL→classification/release-authority vocab; class+domain envelope fields | policy file → enforced decision |
| **EO3** | Programmatic checks during ingestion/fusion, no human approval for predefined conditions | bus is the automated chokepoint | synchronous decision in the publish path | trace: msg → auto decision |
| **EO4** | Provenance records: source ID, classification, timestamp, domain of origin | `zmesg`: source, ns ts, correlation/causation | add `classification`, `domain` fields | envelope dump per element |
| **EO5** | Audit logs: rules applied, actions (permit/restrict/downgrade/segregate), dispositions | CRC32 append-only WAL | enforcement-action WAL record type | WAL export of a session |
| **EO6** | Exportable data-lineage traceability ingestion → fusion output | WAL replay + ontology per-edge lineage | accreditation/forensic export format | exported lineage artifact |

**Read:** every Essential = an existing primitive + a small additive change. No EO needs
hardware, DND-supplied data, or non-software capability. (This is the bar the two prior
no-bids failed — see `FIT.md`.)

## Desired Outcomes (SHOULD — scored, drive PRC-6)

| ID | CH14 Desired | planetar strength |
|---|---|---|
| **DO1** | Real-time enforcement at tactical-decision speed | ns-scale chokepoint (`zbroker0` p50 80–140 ns / p99 400–900 ns) — enforcement adds negligible latency |
| **DO2** | Adaptable policy without system restart | ODRL policies are **data**, not code → hot-reload |
| **DO3** | SWaP / compute limits for edge | ~1.2k-LOC dependency-light **C** broker = genuine edge artifact (Tactical-Edge example) |
| **DO4** | Explainability + operator trust + controlled override | `planetar-ui` causation-chain drill-down; override = a policy-authority action logged to WAL |

## Application domain for the demo

CH14 names **Maritime Domain Awareness** as an example ("compliance checks during
multi-sensor anomaly detection") — planetar's home turf. Use MDA as the demo domain; the
FCE is the product, MDA is the setting. (Other CH14 examples: Joint ISR Fusion, Tactical
Edge Dismounted — reference as breadth, don't build.)

## TODO (authoring)
- [ ] Confirm exact EO wording against `CH14-challenge.txt` lines 57–93 when drafting MC-2.
- [ ] Decide the 2 demo modalities (AIS+SAR vs AIS+EO) and the synthetic Protected-B markings.
- [ ] Cross-check every MC-2 / PRC-6 claim back to a row here.
