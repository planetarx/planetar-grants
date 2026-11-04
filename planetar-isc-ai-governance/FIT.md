# FIT — the three ISC challenges of 2026-10-30 (screened 2026-11-02)

Screened against the repo fit filter (`../CLAUDE.md`): (1) honest TRL, (2) the Essential
deliverable must be software/AI/data.

## Magnetometer (ISED, closes 2026-11-27) — 🛑 NO-BID

Screen 2 fails outright: the deliverable is a sensor (TRL 5–9 hardware). planetar could only ever
consume its output. Same shape as the five MINERVA hardware calls (`../planetar-minerva/DECISION-no-bid.md`).

## NV diamond (ISED, closes 2026-11-27) — 🛑 NO-BID

Screen 2 fails: the deliverable is materials science / fabrication capacity. No planetar asset maps.

## SSC AI governance (closes 2026-12-22) — recommend 🛑 NO-BID (founder to confirm)

**Screen 2 passes** — this is all software, the first ISC Phase 2 call whose Essentials are pure
governance software. **Screen 1 fails**, and the fit beyond the fail is weaker than it first looks.

### Essential → planetar asset map

| Essential | Nearest planetar asset | Honest state |
|---|---|---|
| E1 continuous alignment / reassessment flags | none (no AI-system registry, no requirement-change propagation) | not started |
| E2 interoperability, open standards | `planetar-market` ODRL policy + catalog API; `planetar-ontology` Object API | adjacent; no connectors to ML lifecycle tools (MLflow, model registries) |
| E3 access and data control | `planetar-platform` governed ports / PEP (no ungoverned read or write path) | design + zero-dep core; not a deployable RBAC/residency product |
| E4 requirements → controls → findings (DADM, AIA, PSD, AI Strategy) | none — the FCE's policy-evaluation engine is the *proposed* R&D of the CH14 bid (TRL 2→3) | not started; the core of the call |
| E5 human review, audit-logged | CRC32 WAL (immutable journal); `planetar-ui` trace | substrate only |
| E6 data/output evaluation (fairness, accuracy, drift) | `planetar-fusion` holdout scoring for one detector | not a general monitoring product |

### Why it fails

1. **Q2 (TRL 5–9) is a mandatory fail.** The demonstrated substrate is TRL 4 (bus/envelope/WAL/
   ontology — `../planetar-diana/FIT.md`), but the *thing SSC is buying* — an AI-governance
   compliance assessor over GC directives — does not exist in any repo. Its honest TRL is ~2,
   the same position as the MINERVA deconfliction app. The CH14 FCE that is closest in spirit is
   itself proposed at TRL 2→3 and unfunded.
2. **Off-thesis.** It is enterprise GRC software for SSC's AI inventory, not maritime / fusion /
   re-ID. Bidding would mean a new product, a new market and a third thesis — and it must not
   borrow CH14's FCE framing while CH14 is under evaluation (one thesis per bid).
3. **Weak on the scored grid even if Q2 passed.** Q7 team (20) and Q5/Q9 project + financial
   risk (20) against a $2M, 20-month, 1–2-award contract with a solo founder; established
   competitors exist (incl. Canadian AI-governance vendors) so Q3b "measurable advance" is hard.
4. **Calendar.** 2026-12-22 lands on top of the NIWC brief (target 2026-12-18) and the MINERVA
   lane-B build.

### What would change the call

- A **partner that already ships** an AI-governance/GRC product at TRL ≥5 and wants planetar's
  provenance substrate (immutable WAL lineage, envelope causation chain) as a subcontracted
  traceability layer. That is the only credible route by 2026-12-22.
- **CH14 wins:** an FCE built to TRL 3 would make a *future* SSC/ISC governance call a lane-B
  candidate (generalize "policy at the chokepoint" from classification markings to DADM/AIA).
  Note it as a watch, not a build commitment.

---

## Update 2026-11-02 — decision: GO, lane "sprint to TRL 5"

Steven chose to pursue the SSC call despite the Q2 risk above. Lane: build the assessor in six
weeks and validate it in a relevant environment (public GC AI Register + one live model + an
external reviewer); **file only if the TRL gate on 2026-12-15 passes** ([`PLAN.md`](PLAN.md)).
The analysis above stands as the risk record; reasons 2–4 are now managed risks, not blockers.
