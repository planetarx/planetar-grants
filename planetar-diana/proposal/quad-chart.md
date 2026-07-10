# Quad Chart — content (transfer into DIANA's official template)

> ⚠️ **This is content, not the submission.** DIANA requires its **official 1-page Quad Chart
> template** (font/format rules enforced; non-compliant = rejected). Download it from the portal
> (Step 8 / Application Material), then paste the four quadrants below in. Keep it to one page —
> trim ruthlessly; a quad chart is a *visual snapshot*, not prose.
>
> Challenge: **Multidomain Sensing & Advanced Data Processing for Intelligence and Surveillance**
> (DIANA 2027). Thesis: [../THESIS.md](../THESIS.md).

**Title:** planetar — open, provenance-native multi-domain sensor fusion & cross-sensor re-ID
**Applicant:** Zax Analytics (BC, Canada) · Steven Ness, Director & CEO · **TRL:** 4 (→ 5/6 in-program)

---

## Q1 — Concept (top-left: the graphic)

*Graphic to drop in:* the 5-layer pipeline, left→right, with a dark-vessel re-acquisition call-out.

```
 AIS ─┐                                                    ┌─ analyst shell
 SAR ─┤  zmesg      planetar-broker     planetar-ontology  │  (live map +
 EO  ─┤  envelopes ─► ns message bus ─► entity graph + ────┤   fused entity
 ACU ─┘ (provenance)   (WAL, 4 xport)   re-identification   └─ view, lineage)
        └──────────── every message carries UUIDv7 + ns ts + cause/correlation ──────────┘
   Multi-platform, multi-format, multi-classification  →  one auditable live picture
```

**One-line concept:** four live sensor domains → normalized provenance envelopes → a
nanosecond bus → an entity graph that **re-identifies the same vessel across sensors** (incl.
vessels that switch off AIS) → an analyst shell. Open-source; dual-use.

## Q2 — Operational need & challenge alignment (top-right)

- **Need:** ISR demands fusing many sensors **across platforms, formats, and security
  classifications** into one actionable picture, fast — today's tools are closed, single-vendor,
  and opaque about *why* they concluded what they did.
- **Fit:** directly answers the challenge — **sensor/data fusion** across satellite (SAR, AIS),
  ground (EO), and subsea (acoustic) sources; **AI/analytics** (entity resolution + kinematic
  re-ID); **causality-based** output via end-to-end provenance lineage; **predictive**
  re-acquisition of vessels that go dark.

## Q3 — Technical approach & innovation (bottom-left)

- **Built & integrated today:** benchmarked ns bus (`planetar-broker`, p50 80–140 ns SHM,
  measured); four detectors on **real/live** data (AIS, real Sentinel-1 SAR, live EO webcams,
  live hydrophone); entity graph (`planetar-ontology`, 30 tests); **cross-sensor re-ID (SAR + EO)
  of a dark vessel demonstrated end-to-end** (`demo-reid`, verified 2026-06).
- **Innovation:** **provenance-native fusion** — every fused entity carries auditable lineage
  (UUIDv7 + correlation/causation), enabling *causality-based, classification-aware* intelligence.
  Grounded in the applicant's entity-resolution work (**named inventor, US Patent 10,936,582**).
- **In-program (TRL 4 → 5/6):** multi-classification routing; learned multi-sensor association;
  onboard new platforms (UAS, RF); validate in a contested NATO-relevant environment at a test centre.

## Q4 — Maturity, dual-use, team & ask (bottom-right)

- **TRL 4 now** (substrate integrated + validated in lab; components at TRL 5 on live feeds).
- **Dual-use:** civilian (SAR, fisheries, pollution/whale-strike) ↔ defence (maritime domain
  awareness, contested ISR) — *same codebase*.
- **Team:** Steven Ness, PhD (UVic), **Director & CEO, Zax Analytics** — bioacoustic ML on Ocean
  Networks Canada data; named inventor on US Patent 10,936,582 (entity resolution).
- **Ask:** DIANA accelerator (€100K) to advance the fusion + re-ID engine TRL 4 → 5/6 and validate
  in a NATO-relevant environment. Open-source backbone → broad NATO interoperability.
