# Decision: NO-BID — MINERVA 2026 hardware-platform challenges (Arctic UAS `EN578-24ISC4/95` + four siblings)

- **Decision:** Do **not** bid the five MINERVA challenges whose Essential outcomes are an
  uncrewed air or ground **vehicle**: Arctic Uncrewed Air System, Intelligence Surveillance and
  Reconnaissance UAS, Uncrewed Air System for Cargo/Munition Drop, Uncrewed Ground System for
  Surveillance and Reconnaissance, Uncrewed Ground System for Tactical Cargo Movement.
- **Date:** decided **2026-09-23** by Steven Ness (applicant, Zax Analytics), 31 hours before the
  Arctic UAS close; recorded 2026-09-29.
- **Forward plan:** the sixth MINERVA call, **Uncrewed Aircraft System Deconfliction**
  (`EN578-24ISC4/94`, closes **2026-10-21 14:00 EDT**), is the first with all-software Essential
  outcomes. It gets its own screen in [`FIT.md`](FIT.md); this record does not decide it.

---

## What the opportunities are

The Canadian Army's **MINERVA Initiative** (led by the Canadian Army Land Warfare Centre; launched
December 2025) released six challenges through **Innovative Solutions Canada (ISC) Call 004**
between 2026-08-13 and 2026-09-23. Forwarded by D. Huang ([`idea.md`](idea.md), two of the six).
Full research note: [`CHALLENGE.md`](CHALLENGE.md).

Key facts common to all six (public record, verified 2026-09-23 and 2026-09-29):

| | |
|---|---|
| Vehicle | **ISC Challenge Stream, Phase 2 only** (prototype development); direct entry at Phase 2 is allowed |
| Mechanism | **Contract** (procurement), not a grant |
| Required TRL | **5–9** — mandatory screening question 2; "TRL 4 or below" = fail |
| Award | up to **$500,000 CAD** each, ~5 contracts per challenge, up to **15 months**; demo travel to Suffield, AB |
| Eligibility | for-profit, incorporated in Canada, ≤499 FTE, 50 % Canadian wages / FTEs / senior executives, R&D in Canada — **Zax Analytics passes** |
| Evaluation | mandatory Q1a (all Essential Outcomes), Q2 (TRL 5–9 evidence), Q3a (innovation); then 130 points, 65 to pass |

The five hardware calls:

| Challenge | Solicitation / notice | Closed |
|---|---|---|
| Arctic Uncrewed Air System | `EN578-24ISC4/95` · CanadaBuys `cb-409-31548836` | 2026-09-24 |
| Uncrewed Ground System for Surveillance and Reconnaissance | CanadaBuys `cb-380-1799399` | 2026-09-10 |
| Intelligence Surveillance and Reconnaissance UAS | *(solicitation number not captured)* | 2026-09-21 |
| Uncrewed Ground System for Tactical Cargo Movement | `EN578-24ISC4/97` · CanadaBuys `cb-429-57557756` | 2026-09-21 |
| Uncrewed Air System for Cargo/Munition Drop | CanadaBuys `cb-979-47075586` | **2026-10-05** (still open at recording) |

## Positioning that was explored

planetar as the **ground-control-station data layer**: every one of the five calls lists, under
*Additional* outcomes, a GCS with real-time MGRS position, orientation, camera aim point,
full-motion video, battery state, mission-planning simulation, GNSS waypoint navigation, and a
**Tactical Assault Kit (TAK) interface for position-location and target reports** — plus, in
Additional Outcome 9, a component-origin attachment that names *Software* as a critical component.
That is where the bus, envelope, entity graph, and shell would sit.

---

## Why no-bid (feasibility assessment)

