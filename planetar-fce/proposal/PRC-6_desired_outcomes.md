# PRC-6 — Desired outcomes (15 pts)

> **Field cap:** 3,000 characters. **Tightest section historically** — budget hard.
> Traceability: [`../01-CHALLENGE.md`](../01-CHALLENGE.md) DO1–DO4. CH13 analogue: `../../planetar/proposal/PRC-6_desired_outcomes.md`.

## Draft (skeleton)

Address each CH14 Desired Outcome with planetar's existing strength:
- **DO1 real-time at tactical speed** → ns-scale chokepoint; enforcement overhead measured
  and reported; far under tactical-decision threshold.
- **DO2 adaptable policy without restart** → ODRL policies are data → hot-reload; demo a
  live policy swap mid-session.
- **DO3 SWaP / edge** → ~1.2k-LOC dependency-light C engine; the Tactical-Edge-Dismounted
  example (ruggedized laptop). State compute envelope.
- **DO4 explainability + controlled override** → `planetar-ui` causation drill-down surfaces
  *why* a decision was made; override = an authority action logged immutably to WAL.

## TODO
- [ ] One crisp sentence per DO with concrete demo evidence — this is the tightest field, no padding.
- [ ] Re-measure char count at T-3 (CH13 PRC-6 was the binding one at ~2,997).

## Char-count budget
Target ≤ 2,970 (treat as the binding field).
