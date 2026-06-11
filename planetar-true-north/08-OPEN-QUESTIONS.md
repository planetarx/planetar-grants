# 08 — Open Questions

Live blockers and decisions for the True North bid. Status: 🔴 blocking ·
🟡 needed soon · 🟢 nice-to-have.

## 🔴 Q1 — Exact CFP / solicitation details
**Found (public record, 2026-05-31):**
- Tender **`W7714-248676/012`** (CanadaBuys + MERX notice 22785002827).
- IDEaS **Competitive Projects**; Canadian Army **MINERVA Initiative** challenge #1.
- **$2.1 M total** challenge pool (per-project guidance ≈ $300K); test-ready spring 2027.
- Eligible: individuals / academia / NFP / gov / industry.

- **Proposal deadline: 2026-06-10, 14:00 EDT** (MERX abstract for /012) — **~10 days. VERIFY in the Solicitation Guide.** (A separate W7714-248676 *umbrella* date of 2027-03-31 also appears — that's the standing-CFP envelope, not this challenge's proposal deadline.)
- **Components (standard IDEaS):** 1a TRL 1–3 ≤$250K ≤6 mo · 1b TRL 4–5 ≤$1.5M ≤12 mo · 2 TRL 6–9 ≤$5M.

**Still unknown and load-bearing:**
- Confirm the closing date and **which Components are open** for /012.
- Annex B **screening / mandatory / point-rated criteria** + point weights + char limits.
- **Action:** download the **Solicitation Guide from CanadaBuys** for `W7714-248676/012`
  (Annex B = criteria). Interim: assume the standard IDEaS MC/PRC framework (see resolved note below).

## 🔴 Q1b — Component 1a vs 1b (decision needed)
The $300K budget guidance exceeds 1a's $250K cap, and the ask is a **test-ready
prototype with hard performance specs by spring 2027** — that profile reads as
**Component 1b (TRL 4–5, ≤$1.5M, ≤12 mo)**, not 1a (TRL 1–3 concept). Integrating
high-TRL COTS parts supports a TRL 4–5 claim. **Decide 1a vs 1b** — it drives the
TRL claim, budget, duration, and every narrative. Confirm eligible components in
the Solicitation Guide first.

## 🔴 Q2 — Hardware sourcing (nothing selected yet)
Bid credibility depends on a COTS shortlist that meets EO1/EO2/EO4/EO6.
- Eye-safe **Class 1** laser rangefinder module: weight, accuracy (±2 m @ 1 km),
  update rate, power, export status.
- Small UAS: ≥30 min endurance, 3–4 km radius, ≤25 kg integrated, modular bay,
  GNSS-denied autonomy, **Western/NDAA origin** (DO8).
- **Action:** build `docs/hardware-options.md` into a vetted shortlist with
  datasheet links.

## 🔴 Q3 — Designation scope (DO1)
Class 4 laser **designation** (STANAG 3733) is not eye-safe and conflicts with
the EO5 Class-1 eye-safe essential. Likely **out of scope** for low-TRL; bid
rangefinding/cueing as core, designation as a future path. **Confirm.**

## 🟡 Q4 — GNSS-denied geolocation accuracy (the technical crux)
Can we hit **±2 m @ 1 km (EO1)** with degraded GNSS using COTS VIO/INS pose +
planetar fusion? Determines whether the core essential outcome is achievable.
Needs an error-budget analysis (range error + pose error → CEP).

## 🟡 Q5 — Datalink / EM resilience (DO9)
Fibre-optic tether vs non-EM-spectrum control. Tether caps range/endurance vs
EO2 (3–4 km radius) — tension to resolve. Hardware/link decision, planetar agnostic.

## 🟡 Q6 — ATAK integration path
ATAK plugin vs TAK-Server / CoT bridge from planetar-ui? Scope of STANAG 4586
(full UCS vs payload-control subset) and 4609 edition.

## 🟡 Q7 — ITSP.10.171 applicability
Confirm exact **CCCS/CSE** publication title and what it requires of our data
handling (it is cited verbatim in EO5). Don't paraphrase the requirement wrong.

## 🟢 Q8 — Export / ITAR
Military-grade eye-safe LRFs may be export-controlled (esp. US-origin). Confirm a
Canada-procurable path; ties to DO8 origin documentation.

## 🟢 Q9 — Hardware partner / subcontractor
Solo software founder + a hardware-integration challenge: do we need a hardware
sub for airframe integration and flight test? Affects budget split and risk.

## 🟢 Q10 — Patent language discipline (carry-over)
Reuse planetar's exact framing: **"applicant-named inventor on US Patent
10,936,582"** — never "applicant's patent" / "owns." See `../planetar/08-OPEN-QUESTIONS.md` Q9.

---
**Resolved**
- ✅ Positioning = **system integrator** (COTS payload on existing UAS; planetar = data backbone). 2026-05-31.
- ✅ Hardware path = **COTS** (LRF + UAS), to be sourced. 2026-05-31.
- 🔶 Structure = **pull the real rubric from the portal** (user, 2026-05-31). Interim
  working assumption: standard IDEaS Competitive Projects framework as used by the
  submitted CFP6 bid — MC-1 + MC-2 (pass/fail), PRC-1 S&T/10, PRC-2 novelty/20,
  PRC-3 impact/20, PRC-4 feasibility/20, PRC-5 GBA+/5, PRC-6 desired-outcomes/15,
  PRC-7 budget; **3,000-char caps**; ≥70/100 responsive. **Confirm against the
  actual True North CFP guide before drafting narratives** (see Q1).
