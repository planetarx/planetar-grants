# Innovative Solutions Canada — Testing Stream (TS13)

Research note for the opportunity forwarded by D. Huang (`idea.md`). Verified
against the official ISED challenge page and the CanadaBuys solicitation on
2026-06-01.

## The opportunity at a glance

| Field | Value | Source |
|---|---|---|
| Program | **Innovative Solutions Canada (ISC) — Testing Stream** | ISED |
| Solicitation | **EN578-26ISC1** — "Solicitation of Offers TS13" | CanadaBuys `cb-313-32454734` |
| Published | 2026-05-27 | CanadaBuys |
| **Closes** | **2026-06-17 14:00 EDT** | CanadaBuys |
| Max per contract | **$2.3M CAD** (taxes/shipping/travel extra) | ISED challenge page |
| Total pool | $20M across all resulting contracts | CanadaBuys |
| Contract term | 12 months | CanadaBuys |
| Mechanism | **Contract / procurement** (buy-to-test), not a grant | ISED |
| Contracting authority | TPSGC.PASICVoletessai-APISCTestingStream.PWGSC@tpsgc-pwgsc.gc.ca | CanadaBuys |

Three themed problem statements in TS13:
1. Trust and Verification in Digital Government
2. **Enhancing Capabilities in Complex Environments** ← the planetar-adjacent one
3. Quantum Technologies

## "Enhancing Capabilities in Complex Environments" — the seven sub-challenges

Sponsors: RCMP, DND/CAF, RCN, CCG. **Required TRL: 7 minimum** — "prototype
system ready (form, fit, and function) for testing in an appropriate
operational environment."

1. **Docked RPAS & remote ops** — autonomous launch/recover/recharge from fixed
   or mobile docks; secure remote operation. *(RCMP)*
2. **Arctic & coastal RPAS** — −25 °C Arctic / −10 °C + 48 h saltwater coastal;
   de-icing, condensation control, cold endurance; EO/IR/low-light SAR payloads;
   autonomous surface/underwater platforms with multi-domain integration.
   *(RCMP, DND/CAF)*
3. **Extended-range ISR RPAS** — ≥4 h endurance, BVLOS, mandatory SATCOM uplink,
   secure remote ops, aircraft/payload/software ISR integration. *(RCMP, DND/CAF)*
4. **Automated shipbuilding & maintenance** — hull inspection, surface cleaning,
   confined-space welding, magnetic crawlers, laser ablation, additive
   manufacturing, robotics. *(RCN, CCG)*
5. **Multi-Function RF (MFRF)** — consolidate radar / comms / EW / SIGINT into
   shared AESA apertures; reduce topside clutter and EMI. *(RCN)*
6. **Underwater communications** — submerged submarine comms; JANUS (STANAG
   4748), PHORCYS waveforms, STANAG 1481/1390 interop. *(DND/CAF)*
7. **UAS for ranging** — controlled EO/IR + laser signatures for ship-sensor
   test/calibration at sea. *(RCN)*

## Eligibility (Testing Stream)

- **Canadian Offeror** with a permanent place of business in Canada.
- **≥80% Canadian content** of financial-proposal costs.
- **Own the IP** or hold an exclusive Canadian licence; no infringement.
- **Pre-commercial** — not openly available / not previously sold commercially.
- Canadian-presence tests: ≥50% FTEs, ≥50% wages, ≥50% senior execs in Canada.
- MC1: innovation not previously awarded under BCIP, CICP, or ISC Testing Stream.

## Evaluation (out of ~84 pts; 60 to conditionally qualify)

- **MC** (pass/fail): not previously awarded.
- **SC** (pass/fail): meets ISC innovation definition; TRL 7+ operational
  readiness; risk/cert/safety clearance; addresses a selected problem statement.
- **PS** (0–40): advance on state of the art (PS1); IP strategy (PS2).
- **PR** (0–44): EDI benefits (PR1); commercialization strategy (PR2).
- Pathway to Commercialization (PTC): TRL 9 SMEs can pursue follow-on commercial
  contracts within 12 months.

## Fit verdict for planetar — ⚠️ likely NO-BID on Testing Stream

**Blocking gate: TRL.** Testing Stream requires **TRL 7–9** (a prototype ready,
"form, fit, and function," for operational testing). Planetar's bus + zmesg +
UI + AIS ingest is early-stage R&D (**TRL 1–3** — the level it is pitched at for
IDEaS CH13 Component 1a). We cannot honestly claim TRL 7. SC2 screens this out.

**Thematic adjacency without a slot.** The theme (maritime/Arctic/coastal
sensing, multi-domain awareness) is squarely planetar's wheelhouse — dark-vessel
detection fusing AIS/SAR/EO/hydrophone/RF. But all seven *actual* sub-challenges
are **hardware-platform deliverables** (drones, ship robotics, AESA radar,
submarine comms). None is a pure software / multi-sensor-fusion / MDA-shell
problem statement that planetar's stack would drop into. Closest is #2's
"autonomous surface/underwater platforms with multi-domain integration" and #3's
ISR "payload/software integration" — but both require us to deliver the flying
or floating platform at TRL 7, not just the data fabric.

**Where ISC *would* fit.** The right ISC vehicle for a TRL 1–3 software platform
is the **Challenge Stream** (TRL 1–6; Phase 1 ≤$150K / 6 mo feasibility, Phase 2
≤$1M / 2 yr prototype) — not the Testing Stream. That is the same early-TRL band
as IDEaS CH13, which remains the better-matched live opportunity.

**Recommendation:** treat TS13 as out of scope on TRL grounds (mirrors the
`planetar-true-north` no-bid). Don't divert effort from the IDEaS CH13 deadline
(2026-06-02). Optionally monitor the ISC **Challenge Stream** for a future
maritime-MDA / data-fusion problem statement, which planetar could credibly
enter at Phase 1/2.

## Sources

- ISED — Enhancing capabilities in complex environments:
  https://ised-isde.canada.ca/site/innovative-solutions-canada/en/enhancing-capabilities-complex-environments
- CanadaBuys — TS13 solicitation EN578-26ISC1:
  https://canadabuys.canada.ca/en/tender-opportunities/tender-notice/cb-313-32454734
- ISED — Testing Stream for innovators:
  https://ised-isde.canada.ca/site/innovative-solutions-canada/en/testing-stream
- ISED — Challenge Stream (TRL 1–6, Phase 1/2):
  https://ised-isde.canada.ca/site/innovative-solutions-canada/en/challenges
