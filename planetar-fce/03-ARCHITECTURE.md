# 03 — FCE architecture (the compliance layer on the bus)

> Skeleton. The CH13 analogue is `planetar/03-ARCHITECTURE.md` (5-layer reference
> architecture) — **reuse the substrate description, add the FCE as a new enforcement
> layer.** Diagrams go in a future `docs/` (mirror `planetar/docs/architecture-diagrams.md`).

## The one-line architecture

```
sensors → [ingestion] → ┌─────────── FCE (new) ───────────┐ → [fusion analytics] → shell
                        │ policy eval @ chokepoint:        │
  zmesg envelopes ─────▶│  tag · permit/restrict/downgrade │──▶ provenance-stamped output
  (source, ts, ids,     │  /segregate per ODRL policy      │    + immutable WAL audit record
   +class, +domain)     └──────────────┬──────────────────┘    + exportable lineage
                                        │
                              CRC32 append-only WAL  (audit trail + replayable lineage)
```

The FCE is **not a new system beside fusion** — it is a hook **inside the one bus** every
fused observation already crosses. That is the whole structural advantage (see `THESIS.md`).

## Layers

| Layer | Repo (built) | Role in the FCE | 1a change |
|---|---|---|---|
| Envelope | `zmesg` | carries provenance every element needs | **add** `classification`, `domain_of_origin` fields |
| Bus / chokepoint | `planetar-broker` | the single point enforcement sits at | **add** synchronous policy-eval hook on publish/sub |
| Policy | `planetar-market` (ODRL) | machine-readable rules the engine evaluates | **map** ODRL → classification guides / release authorities / coalition caveats; hot-reload |
| Audit/lineage | CRC32 WAL + `planetar-ontology` | immutable journal + per-edge lineage | **add** enforcement-action record type + export format |
| Detectors | `planetar-ais/-sat/-eo/-acoustic` | the ≥2 modalities enforced across | none (reuse) |
| Shell | `planetar-ui` | explainable decisions + controlled override | surface compliance disposition + override-as-logged-action |

## The FCE engine (the net-new R&D — detail for PRC-2 / PRC-4)

1. **Policy model.** ODRL permission/prohibition/duty → an evaluable rule over an element's
   `{classification, domain, source, modality, releasability}`. Decision space:
   **permit / restrict / downgrade / segregate**.
2. **Evaluation point.** Synchronous check in the broker publish path (and on cross-domain
   merge in the fusion consumer). Must stay within the latency budget — measure overhead vs.
   the `zbroker0` baseline; target enforcement overhead ≪ tactical-decision threshold.
3. **Disposition + audit.** Every decision writes a WAL enforcement-action record (rule id,
   action, disposition, element provenance) — append-only, CRC32, replayable.
4. **Lineage export.** Reconstruct ingestion→fusion-output lineage from WAL + ontology edges;
   serialize to an exportable accreditation/forensic format.
5. **Hot-reload.** Swap policy sets without restart (data, not code) for rapid context change.

## Latency argument (DO1 — the FCE's core risk)

The FCE's design risk is *added latency in the fusion path*. planetar's measured
ns-scale chokepoint (`../benchmark-2026-07-13-ring-hop.md`: planetar-broker ring-hop
p50 95–100 ns / p99 1.0–1.6 µs SHM; predecessor `zbroker0` 2026-04-27: p50 80–140 ns /
p99 400–900 ns) gives headroom to insert a policy check and still stay far under any
tactical-decision threshold. **The 1a must measure FCE-on overhead** and report it the same
conservative way as the CH13 benchmark (bracket measured runs; no post-tuning numbers).

## TODO (authoring)
- [ ] Draw the FCE sequence diagram (element → policy eval → disposition → WAL → export).
- [ ] Define the ODRL→classification mapping concretely for the 2 demo modalities.
- [ ] Specify the WAL enforcement-action record layout.
- [ ] Specify the exportable lineage format (accreditation-friendly).