Two structural blockers, either one disqualifying — the same two screens that killed
[`../planetar-true-north`](../planetar-true-north/DECISION-no-bid.md) (MINERVA challenge #1) and
[`../planetar-innovation`](../planetar-innovation/DECISION-no-bid.md) (ISC Testing Stream TS13):

1. **Mandatory Q1a — the Essential Outcomes are the vehicle.** Each call requires the proposal to
   meet *every* Essential Outcome, and those are the complete platform: air vehicle or ground
   vehicle, sensor payload, GCS, radio, battery and charger, remote antenna, with environmental,
   range, endurance, mass, and sensor-recognition specifications (Arctic UAS: −40 °C to +40 °C,
   20 km radius, 90 min, ≤25 kg, Johnson-criteria recognition). planetar's genuine fit is entirely
   under *Additional* outcomes, which are worth **10 of 130 points** in total.
2. **Mandatory Q2 — TRL 5–9 for that system.** Zax has no aircraft or ground vehicle. Declaring
   TRL 5 for a system that does not exist would be a false statement in a federal procurement,
   and the workspace's honest-TRL rule forbids it.

**What was in favor (for balance):** eligibility fits cleanly (Zax passes every ISC test); five
awards per challenge; every call names the TAK/GCS software layer explicitly; the Arctic UAS
notice listed seven businesses that registered interest in partnering. None of this moves a
hardware Essential or a TRL gate.

## Options considered

| | Path | Outcome |
|---|---|---|
| **A** | Don't bid the hardware calls; screen the Deconfliction call on its own merits | **CHOSEN** (2026-09-23) |
| **B** | Join a Canadian UAS/UGS prime as the GCS/TAK software subcontractor (the prime files) | Viable in principle; not pursued — 31 h to the Arctic UAS close, no prime relationship in hand, founder chose to spend the hours on the software call |
| **C** | Truthful solo filing declaring TRL ~3 for a planetar GCS plus an unsourced airframe | Screened out at Q2 by construction; wastes evaluator goodwill |

---

## Corrections to the standing watch

- **MINERVA is not an IDEaS lane this cycle.** `../planetar-brainstorm/03-defence-dualuse.md` and
  `06-shortlist-and-calendar.md` (row 9) assume MINERVA challenges arrive as IDEaS Competitive
  Projects with Component 1a (TRL 1–3, ≤$250K) and individual eligibility. True for challenge #1
  (True North, W7714-248676/012); **false for all six 2026 calls**, which run through ISC Call 004
  at Phase 2 (TRL 5–9, $500K, incorporated SMEs only). MINERVA's own page states the split: IDEaS
  for earlier-stage, ISC for later-stage toward procurement.
- **The software-essential MINERVA call the prior no-bids were waiting for has now appeared**
  (UAS Deconfliction). The remaining screen is TRL, not deliverable type — see
  [`FIT.md`](FIT.md).

## Sources

- [ISED — MINERVA Initiative – Arctic Uncrewed Air System](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/minerva-initiative-arctic-uncrewed-air-system) (modified 2026-09-15; full evaluation grid)
- [CanadaBuys — Arctic UAS `cb-409-31548836`](https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-409-31548836) (`EN578-24ISC4/95`; amendments 001–004, last 2026-09-17)
- [ISED — Uncrewed Ground System for Surveillance and Reconnaissance](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/minerva-initiative-uncrewed-ground-system-surveillance-and-reconnaissance) · [ISED — ISR UAS](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/minerva-initiative-intelligence-surveillance-and-reconnaissance-uncrewed-air-system) · [ISED — Cargo/Munition Drop UAS](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/minerva-initiative-uncrewed-air-system-cargomunition-drop) · [CanadaBuys — Tactical Cargo UGS `cb-429-57557756`](https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-429-57557756)
- [Canada.ca — MINERVA Initiative innovation challenges](https://www.canada.ca/en/army/services/army-modernization/minerva-initiative/innovation.html) · [Canada.ca — MINERVA Initiative](https://www.canada.ca/en/army/services/army-modernization/minerva-initiative.html) (IDEaS-vs-ISC split)
- [The Maple Leaf, 2026-09-16 — From the Arctic to the front line](https://www.canada.ca/en/department-national-defence/maple-leaf/defence/2026/09/from-arctic-to-front-line-army-industry-join-forces-minerva.html)
- [Canadian Defence Review, 2026-09-21 — Six MINERVA challenges](https://canadiandefencereview.com/canadian-army-launches-six-minerva-challenges-as-dnd-seeks-autonomous-mine-countermeasures-vessel/)
- [CanadaBuys — ISC Call for Proposals 004 `EN578-24ISC4`](https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-331-17030872) (eligibility, Phase 1/2 entry)
