# 03 — Reference Architecture (True North adaptation)

planetar's 5-layer maritime stack (envelope → bus → detectors → entity graph →
shell) is retuned into a **sensor-to-shooter loop** with a hardware layer added
below it. The flow is **range → geolocation → track → fire solution → C2**, with
an auditable record at every hop.

```
        ┌─────────────────────────────────────────────────────────────┐
  L6    │  C2 / SHELL    planetar-ui operator shell + ATAK/CoT bridge   │
        │                STANAG 4586 (payload ctrl) · 4609 (FMV)        │  ✅ planetar
        ├─────────────────────────────────────────────────────────────┤
  L5    │  ENTITY GRAPH  target-track identity / re-ID / deconflict     │  ✅ doibio
        │                (US Patent 10,936,582 — applicant named inv.)  │
        ├─────────────────────────────────────────────────────────────┤
  L4    │  FUSION /      range+pose→MGRS geoloc · predictive track ·    │  ✅ planetar
        │  TRACKING      GNSS-degraded fusion · fire-impact adjustment  │  + 🟡 autopilot
        ├─────────────────────────────────────────────────────────────┤
  L3    │  BUS           planetar-broker SHM/TCP/UDP · WAL (audit)      │  ✅ planetar
        │                p50 80–140 ns / p99 400–900 ns                 │
        ├─────────────────────────────────────────────────────────────┤
  L2    │  ENVELOPE      zmesg typed msgs: RangeFix · TargetGeo ·       │  ✅ zmesg
        │                Track · Telemetry · FMVRef · CallForFire       │
        ├─────────────────────────────────────────────────────────────┤
  L1    │  DATALINK      air↔ground link; DO9 fibre-optic / non-EM      │  🟡 hardware
        ├─────────────────────────────────────────────────────────────┤
  L0    │  AIR VEHICLE + PAYLOAD (COTS, to source)                      │  ❌ COTS
        │   • small UAS (NATO Class I Mini/Small, ≤25 kg integrated)    │
        │   • eye-safe Class 1 laser rangefinder module                 │
        │   • onboard compute + autopilot (VIO/INS, GNSS-denied)        │
        └─────────────────────────────────────────────────────────────┘
```

## Layer responsibilities

**L0 — Air vehicle + payload (COTS, ❌ to source).** Existing Western/NDAA small
UAS + eye-safe LRF + autopilot/compute. Owns EO1 (raw range), EO2 (endurance/
radius), EO4 (environment), EO6 (weight), DO6 (modular bay), DO2/DO3 (higher-grade
variants). Selection criteria in `docs/hardware-options.md`.

**L1 — Datalink (🟡 hardware).** Air-ground control + data. DO9 wants fibre-optic
tether or non-EM-spectrum means + remote GCS extension — a **hardware/link**
choice; planetar rides on top of whatever link is chosen and logs link health.

**L2 — Envelope (zmesg, ✅).** Define True North message types:
`RangeFix` (slant range, beam, t), `PlatformPose` (lat/lon/alt/att, GNSS quality),
`TargetGeo` (MGRS 10-fig + CEP), `Track` (id, kinematics, smoothing state),
`FMVRef` (4609 metadata pointer), `CallForFire`, `ImpactObs`, `FireAdjust`. Each
carries UUIDv7 + ns timestamp + correlation/causation → full fires audit chain.

**L3 — Bus (planetar-broker, ✅).** Moves envelopes in the GCS and across the link
at ns latency; **WAL = the auditable observation-to-fire record** (after-action,
accountability). Re-benchmark on target GCS hardware before citing new numbers.

**L4 — Fusion / tracking (✅ planetar + 🟡 autopilot).** The technical crux:
- `RangeFix + PlatformPose → TargetGeo` (range/bearing/own-position → MGRS).
- Predictive track smoothing; targets ≤20 m/s (DO5).
- **GNSS-degraded geolocation** (EO3): fuse VIO/INS pose when GNSS is poor.
- **Fire-impact adjustment** (DO4): `ImpactObs → FireAdjust` correction.

**L5 — Entity graph (doibio, ✅).** Track identity / re-ID across passes,
deconfliction, handoff continuity (DO5). The identity-resolution architecture
from the patent, applied to target tracks instead of vessels.

**L6 — C2 / shell (planetar-ui, ✅).** Operator shell + **ATAK/CoT bridge**;
STANAG 4586 payload control, 4609 FMV. Surfaces calls-for-fire and **hands tracks
off to ground C2** (DO5). This is the demonstrable flagship of the bid.

## Demonstration target (low-TRL honest scope)

End-to-end **observation-to-C2 loop**: COTS LRF on COTS drone produces a range →
planetar geolocates to 10-fig MGRS → forms/maintains track → pushes a call-for-
fire into ATAK → ingests an impact observation → emits a fire adjustment — first
in SITL/bench, then a short live flight for the May 2027 assessment.

## Reuse vs. new

| | Reuse from planetar | New for True North |
|---|---|---|
| Bus, envelope, shell, entity graph | ✅ core code | message types, ATAK bridge |
| Detectors (maritime AIS/SAR/EO) | ❌ not applicable | range→geo, track, fire-adjust |
| AIS ingest microservice | pattern only | telemetry/range ingest from autopilot |
