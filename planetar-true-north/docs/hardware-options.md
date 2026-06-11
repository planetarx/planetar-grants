# COTS Hardware Sourcing — scoping (UNVETTED research targets)

> ⚠️ **Nothing here is selected or verified.** These are *research starting
> points* to investigate, not recommendations or claims. Every spec must be
> confirmed against a current datasheet before it enters any proposal text. Do
> not cite a number from this file in a PRC narrative — cite the datasheet.

## Selection criteria (derived from outcomes)

**Laser rangefinder (must, EO1/EO5; stretch DO2):**
- Eye-safe **Class 1** (typically 1550 nm) — **hard requirement** (EO5).
- Range accuracy ±2 m @ 1 km on vehicle (EO1); stretch ±1 m on human (DO2).
- Update rate supporting ≤1 s latency loop; light enough for the weight budget.
- Low power; UART/serial or MAVLink-friendly output.
- Export status procurable in Canada (Q8).

**Air vehicle (must, EO2/EO4/EO6; DO6/DO7):**
- ≥30 min endurance; 3–4 km operating radius (EO2).
- Integrated drone + payload **≤25 kg** (EO6) → NATO Class I Mini (2–20 kg) or Small (>20 kg).
- Modular payload bay, no structural mod (DO6).
- GNSS-denied autonomy: VIO / INS, obstacle avoidance (EO3/DO7).
- Environmental: 0 °C+ / winds ≤10 m/s / dust (EO4); stretch −20 °C / 15 m/s / precip (DO3).
- **Western / NDAA-compliant origin** (DO8) — **excludes DJI-class**.

**Datalink (DO9):** fibre-optic tether or non-EM-spectrum control option;
remote GCS extension. Note tether-vs-radius tension (Q5).

## Research targets — laser rangefinder modules (VERIFY ALL)

| Family / vendor | Why look | Must confirm |
|---|---|---|
| Jenoptik DLEM / LDM OEM modules | Compact OEM eye-safe LRF line | weight, accuracy@1km, export |
| Safran Vectronix (e.g. PLRF family) | Mil-grade eye-safe LRF | UAV-mountable variant? weight |
| Lightware SF-series (UAV LiDAR/LRF) | Drone-oriented, light, MAVLink | range to 1 km? accuracy grade |
| Bharat / FLIR / other OEM LRF | Alt sources | eye-safe class, origin |

*(List is a starting net — confirm which actually hit ±2 m @ 1 km + Class 1 +
weight. Some "rangefinders" are short-range altimeters, not 1 km target LRFs.)*

## Research targets — small UAS (VERIFY ALL)

| Platform | Why look | Must confirm |
|---|---|---|
| Skydio X10D | NDAA, strong GPS-denied visual autonomy, payload | endurance, payload mass, LRF integration |
| Teledyne FLIR SIRAS | NDAA ISR drone, modular payload | radius, weight budget |
| Quantum Systems (Vector/Trinity) | Western, longer endurance | VTOL vs payload fit |
| Parrot ANAFI USA / AeroVironment | NDAA, established mil use | payload openness for LRF |
| ArduPilot/PX4 custom airframe | Max integration control + VIO | build/test burden for solo founder |

*(DJI explicitly excluded — origin/DO8.)*

## Open hardware questions (→ `08-OPEN-QUESTIONS.md`)
- Q2 sourcing · Q4 GNSS-denied accuracy error budget · Q5 datalink/tether ·
  Q8 export/ITAR · Q9 hardware partner for integration & flight test.

## Next action
Turn the top 2–3 LRF + 2–3 UAS candidates into a **comparison table with real
datasheet figures** (weight / accuracy / endurance / origin / export / price),
then pick a baseline + alternate for the proposal.
