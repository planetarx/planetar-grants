# THESIS — planetar for DIANA 2027 (single source of truth)

> Every DIANA narrative (quad chart, long-form, pitch) must match this. **One thesis per bid**
> (per [../CLAUDE.md](../CLAUDE.md)): don't import CH13's learned-fusion-model thesis or CH14's
> compliance-substrate thesis. DIANA's hero is different.

## The one line

> **A working, open, provenance-native engine that fuses multi-domain sensors into one live
> picture and re-identifies the same entity across them — situational awareness you can audit,
> already running on live feeds, ready to harden for contested, multi-classification ISR.**

## Why this thesis (and not CH13's / CH14's)

- **CH13** hero = the *learned fusion model*. **CH14** hero = the *provenance/compliance
  substrate*. **DIANA ISR** hero = the **demonstrated multi-domain fusion + cross-sensor
  re-identification capability itself** — the thing the challenge literally asks for ("sensor and
  data fusion … across platforms, formats, and security classifications … actionable,
  causality-based intelligence"). Provenance is the *trust layer* that makes the fusion auditable
  (= DIANA's "causality-based"), not the headline.

## The three claims it rests on (all auditable — see [FIT.md](FIT.md))

1. **Multi-domain fusion that exists.** Four detector families running on real/live data —
   AIS (`planetar-ais`), satellite SAR (`planetar-sat`, real Sentinel-1), EO (`planetar-eo`,
   live webcams), acoustic (`planetar-acoustic`, live hydrophone) — all publishing normalized
   `zmesg` envelopes onto a benchmarked nanosecond bus (`planetar-broker`).
2. **Cross-sensor re-identification that exists.** An entity-graph service (`planetar-ontology`,
   30 tests, live-verified against the bus) that resolves observations into canonical entities
   and re-identifies dark vessels by kinematics — grounded in the applicant's entity-resolution
   work (**named inventor on US Patent 10,936,582**; never claim ownership).
3. **Auditability built in.** Every envelope carries UUIDv7 ids, nanosecond timestamps, and
   correlation/causation links — fusion across "different sources, formats, and security
   classifications" with end-to-end lineage. This is the "causality-based intelligence" hook.

## The dual-use spine (DIANA scores dual-use heavily)

Same fusion + re-ID backbone, two faces:
- **Civilian:** search-and-rescue, illegal-fishing enforcement, pollution / whale-strike
  monitoring (the live demo's native domain).
- **Defence:** maritime domain awareness, contested multi-classification ISR (the DIANA face).

Lead with the demonstrated capability; the dual-use is the *same code*, honestly.

## What DIANA funds (the TRL story, stated honestly)

The **platform substrate is at TRL 4** (integrated + validated in lab; several components at
TRL 5 on live data). DIANA's €100K advances it **TRL 4 → 5/6**: a single fully-fused multi-sensor
demonstration with cross-sensor re-ID surfaced in the analyst shell, hardened for contested /
multi-classification operation and validated at a NATO test centre. This is consistent with the
IDEaS "TRL 1–3" framing, which scopes *new R&D layered on top of* this substrate — different
things, both true.

## Guardrails (carry from [../CLAUDE.md](../CLAUDE.md))

- Benchmark headline stays **p50 80–140 ns / p99 400–900 ns** (brackets four measured runs);
  no un-measured post-tuning numbers.
- Patent: **"applicant-named inventor on US Patent 10,936,582"** (Salesforce-assigned, 1 of 19).
  Never "applicant's patent" / "owns".
- Every claim traces to a repo path, a measurement, or a citation. Don't soften the spine into
  marketing; don't overclaim TRL or the not-yet-built full-fusion demo as already done.
