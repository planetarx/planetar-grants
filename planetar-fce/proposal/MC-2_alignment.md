# MC-2 — Alignment to the challenge

> **Field cap:** 3,000 characters. **Pass/fail.** Must show the solution addresses CH14.
> Traceability source: [`../01-CHALLENGE.md`](../01-CHALLENGE.md) (EO1–EO6). Keep consistent with PRC-6.
> CH13 analogue: `../../planetar/proposal/MC-2_alignment.md`.

## Draft (skeleton)

Open with the CH14 ask in its own words (FCE = compliance-by-design enforcement at the
fusion chokepoint), then walk **EO1–EO6** showing each is met by a built primitive + a
defined 1a build:

- **EO1** modular AI component enforcing policy during ≥2-sensor fusion → broker hook.
- **EO2** machine-readable policy, ≥2 modalities, Network domain, ≥Protected B → ODRL + class/domain fields.
- **EO3** programmatic, no human approval → synchronous check in publish path.
- **EO4** provenance records (source/class/ts/domain) → `zmesg` + additive fields.
- **EO5** audit logs (permit/restrict/downgrade/segregate + dispositions) → WAL record type.
- **EO6** exportable ingestion→output lineage → WAL replay + ontology + export format.

Close: demo domain = **Maritime Domain Awareness** (CH14's named example); sovereign
Canadian IP fills the gap CH14 states.

## TODO
- [ ] One sentence per EO, each ending in concrete demo evidence (see 01 table "Demo evidence").
- [ ] Verbatim-check EO wording vs. `../CH14-challenge.txt` lines 57–77.

## Char-count budget
Target ≤ 2,950.
