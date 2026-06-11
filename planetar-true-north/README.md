# Planetar True North — IDEaS "True North Precision" Proposal Workspace

> 🛑 **NO-BID (decided 2026-05-31).** We are **not** bidding `W7714-248676/012` this
> round — wrong fit for a solo software founder (Essential outcomes are hardware; the
> integrated solution is TRL ~1–2, not the 1b TRL 4–5 it would need; ~10 days, no
> hardware sourced). Full rationale: [`DECISION-no-bid.md`](DECISION-no-bid.md).
> Watching for better-fit (software/AI/fusion) IDEaS & MINERVA challenges instead.
> Workspace kept as reference if a hardware partner later re-opens Option C.

Working area for the DND/CAF IDEaS challenge **"True North Precision: Low cost
drones with laser ranging"** (BOREALIS-supported). Full challenge text +
transcribed images: [`CHALLENGE.md`](CHALLENGE.md). Source capture: [`idea/`](idea/).

> **This is a new, separate contract** from the CFP6 Challenge 13 "Multi-modal
> AI" bid (that one is already submitted; workspace at `../planetar/`). We are
> **adapting the planetar platform** to this challenge as a *system integrator*,
> not re-using the maritime pitch.

## Positioning (decided 2026-05-31)

Bid as a **system integrator**: mount a **COTS eye-safe laser rangefinder** on an
**existing small UAS**, and provide **planetar as the precision sensor-to-shooter
data backbone** — nanosecond message bus + typed envelope + fusion/tracking +
ATAK/STANAG C2 integration + operator shell. This matches the challenge's own
budget line *"Integration of Technologies onto Existing UAS Platforms — $100K."*

- **We own:** the data/C2/fusion software layer (the verifiable spine below).
- **We source (COTS, not yet selected):** laser rangefinder module + air vehicle.
- **We do NOT claim:** to build the airframe or the laser. The essential
  outcomes (rangefinding accuracy, platform endurance, eye-safe optics, weight)
  are met by **selected COTS hardware**, integrated and proven by planetar.

## Where planetar fits (honest tier split)

| Tier | Outcomes | Owner |
|---|---|---|
| **Strong — planetar core** | DO4 sensor-to-shooter (ATAK/STANAG), DO5 tracking+handoff, DO8 origin/provenance, EO5 data-handling | planetar software |
| **Partial — fusion software** | EO3 GNSS-denied geolocation, DO7 autonomy, DO9 comms architecture | planetar + COTS autopilot |
| **Gap — hardware** | EO1/EO2/EO4/EO6, DO1/DO2/DO3/DO6 (rangefinder, airframe, ruggedization, designation) | **COTS, to source** |

See [`01-CHALLENGE.md`](01-CHALLENGE.md) for the full outcome-by-outcome map.

## Verifiable spine (reused from planetar — verify against repos before citing)

| Component | Path | Role in True North |
|---|---|---|
| Bus | `~/github/planetarx/planetar-broker` | Real-time data fabric in the GCS / air-ground; WAL = auditable fires record |
| Envelope | `~/github/sness23/zmesg` | Typed messages: range fix, target geoloc, track, telemetry, FMV ref |
| Shell | `~/github/planetarx/planetar-ui` | Operator C2 shell; ATAK bridge target |
| Entity graph | `~/data/dev/doibio` | Target-track identity / re-ID (US Patent 10,936,582 — applicant is a *named inventor*) |
| AIS ingest | `~/github/planetarx/planetar-ais` | Pattern reference for live sensor ingest microservice |

Benchmark (planetar-broker, conservative): **SHM p50 80–140 ns / p99 400–900 ns**.

## Key facts

> ⏰ **PROPOSAL DEADLINE: 2026-06-10, 14:00 EDT** (MERX notice for /012) — **~10 days out.** **VERIFY in the CanadaBuys Solicitation Guide before relying on it.**

**Confirmed (public record, 2026-05-31):**
- **Solicitation / tender:** `W7714-248676/012` (CanadaBuys + MERX notice 22785002827). Sibling of the submitted CFP6 bid `…/013`.
- **Program:** IDEaS **Competitive Projects**; first challenge under the Canadian Army **MINERVA Initiative**. BOREALIS-supported.
- **Components (standard IDEaS):** **1a** TRL 1–3 / ≤$250K / ≤6 mo · **1b** TRL 4–5 / ≤$1.5M / ≤12 mo · **2** TRL 6–9 / ≤$5M. (Confirm which are open for /012.)
- **Challenge pool:** **$2.1 M total** across all awards (≈ 7 × ~$300K); per-project budget guidance ≈ **$300K** (image table).
- **Eligibility:** **individuals**, academia, not-for-profit, gov, all industry → solo founder qualifies.
- **Schedule:** mid-point Capability Validation **3–4 mo after award**; **test-ready by spring 2027**; Final Capability Assessment **May 2027**.
- **Apply via:** Solicitation Guide on CanadaBuys. Canada.ca challenge page exists (Salesforce portal is auth-gated — 403 to fetch).

> **Component read:** $300K guidance (> 1a's $250K cap) + a *test-ready prototype with hard specs by spring 2027* reads as **Component 1b (TRL 4–5)**, not 1a. **Decision needed** — [`08-OPEN-QUESTIONS.md`](08-OPEN-QUESTIONS.md) Q1b.

**Still ❓:** confirmed closing date, which Components are open, and Annex B screening / mandatory / point-rated criteria + char limits — all in the **CanadaBuys Solicitation Guide** (not yet downloaded).

## File index

| File | State |
|---|---|
| `DECISION-no-bid.md` | 🛑 **No-bid decision + rationale (read this first)** |
| `CHALLENGE.md` | ✅ Challenge text + images transcribed |
| `01-CHALLENGE.md` | ✅ Outcome → owner mapping + standards |
| `02-STRATEGY.md` | ✅ System-integrator pitch |
| `03-ARCHITECTURE.md` | ✅ Adapted reference architecture |
| `08-OPEN-QUESTIONS.md` | ✅ Live open items |
| `docs/hardware-options.md` | ✅ COTS sourcing scoping (research, unvetted) |
| `04-PORTFOLIO.md` | — not written (no-bid) |
| `05-DATASETS.md` | — not written (no-bid) |
| `06-REFERENCES.md` | — not written (no-bid) |
| `07-TIMELINE.md` | — not written (no-bid) |
| `proposal/` (MC-1, MC-2, PRC-1..7) | — not written (no-bid) |

## Status: CLOSED — NO-BID

Decision and full feasibility rationale: [`DECISION-no-bid.md`](DECISION-no-bid.md).
No proposal narratives were written. The strategy/architecture/sourcing docs below
remain as a **reference** for the system-integrator angle if a hardware partner later
makes a team bid (Option C) viable, or if a similar challenge reappears.

**Forward plan:** scan for IDEaS / MINERVA challenges whose **Essential** outcomes are
software/AI/data-fusion (not hardware platforms) — see the "what to pursue instead"
section of [`DECISION-no-bid.md`](DECISION-no-bid.md).
