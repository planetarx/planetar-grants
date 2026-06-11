# Decision: NO-BID — True North Precision (W7714-248676/012)

- **Decision:** Do **not** bid this challenge this round.
- **Date:** 2026-05-31.
- **Decided by:** Steven Ness (applicant, Zax Analytics).
- **Forward plan:** wait for / actively scan for other IDEaS (incl. MINERVA) challenges
  that fit planetar's actual strengths; keep this workspace as a reference in case a
  hardware partner later makes Option C viable (see below).

---

## What the challenge is

DND/CAF IDEaS **Competitive Projects** challenge, first under the Canadian Army
**MINERVA Initiative**: *"True North Precision: Low cost drones with laser ranging"* —
cost-effective small UAS with laser rangefinding for target cueing / indirect-fire
support. Full text + transcribed images: [`CHALLENGE.md`](CHALLENGE.md).

Key facts (public record, 2026-05-31):

| | |
|---|---|
| Tender | `W7714-248676/012` (CanadaBuys + MERX notice 22785002827) |
| Proposal deadline | **2026-06-10, 14:00 EDT** (MERX /012; ~10 days out at decision time) |
| Components (standard IDEaS) | 1a TRL 1–3 ≤$250K ≤6 mo · 1b TRL 4–5 ≤$1.5M ≤12 mo · 2 TRL 6–9 ≤$5M |
| Challenge pool | ~$2.1 M total (≈ 7 × ~$300K); per-project guidance ≈ $300K |
| Schedule | mid-point validation 3–4 mo after award; test-ready spring 2027 |
| Eligibility | individuals, academia, NFP, gov, all industry |

## Positioning that was explored

**System integrator:** mount a **COTS eye-safe laser rangefinder** on an **existing
small UAS**, and provide **planetar as the sensor-to-shooter data backbone** (ns
message bus + typed envelope + fusion/tracking + ATAK/STANAG C2 + operator shell).
Full analysis: [`02-STRATEGY.md`](02-STRATEGY.md), [`03-ARCHITECTURE.md`](03-ARCHITECTURE.md),
outcome map [`01-CHALLENGE.md`](01-CHALLENGE.md).

---

## Why no-bid (feasibility assessment)

For a **solo software founder bidding alone, in ~10 days, with no hardware sourced**,
this is a weak fit. Three structural blockers:

1. **TRL mismatch — can't honestly bid 1b.** Component 1b is TRL 4–5, and MC-1
   requires accurately stating current TRL (eligibility is gated by it). The TRL of
   the *integrated* drone + laser + C2 solution is set by its least-mature element +
   the integration — and that solution is **un-sourced, un-integrated, un-flown today
   (TRL ~1–2)**. planetar's software alone is ~TRL 3, but the funded capability is at
   concept stage. The honest lane would be **1a, not 1b**; claiming 1b risks failing a
   mandatory criterion.

2. **The must-pass outcomes are the part planetar can't own.** The **Essential**
   outcomes (EO1 ±2 m @ 1 km, EO2 endurance/range, EO4 environment, EO5 eye-safe
   laser, EO6 ≤25 kg) are **hardware**. planetar's genuine strength maps to **DO4/DO5
   — which are *Desired*, not Essential.** Competitors will be drone/defence-hardware
   firms that already fly and already integrate rangefinders.

3. **Clock + cold start.** ~10 days, nothing sourced, and immediately after submitting
   the sibling /013 bid (2026-05-30). Not enough runway to make the hardware story
   credible.

**What was in favor (for balance):** eligibility includes individuals; the challenge
explicitly funds "Integration onto Existing UAS Platforms"; ~7 awards (not
winner-take-all); and the nanosecond sensor-to-shooter / auditable-fires / ATAK-STANAG
data layer is a real differentiator most drone shops lack. Not enough to overcome the
three blockers under these constraints.

## Options considered

| | Path | Outcome |
|---|---|---|
| **A** | Don't bid this round (revisit if a hardware partner appears) | **CHOSEN** |
| **B** | Bid Component 1a as a concept-definition of the data layer + COTS-integration plan | Truthful + submittable solo, but weak on Essential hardware outcomes |
| **C** | Find a hardware partner/sub and bid 1b as a team | Best fit to the ask; blocked by 10-day partner-sourcing |

## Unconfirmed at decision time

The **CanadaBuys Solicitation Guide** for /012 (Annex B = exact criteria, and which
Components are open) could not be pulled — the Salesforce portal is auth-gated (403).
If /012 turns out to be **1b-only**, that independently rules out a solo bid and
confirms this decision.

---

## Forward-looking: what to pursue instead

planetar is a **software / AI / data-fusion platform**. Bid challenges whose **Essential
outcomes are software/AI**, not hardware platforms. Good-fit signals to scan for:

- Multi-modal / multi-domain **data fusion**; **sensor-to-shooter** or C2 integration.
- **Entity resolution / re-identification**, knowledge graphs, provenance/lineage.
- **Maritime / Arctic / ISR domain awareness**; anomaly detection with uncertainty.
- Real-time, explainable, **edge** AI; human-in-the-loop decision support.
- "Integration / software backbone" framings where hardware is COTS/GFE.

Avoid (or only bid with a hardware partner): challenges whose **Essential** outcomes
are airframes, optics, RF hardware, weapons, or other physical platforms.

**Where to watch:**
- CanadaBuys — `W7714-248676` umbrella (the IDEaS standing CFP; new challenges post here).
- IDEaS Competitive Projects challenges list (canada.ca/defence-ideas).
- Canadian Army **MINERVA Initiative** (this was challenge #1; more expected).
- Contracting / questions: `paidees.apideas@tpsgc-pwgsc.gc.ca`.

**If a hardware partner appears**, Option C re-opens — this workspace already holds the
challenge text, the system-integrator architecture, and the COTS sourcing scoping
([`docs/hardware-options.md`](docs/hardware-options.md)) to move fast.

## Sources

- [Canada.ca — True North Precision](https://www.canada.ca/en/department-national-defence/programs/defence-ideas/element/competitive-projects/challenges/true-north-precision.html)
- [MERX notice — W7714-248676/012](https://www.merx.com/public/supplier/solicitations/notice/22785002827/abstract)
- [Canadian Defence Review — MINERVA launch](https://canadiandefencereview.com/canadian-army-launches-minerva-initiatives-first-innovation-challenge/)
