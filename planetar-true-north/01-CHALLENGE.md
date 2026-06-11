# 01 — Challenge Mapping: outcomes → owners

Maps every **Essential (EO)** and **Desired (DO)** outcome from
[`CHALLENGE.md`](CHALLENGE.md) to who delivers it under the system-integrator
positioning. **Owner** = COTS hardware (to source), planetar software, COTS
autopilot/autonomy, or process.

Legend: ✅ planetar strength · 🟡 partial / shared · ❌ hardware gap (COTS).

## Essential Outcomes (must demonstrate)

| EO | Outcome (abridged) | Owner | Notes |
|---|---|---|---|
| **EO1** | Precision rangefinding ±2 m @ 1 km on vehicle, 10-fig MGRS; updates ≤1 s latency / ≤2 m | ❌ COTS LRF + ✅ planetar geoloc | LRF gives slant range; planetar computes MGRS from range + platform pose; latency/track is planetar's bus |
| **EO2** | Platform: 3–4 km radius (LOS/BVLOS w/ waiver), ≥30 min endurance | ❌ COTS UAS | Drives airframe selection (NATO Class I Mini/Small) |
| **EO3** | Resilience & nav: hold geoloc during GNSS degradation; VO / inertial / RTK fallback | 🟡 COTS autopilot + ✅ planetar fusion | On-airframe VIO/INS; planetar fuses degraded pose into geoloc solution |
| **EO4** | Environmental: 0 °C+, winds ≤10 m/s, dust/smoke (MIL-STD-810 510.5) | ❌ COTS hardware | Selection criterion for airframe + payload |
| **EO5** | Data handling & safety: **Class 1 eye-safe** laser; info handling per **ITSP.10.171** | ❌ LRF (eye-safe) / ✅ planetar (info handling) | Eye-safe = pick Class 1 COTS module; ITSP.10.171 = planetar's data security posture (verify exact CCCS title) |
| **EO6** | Size: integrated drone + payload **≤ 25 kg** | ❌ COTS integration | Weight budget = airframe + LRF + compute; constrains selection |
| **EO7** | Prototype ready for Final Capability Assessment **May 2027** | process | Drives `07-TIMELINE.md` |

> **Bid risk:** EO1/EO2/EO4/EO6 are the must-pass core and they are hardware. The
> bid is credible **only** with a concrete COTS shortlist that meets these specs
> (see `docs/hardware-options.md`). Do not advertise accuracy/endurance numbers
> we haven't sourced to a real datasheet.

## Desired Outcomes (should include)

| DO | Outcome (abridged) | Owner | Notes |
|---|---|---|---|
| **DO1** | Target designation: STANAG 3733, up to Class 4 designator | ❌ COTS payload | Class 4 designator ≠ eye-safe; likely **out of scope** for low-TRL eye-safe-only essential — flag |
| **DO2** | Advanced rangefinding ±1 m on human-sized @ 1 km | ❌ COTS LRF (higher grade) | Tighter than EO1; depends on LRF beam divergence/grade |
| **DO3** | Environmental: −20 °C+, winds ≤15 m/s, precip 4 mm/m²/hr | ❌ COTS hardware | Tighter than EO4 |
| **DO4** | **Sensor-to-shooter:** real-time telemetry + **ATAK**; STANAG **4586** (payload control), **4609** (FMV); impact adjustment for fires | ✅ **planetar core** | Bus + envelope + shell → CoT/TAK bridge; this is the flagship demo |
| **DO5** | High-speed tracking ≤20 m/s, predictive smoothing, **auto track handoff to ground C2** | ✅ **planetar core** | Fusion/tracking + entity-graph track identity |
| **DO6** | Modular payload bay (swap sensors/batteries, no structural mod) | ❌ COTS airframe | Selection criterion |
| **DO7** | Autonomous/semi-auto nav in GNSS-denied (VO, inertial); front obstacle avoidance | 🟡 COTS autopilot + ✅ planetar | Native platform autonomy + planetar mission/track layer |
| **DO8** | **Origin:** countries of origin for critical systems clearly identified | ✅ planetar (provenance) | Western/NDAA-compliant stack; rules out DJI-class; planetar's auditable-spine ethos |
| **DO9** | EM resilience: fibre-optic / non-EM control & data GCS→air; remote GCS extension | 🟡 datalink hardware + planetar | Datalink is hardware; planetar rides on top and logs link state |

## Standards & specs to satisfy (consolidated)

| Ref | Applies to | Owner | Verify |
|---|---|---|---|
| MGRS 10-figure | Target geolocation output | planetar | — |
| STANAG 4586 | UAS control segment (payload control) | planetar bridge | interface scope |
| STANAG 4609 | Full-Motion Video metadata | planetar bridge | which edition |
| STANAG 3733 | Laser designation | COTS designator (DO) | scope in/out |
| MIL-STD-810 Method 510.5 | Sand & dust | COTS hardware | datasheet evidence |
| ITSP.10.171 | Information handling | planetar | ❓ confirm exact CCCS/CSE title & scope |
| Eye-safe **Class 1** | Laser rangefinder | COTS LRF | datasheet |
| ATAK / CoT / TAK Server | Ground C2 integration | planetar | plugin vs server bridge |
| NDAA / origin | Whole stack | sourcing | DO8 driver |

NATO UAS class definitions (Class I Micro/Mini/Small, Class II Tactical) are in
[`CHALLENGE.md`](CHALLENGE.md) — the ≤25 kg limit (EO6) puts us in **Class I
Mini (2–20 kg)** or **Small (>20 kg)** territory.
