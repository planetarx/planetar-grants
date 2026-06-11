# Decisions on record — funding & OSS strategy

Resolved choices that steer the rest of this workspace. Dated; update as things change.

## Resolved (2026-06-02, with Steven)

| # | Decision | Detail / consequence |
|---|---|---|
| D1 | **Zax Analytics is incorporated** | ~10-year-old Canadian corporation, has an accountant. **Unblocks IRAP, SR&ED, ISC, Innovate BC** (Track B in [`06`](06-shortlist-and-calendar.md)). ⚠️ *see clarification C1 — it is Steven's wife's company.* |
| D2 | **License model: permissive bus + AGPL platform** | Goal = **wide adoption**. The interoperability substrate is permissive; the value-add platform is AGPL-3.0 (dual-licensable for commercial/defence customers who can't take copyleft → upside preserved). Full plan: [`drafts/04-license-and-funding-setup.md`](drafts/04-license-and-funding-setup.md). |
| D3 | **Public/civilian-forward identity for OSS + non-defence funders** | Lead OSS (NLnet) and ocean (Ocean Startup, ONC) pitches with the open-infrastructure + maritime-safety face; keep the dual-use/defence face for IDEaS/DIANA. One codebase, honest framing per funder. |

### What D2 means concretely (verified on disk 2026-06-02)

Only **one repo needs relicensing**; everything else already matches the decision:

| Component | Current | Target | Action |
|---|---|---|---|
| `planetar-broker` (bus) | AGPL-3.0 | **Apache-2.0** | **Relicense** (sole-authored → clean) |
| `zmesg` (envelope) | Apache-2.0 | Apache-2.0 | none ✓ |
| `planetar-ui / ais / sat / eo / acoustic` | AGPL-3.0 | AGPL-3.0 | none ✓ |
| `planetar-ontology / registry` | **no LICENSE** | AGPL-3.0 | **Add LICENSE** (currently public but "all rights reserved") |

> **Note vs. `planetar/MOAT-STRATEGY.md` (2026-05-19).** That doc's stance was a *thin
> open layer* — envelope public, "bus internals, detectors, fusion, ontology **closed**."
> D2 is a **deliberate shift to openness** (AGPL-open the platform, permissive-open the
> bus) in exchange for adoption. It stays moat-compatible because **AGPL is
> dual-licensable** — a defence/enterprise customer who can't accept copyleft buys a
> commercial license; the patent-covered entity-resolution architecture and the earned
> secret remain the real moat. If the company later pivots back to "keep it closed,"
> note that the 2026-05-15 public release already happened under AGPL — that can't be
> retracted for code already published.

## Clarifications — RESOLVED (2026-06-03, with Steven)

| # | Resolution | Consequence |
|---|---|---|
| C1 | **Steven is now CEO of Zax Analytics.** His wife has stepped away (she works at Open Ocean Robotics) and is **not involved in planetar at all**. The corporation is still *registered in her name*, but Steven is on the record as CEO. | Applicant for IRAP/SR&ED = **Zax Analytics, with Steven as CEO performing the R&D** — the founder is properly connected. ✅ **Track B unblocked.** ⚠️ *One mechanical item for the accountant: confirm the share-ownership split — CCPC ownership sets the SR&ED refundable rate (enhanced 35% on the first $3M of qualifying SR&ED for a CCPC). A rate question, not an eligibility blocker.* Also reconcile the applicant name with the live CH13 bid. |
| C2 | **Disclose the OOR relationship — yes.** Spouse works at Open Ocean Robotics, same blue-economy ecosystem as Ocean Startup / Ocean Supercluster. | When an ocean application asks about conflicts/relationships, **disclose proactively**. Reflect in [`drafts/02`](drafts/02-ocean-startup-challenge.md) (Ocean Startup) and [`drafts/03`](drafts/03-onc-outreach-email.md) (ONC). |
| C3 | **Apply the license changes — yes. DONE 2026-06-03.** | `planetar-broker` relicensed AGPL→Apache-2.0 (+`NOTICE`) and pushed; `planetar-registry` AGPL-3.0 `LICENSE` added + dual-license note (`sness@sness.net`) and pushed. **`planetar-ontology` DONE** — AGPL-3.0 LICENSE + dual-license note committed on `add-ontology-service` (`1aef5de`), where the code lives; **not pushed** (origin/main is a README stub; publishing the branch is Steven's call). WIP untouched. **Still pending (manual):** `.github/FUNDING.yml`, GitHub Sponsors, Open Collective, and dual-license notes on the other 5 AGPL repos (ui/ais/sat/eo/acoustic). |

## Assets unlocked by D1 (the accountant is a real advantage)

A 10-year corporation with an accountant means **SR&ED is low-friction** — the books,
payroll, and filing discipline already exist; the accountant may already file SR&ED.
That makes the IRAP + SR&ED stack ([`01`](01-canada-non-dilutive.md)) the highest-$,
now-unblocked path, *pending only the C1 relationship clarification.*
