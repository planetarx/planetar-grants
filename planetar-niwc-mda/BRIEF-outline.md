# Step-1 solution brief — outline and build schedule (lane B)

> Outline 2026-10-22; no prose drafted. Five pages at 12-point (title page not counted), or 15
> slides (§4.1). Lane B: close the top gaps, then brief. Every claim must cite a repo path or a
> measurement; anything not yet true is marked **[GAP]** and either gets built or comes out.

## The one-line offer (draft — the SSOT will be `THESIS.md`)

An open, auditable **dark-vessel candidate feed for SeaVision**: vessel detections from Sentinel-1
SAR, associated with AIS, where every result names the exact sources it came from and the method
is published in full.

**Thesis guard:** the hero is the *feed and its auditability* (R6, R7). It must not be CH13's
learned cross-modal fusion model or CH14's compliance engine (FIT risk 6). Overlap to resolve in
`THESIS.md`: R6 per-result provenance is close to CH14's substrate — present it as a property of
the feed, not as the product.

## Page plan

| Page | Section (§4.1 item) | Content | Evidence | State |
|---|---|---|---|---|
| — | Title page (1) | Zax Analytics, address, POC, CAGE/NCAGE "if available", date | `SAM-REGISTRATION.md` | `[TODO]` NCAGE |
| 1 | Executive summary (2) | The offer; what SeaVision receives; why it is trustworthy (named sources, open method); availability | — | outline only |
| 1–2 | Technology concept (3) | Pipeline as delivered: Sentinel-1 GRD → SAR vessel detector → **rule-based kinematic AIS association** (`kinematics.ts` dead-reckons known vessels to the image time) → dark-candidate flag (a detection no AIS track explains) → feed. What is innovative: per-result source identification down to the product ID, open method, measured accuracy. The **learned** cross-modal association is CH13's thesis — do not offer it here | `planetar-sat`, `planetar-ontology` (`src/resolve/kinematics.ts`, `GET /trace/:id`) | detector choice below |
| 2–3 | Measured performance (feeds R1, R11) | xView3 holdout score (MR and components) from the Stage 1 run, stated with the split and compared to the published reference, as **evidence the detection method works**. The xView3-trained weights are not the delivered model (CC BY-NC-SA); the delivered detector is CFAR today, or a learned detector retrained on commercially usable data (Stage 2's self-collected Sentinel-1 + AIS pairs) — say which, and when | `planetar-fusion/runs/*/bench/score.json` | **[GAP]** blocked on xView3 download + pod run; a CFAR score on the same holdout would make the comparison honest |
| 3 | Source identification + method (R6, R7) | One worked example: a fused result traced to its Sentinel-1 product and AIS messages in one call; link to the methodology document | `planetar-ontology` `/trace/:id`; methodology doc | **[GAP]** one-call trace demo; buyer-facing method doc |
| 3–4 | Delivery and integration (R2–R4) | REST (Object API), TCP stream (bus), **S3 drop**, **bulk export by time range**, **API keys**; formats; SeaVision ingest per the contact's answer | `planetar-ontology/src/api/server.ts` | **[GAP]** S3, bulk export, auth |
| 4 | Schedule (5) | What is available now (REST/stream, live demo), what lands by date | this file, § Build schedule | outline only |
| 4–5 | Intellectual property (6) | Software GPLv3, public; envelope Apache-2.0; delivered results carry no licence barrier between US agencies and partner nations (R10); **xView3-trained weights are benchmark evidence only (CC BY-NC-SA), not the delivered model** | `../../planetar-fusion/docs/DESIGN.md` licence note | input-feed rights **[GAP]** (FIT risk 2) |
| 5 | Price (4) | Rough order of magnitude for a pilot (Prototype OT): feed for a named area, N months, support | — | `[TODO]` founder |
| 5 | Company viability (7) | Zax Analytics; founder background; open-source record; filed IDEaS bids may be mentioned only as facts, not content | `../planetar-brainstorm/DECISIONS.md` | `[TODO]` market traction |

## Build schedule (proposed — founder to confirm)

Deadline 2027-01-07 16:00 Pacific. Aim to send before the US holiday slowdown.

| Target | Item | Repo | Depends on |
|---|---|---|---|
| now | Send `QUESTIONS-email.md`; request NCAGE | — | founder |
| 2026-11-15 | Stage 1 trained + holdout score (both configs), plus `planetar-sat`'s CFAR scored on the same holdout scenes as the baseline | `planetar-fusion`, `planetar-sat` | xView3 download (founder), RunPod |
| 2026-11-27 | Bulk export by time range + S3 drop + API keys on the Object API | `planetar-ontology` | — |
| 2026-12-04 | One-call source-identification demo + buyer-facing methodology doc | `planetar-ontology`, this workspace | Stage 1 score |
| 2026-12-11 | `THESIS.md` + full brief draft | this workspace | the above; contact's answers |
| 2026-12-18 | Send the brief | — | founder review |

Learned detector in `planetar-sat` (Task 9) is optional for the brief: the benchmark is the
evidence, the CFAR path stays the live feed until the learned path is compared on real scenes.

## Do not claim

- A probability of detection or false-alarm rate that was not measured on stated data.
- Any delivery latency number (the bus benchmark is not a collection-to-delivery figure).
- Classification-level support in the live service (exists only in `planetar-platform`'s core).
- Vessel type (R5): not produced today.
