# 02 — Strategy: the system-integrator pitch

## The wedge (from the challenge's own framing)

The challenge names a **mid-tier capability gap**: cheap quadcopters lack the
geolocation precision for sensor-to-shooter integration; high-end Class 2 systems
are too costly/export-restricted to field widely. DND wants *affordable, durable
ISR drones that deliver precise rangefinding and target cueing under contested
EM conditions* — initially to help **mortar/artillery observers make better
calls-for-fire from protected positions.**

The hard part is rarely the laser itself — eye-safe rangefinder modules are COTS.
The hard part is **turning a range measurement into a trusted, timely, shareable
fires solution**: geolocating it, tracking it, deconflicting it, adjusting fire
from observed impact, and pushing it into ATAK/C2 — fast, auditable, and resilient
when GNSS and the EM spectrum are degraded. **That data-to-decision layer is what
planetar is.**

## The pitch (one paragraph)

> We integrate a **COTS eye-safe laser rangefinder** onto an **existing
> low-cost small UAS** and bind it to **planetar — a nanosecond message bus,
> typed envelope, fusion/tracking engine, and operator shell** — to deliver a
> low-cost precision sensor-to-shooter capability. The drone + laser produce the
> raw range; planetar converts it to a 10-figure MGRS target, maintains the
> track with predictive smoothing, re-identifies it across passes, computes
> fire adjustment from observed impact, and delivers it into **ATAK / ground C2
> via STANAG 4586/4609** — with a write-ahead-logged, auditable record of every
> observation-to-fire decision.

## Why planetar is the right backbone (verifiable, not marketing)

- **Latency headroom.** A real-time fires loop needs deterministic, low-latency
  message movement. planetar-broker measured **SHM p50 80–140 ns / p99 400–900 ns**
  (conservative, brackets four runs) — orders of magnitude under the ≤1 s update
  latency the challenge asks for (EO1), leaving budget for sensing + comms.
- **Typed, correlated envelope (zmesg).** UUIDv7 + ns timestamps + correlation/
  causation IDs give a first-class **observation → track → call-for-fire → impact
  → adjustment** chain — exactly the provenance a fires record needs.
- **Track identity / re-ID (doibio).** The entity-graph identity-resolution
  architecture (applicant is a **named inventor on US Patent 10,936,582**)
  re-identifies and deconflicts target tracks across passes — directly serving
  DO5 (handoff) and high-tempo tracking.
- **Operator shell (planetar-ui).** A working 4-pane real-time shell already
  bridged to the bus over WebSocket; the ATAK/CoT bridge is an extension of an
  existing pattern, not a from-scratch UI.
- **Provenance culture (DO8).** Western/NDAA-sourced stack with explicit
  country-of-origin documentation for every critical component — the same
  auditable-spine discipline carried over from planetar.

## What we explicitly do NOT claim

- We do **not** build the airframe or the laser. Essential hardware outcomes
  (EO1 accuracy, EO2 endurance, EO4 environment, EO6 weight) are met by
  **selected COTS hardware**, evidenced by datasheets, and proven through
  planetar integration.
- We do **not** advertise rangefinding/endurance numbers until they trace to a
  real datasheet of a sourced module (see `docs/hardware-options.md`).
- Class 4 **designation** (DO1) is likely beyond an eye-safe, low-TRL scope —
  treat as a desirable stretch, not a commitment (confirm in open questions).

## Fit with low-TRL / Concept-Definition stage

At Concept-Definition stage the deliverable is a **proven concept and integrated
data fabric**, not a fielded, hardened weapon system. A SITL/bench + short flight
demonstration of the **full observation-to-C2 loop** (COTS LRF on a COTS drone →
planetar geoloc/track → ATAK) is an honest, achievable target for the budget and
the May 2027 assessment — and it puts our genuine strength (the data layer) at
the center of what gets demonstrated.

## Risks (carried to `08-OPEN-QUESTIONS.md`)

1. **Hardware credibility** — bid fails if COTS shortlist doesn't hit EO1/EO2/EO6.
2. **Solo-founder + hardware** — integration/test load; may need a hardware sub.
3. **GNSS-denied geoloc accuracy** — ±2 m @ 1 km under degraded pose is the
   technical crux; depends on COTS VIO/INS quality + planetar fusion.
4. **Export/ITAR on LRF** — eye-safe military-grade rangefinders may be controlled.
5. **Rubric unknown** — exact scored criteria/page limits not yet retrieved.
