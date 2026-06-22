# MC-1 — Current TRL and prior R&D

> **Field cap:** 3,000 characters. **Pass/fail.** Must accurately state current TRL + R&D to reach it.
> **Locked claim:** the solution — the **Fusion Compliance Engine** — is **TRL 2 at start → TRL 3** at end-state.
> CH13 analogue: `../../planetar/proposal/MC-1_trl.md` (reuse the "built substrate" evidence list).

## Draft (skeleton — strip headings before submission)

**Current TRL: 2.** The solution is a modular Fusion Compliance Engine that enforces
machine-readable classification/release-authority policy at the fusion chokepoint. The
concept is formulated with strong component-level evidence (built provenance substrate +
machine-readable policy), but the enforcement engine itself is not yet built or
demonstrated. The 1a builds and demonstrates it → **TRL 3** (PoC, incl. a live system).

Prior R&D establishing the critical function (BUILT — see `THESIS.md`):
- (1) **The chokepoint** — `planetar-broker`: the single typed bus between ingestion and
  fusion; ~1.2k LOC C, broker-integrated detectors. [reuse CH13 MC-1 item 1+4]
- (2) **Native provenance** — `zmesg`: source, ns timestamps, correlation/causation ids.
- (3) **Immutable audit spine** — CRC32 append-only WAL (replayable lineage).
- (4) **Machine-readable policy** — `planetar-market` W3C ODRL + provenance manifests.
- (5) **Per-edge lineage** — `planetar-ontology` (zero-dep TS, 30 tests).
- (6) Applicant credentials [reuse CH13 portfolio].

**Net-new in the 1a (the TRL 2→3 advance):** the policy-evaluation engine at the
chokepoint (permit/restrict/downgrade/segregate), additive class+domain envelope fields,
the WAL enforcement-action record type, and the exportable lineage format.

## TODO
- [ ] Confirm TRL-2 honesty for the *engine* (Q1) — don't let the built substrate inflate it.
- [ ] Pull exact LOC/test counts from `planetar/docs/built-services-inventory.md`.

## Char-count budget
Target ≤ 2,950 (50 buffer). Measure stripped paste block at red-team.
