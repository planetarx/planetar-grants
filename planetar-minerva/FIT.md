# FIT — MINERVA UAS Deconfliction (`EN578-24ISC4/94`): go/no-go + evidence

- **Verdict (2026-09-29):** **Screen #2 passes for the first time in MINERVA's history — every
  Essential outcome is software. Screen #1 fails for a solo bid this round:** the call is Phase 2,
  **TRL 5–9 is a mandatory pass/fail**, and the specific application it asks for (a Windows 4D
  flight-planning and deconfliction system with an RF-spectrum-aware repository) **does not exist
  in planetar today (TRL ~2)**. 22 days remain. No honest path to TRL 5 by 2026-10-21 alone.
- **Honest lanes:** **(A)** join an eligible SME prime that already has a TRL 5+ planning core, as
  the *live conformance and collision-avoidance* subcontractor (Additional outcomes 1–2 are
  planetar's strengths); **(B)** treat this notice as the design spec, build the deconfliction
  application on the planetar substrate to TRL 4–5 over the coming months, and bid the next
  airspace/C2 call. (A) and (B) are compatible. **(C)** a truthful solo filing fails Q2 by construction.
- **Decision owner:** Steven Ness. **Not yet decided** (see `## Status` in [`README.md`](README.md)).
- **Deadline:** 2026-10-21 14:00 EDT; enquiries by 2026-10-11.

---

## The two-screen fit filter

| Screen | Test | Result |
|---|---|---|
| **#1 — Honest TRL** | Gate is **TRL 5–9** (Q2, pass/fail; "TRL 4 or below" fails). | ❌ **FAIL today, solo.** Substrate verified TRL 4 (maritime, 2026-06-22, [`../planetar-diana/FIT.md`](../planetar-diana/FIT.md)); the deconfliction *application* is unbuilt (TRL ~2). Reachable with a partner's core (A) or after a build (B). |
| **#2 — Software-essential deliverable** | Are the must-pass outcomes software/AI/data? | ✅ **PASS, cleanly.** All seven Essentials are software: Windows app, flight-plan authoring, 4D repository, data-service integration, 4D path generation, conflict check/resolve, deconflicted-volume generation. No airframe, optics, or RF aperture. |

This is the inverse of the five sibling calls and of both prior no-bids: the deliverable is
right, the maturity is not.

## Essential-outcome → planetar-asset map (the Q1a gate)

| # | Essential outcome | planetar today (verify against repos before citing) | Gap |
|---|---|---|---|
| 1 | Windows-based | `planetar-ui` (browser) and `planetar-ontology` (Node/TS) run on Windows; **`planetar-broker` is Linux/epoll-only** | Server side must run on Windows without the C broker, or the broker needs a Windows port. Whether a browser app on a Windows host satisfies "Windows-based" is an enquiry question |
| 2 | Create/store flight plans incl. RF requirements | nothing | **net-new** (authoring UI + schema) |
| 3 | 4D trajectory + spectrum repository | `planetar-registry` typed-model codegen; `planetar-ontology` SQLite entity store with kinematic tracks (maritime) | new record types on an existing store — moderate |
| 4 | Integrate crewed flight plans, weather | the per-modality ingest pattern (`-ais`, `-sat`, `-eo`, `-acoustic` → bus) | new adapters (ADS-B/ICAO FPL, ECCC weather) — pattern exists, code is new |
| 5 | Optimal 4D flight path from mission goals + physical limits | nothing | **net-new algorithmic core** (4D routing under constraints) |
| 6 | Check requests vs plans, no-fly zones, RF spectrum; resolve by priority or human decision | spatio-temporal association in the entity graph is adjacent; human-in-the-loop shell exists | **net-new** conflict engine; UI pattern reusable |
| 7 | Generate 4D deconflicted "tunnels"/"boxes" | nothing | **net-new** volume generation |

**Read:** four of seven Essentials are net-new and two are moderate builds. That is the honest
TRL ~2 finding. Contrast the FCE bid, where every Essential mapped to an existing primitive.

## Additional outcomes — where planetar is genuinely strong

| # | Additional outcome | planetar asset |
|---|---|---|
| 1 | Real-time UAS data analysis to prevent collisions, auto-adjust paths | the whole live substrate: ns bus, `zmesg` envelopes, live multi-source tracks fused in the entity graph, HLC-ordered ring design (`../../planetar-disruptor/`) for causal ordering across feeds |
| 2 | Real-time check that a UAS follows its approved 4D trajectory | live track vs. plan is the same machinery as dark-vessel re-acquisition; per-edge provenance gives an auditable "why" per alert |
| 3 | NATO-sourced critical components | all software Canadian-authored, GPLv3 (D2a) |

These are worth at most 10 of 130 points **but they are the differentiator a prime lacks** — and
they are exactly what LCol Lemay described (helicopters, air defence, counter-UAS, friendly fire).
Under lane (A) this is the offer; under lane (B) it is the part that is already at TRL 4–5.

## TRL evidence and honesty

- Substrate TRL 4 (components at 5 on live feeds) was verified against the repos on 2026-06-22
  for the DIANA bid. That verification is **three months old and maritime-specific**; re-run it
  before any narrative repeats it.
- ISC TRL 5 = "component and/or process validation in a relevant environment," beta prototype
  tested with the end user's conditions. For this call, the relevant environment is Army UAS
  operations with crewed traffic and spectrum constraints. Nothing in planetar has been validated
  there.
- Q2 also asks for the R&D record: methods, feasibility data, validation evidence, environment,
  personnel. A build under lane (B) must generate that record as it goes (contemporaneous —
  also what SR&ED wants).

## Why this beats every prior MINERVA/IDEaS/ISC screen — and where it doesn't

| Test | True North (/012) | ISC TS13 | Arctic UAS (/95) | **FCE (CH14)** | **Deconfliction (/94)** |
|---|---|---|---|---|---|
| Essentials are software | ❌ | ❌ | ❌ | ✅ | ✅ |
| Honest TRL lane exists for a solo bid | weak (1a) | ❌ TRL 7 | ❌ TRL 5 | ✅ 1a | ❌ **TRL 5 solo; ✅ with partner or after build** |
| Reuses the substrate | thin | thin | GCS only | core | **Additional outcomes only; Essentials mostly new** |
| Eligibility | individual OK | Zax OK | Zax OK | individual OK | Zax OK |

## Lanes

**(A) Subcontractor to an SME prime — the only route to the 2026-10-21 close.**
- The prime must already hold a TRL 5+ planning/deconfliction core and be preparing a bid.
  Three firms registered partnering interest on the notice (Edgeward, Moon Vault, HiveRadar —
  unresearched). The obvious incumbent, Kongsberg Geospatial (IRIS Terminal), may fail the
  ≤499-FTE affiliation test — verify; if ineligible, the field is SMEs.
- Offer: live conformance monitoring + collision-risk alerts + provenance/audit on the planetar
  bus (Additional 1–2), plus data-service adapters (Essential 4). Zax files nothing; the prime
  carries Q1a/Q2.
- Cost: a one-page capability sheet and outreach this week; the prime's clock is 2026-10-21.
- Risk: subcontract share is capped (Phase 1: one-third; Phase 2 unverified) and IP terms follow
  the prime's contract.

**(B) Build to TRL 5 for the next call.**
- MINERVA is iterative and explicitly wants "command/control integration"; ISC re-issues
  challenges; IDEaS has "Breacher" upcoming and posts under `W7714-248676`. A TRL 4–5 open-source
  deconfliction prototype validated on live traffic (ADS-B + hobby/RPAS-club UAS telemetry, or an
  Army exercise if MINERVA grants access) would clear Q2 next time and is a dual-use civilian
  product in its own right (UTM for Canadian BVLOS operators).
- Build home: a new code repo (suggested `planetar-airspace`), not this Markdown repo.
- Engagement now: `MINERVA.Initiative@forces.gc.ca` for the Enabling Technologies working group and
  the Gagetown deconfliction follow-up; that is how the relevant-environment validation happens.

**(C) Solo filing.** Truthful TRL 2–3 fails Q2. Not recommended; recorded for completeness.

## Open risks

1. **Windows (Essential 1).** Decide early whether the product is a native Windows service +
   browser UI, or a full port. Ask ISC by 2026-10-11 whether a browser client on Windows with a
   Windows-hosted service qualifies (useful for (B) even if (A) fails).
2. **Spectrum expertise.** RF spectrum deconfliction (Essentials 2, 3, 6) is a domain planetar
   has never touched. Under (A) the prime owns it; under (B) it needs a source of frequency
   allocation rules.
3. **Bandwidth.** CH13 and CH14 are under evaluation; Ocean Startup and Schmidt outcomes are
   pending; a TRL-5 build competes with the learned-fusion thesis (`planetar-fusion`). This is a
   founder trade-off, not a fit question.
4. **Thesis hygiene.** One thesis per bid: the Deconfliction thesis ([`THESIS.md`](THESIS.md))
   must not import CH13's learned-fusion model or CH14's compliance engine as the hero.

## Before committing to either lane

- [ ] Founder decision recorded in `README.md` `## Status` and, if (A), a dated `OUTREACH.md`.
- [ ] Re-verify substrate TRL claims against the repos (not the June note).
- [ ] Read the Call 004 solicitation for Phase 2 subcontracting and IP terms.
- [ ] If (A): research Edgeward, Moon Vault, HiveRadar; send the capability sheet; confirm the
  prime's Q2 story is real before lending the planetar name to it.
- [ ] If (B): open the build repo with the notice's seven Essentials as its `docs/DESIGN.md`
  requirements table; log R&D contemporaneously.

## Sources

- Challenge text, grid, eligibility, contacts: [`CHALLENGE.md`](CHALLENGE.md)
- Substrate TRL verification: [`../planetar-diana/FIT.md`](../planetar-diana/FIT.md) (2026-06-22); built inventory `../../planetar/docs/built-services-inventory.md` (2026-05-21)
- Prior screens: [`../planetar-fce/FIT.md`](../planetar-fce/FIT.md), [`../planetar-true-north/DECISION-no-bid.md`](../planetar-true-north/DECISION-no-bid.md), [`../planetar-innovation/DECISION-no-bid.md`](../planetar-innovation/DECISION-no-bid.md), [`DECISION-no-bid.md`](DECISION-no-bid.md)
