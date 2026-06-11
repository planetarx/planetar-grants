# Decision: NO-BID — ISC Testing Stream TS13 (EN578-26ISC1)

- **Decision:** Do **not** bid this solicitation.
- **Date:** 2026-06-01.
- **Decided by:** Steven Ness (applicant, Zax Analytics).
- **Forward plan:** keep effort on IDEaS CH13 (deadline 2026-06-02); monitor the
  ISC **Challenge Stream** (TRL 1–6) for a future maritime-MDA / data-fusion
  problem statement, which planetar could credibly enter at Phase 1/2.

---

## What the opportunity is

**Innovative Solutions Canada — Testing Stream**, solicitation **EN578-26ISC1**
("Solicitation of Offers TS13"), forwarded by D. Huang ([`idea.md`](idea.md)).
Full research note: [`CHALLENGE.md`](CHALLENGE.md).

Key facts (public record, 2026-06-01):

| | |
|---|---|
| Solicitation | `EN578-26ISC1` (CanadaBuys notice `cb-313-32454734`) |
| Published / closes | 2026-05-27 / **2026-06-17 14:00 EDT** |
| Mechanism | **Contract / procurement** (buy-to-test), not a grant |
| Max per contract | **$2.3M CAD** (taxes/shipping/travel extra); $20M pool; 12-mo term |
| **Required TRL** | **7–9** — "ready (form, fit, function) for operational testing" |
| Themes | Trust & Verification · **Enhancing Capabilities in Complex Environments** · Quantum |
| Eligibility | Canadian Offeror, ≥80% Canadian content, own-IP/exclusive CA licence, pre-commercial, 50% FTE/wages/execs in Canada |

The planetar-adjacent theme is **Enhancing Capabilities in Complex
Environments** (sensing/comms in remote, maritime, Arctic/coastal settings).

## Positioning that was explored

planetar as the **multi-sensor data fabric** for maritime/Arctic domain
awareness — ns message bus + typed envelope + AIS/SAR/EO/hydrophone/RF fusion +
operator shell — mapped against the theme's seven sub-challenges (docked RPAS,
Arctic/coastal RPAS, extended-range ISR RPAS, ship-maintenance robotics,
multi-function AESA radar, submarine underwater comms, UAS sensor-ranging).

---

## Why no-bid (feasibility assessment)

Two structural blockers, either of which is disqualifying:

1. **TRL gate — can't honestly clear SC2.** The Testing Stream requires a
   **TRL 7–9** prototype ready "form, fit, and function" for operational
   testing. Planetar's bus + zmesg + UI + AIS ingest is early-stage R&D
   (**TRL 1–3** — the band pitched for IDEaS CH13 Component 1a). Screening
   criterion **SC2** validates operational readiness at TRL 7+; we cannot claim
   it truthfully. This alone ends it.

2. **No software slot in the problem statements.** The theme reads like
   planetar's wheelhouse, but all **seven** sub-challenges are **hardware
   platform deliverables** (drones, ship robotics, radar apertures, submarine
   comms). The nearest adjacencies — #2 "autonomous surface/underwater platforms
   with multi-domain integration" and #3 ISR "payload/software integration" —
   still require delivering the flying/floating platform at TRL 7, not just the
   data layer. There is no pure data-fusion / MDA-shell statement to enter.

**What was in favor (for balance):** eligibility otherwise fits (Canadian
Offeror, ≥80% Canadian content, own-IP, 50% Canadian presence); ~$20M pool with
multiple awards; and the theme is genuinely in planetar's domain. Not enough to
overcome a hard TRL gate with no matching problem statement.

## Options considered

| | Path | Outcome |
|---|---|---|
| **A** | Don't bid; stay on CH13; watch the Challenge Stream | **CHOSEN** |
| **B** | Bid the data layer against sub-challenge #2/#3 | Fails SC2 (TRL) and still owes hardware at TRL 7 |
| **C** | Team with a TRL-7 RPAS/ship-robotics prime, supply the data fabric | Conceivable, but no partner sourced and not worth diverting from the 2026-06-02 CH13 deadline |

---

## Forward-looking: what to pursue instead

planetar is a **software / AI / data-fusion platform** at **TRL 1–3**. The
matching ISC vehicle is the **Challenge Stream** (TRL 1–6; Phase 1 ≤$150K / 6 mo
feasibility, Phase 2 ≤$1M / 2 yr prototype) — *not* the Testing Stream. Same
early-TRL band as IDEaS CH13, which remains the better-matched live opportunity.

Good-fit signals to scan for (Challenge Stream or future IDEaS):

- Multi-modal **data fusion**; **maritime / Arctic / ISR domain awareness**.
- Entity resolution / re-identification, anomaly detection with uncertainty.
- Real-time, explainable, human-in-the-loop decision support; "software backbone"
  framings where hardware is COTS/GFE.

Avoid (or bid only with a hardware partner): statements whose deliverable is an
airframe, ship robot, RF aperture, or other physical platform at TRL 7+.

**Where to watch:**
- ISC **Challenge Stream** — https://ised-isde.canada.ca/site/innovative-solutions-canada/en/challenges
- ISC **Testing Stream** open calls (future themed rounds) — https://ised-isde.canada.ca/site/innovative-solutions-canada/en/testing-stream-open-calls-innovative-prototypes
- Questions / contracting: TPSGC.PASICVoletessai-APISCTestingStream.PWGSC@tpsgc-pwgsc.gc.ca

## Sources

- [ISED — Enhancing capabilities in complex environments](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/enhancing-capabilities-complex-environments)
- [CanadaBuys — TS13 / EN578-26ISC1](https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-313-32454734)
- [ISED — Testing Stream for innovators](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/testing-stream)
- [ISED — Challenge Stream (TRL 1–6, Phase 1/2)](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/challenges)
