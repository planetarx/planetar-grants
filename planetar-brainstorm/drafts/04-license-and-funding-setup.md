# License & funding-rails setup plan

> Implements decision **D2** (permissive bus + AGPL platform, for wide adoption) and turns
> on the community-revenue rails. **Not yet applied** — these touch public repos
> (relicensing is outward-facing and hard to fully reverse). Awaiting go-ahead (C3 in
> [`../DECISIONS.md`](../DECISIONS.md)). Verified state as of 2026-06-02.

## Target license map

| Repo | Role | Current | Target | Change |
|---|---|---|---|---|
| `planetar-broker` | **bus** | AGPL-3.0 | **Apache-2.0** | ⚠️ relicense |
| `zmesg` | **envelope** | Apache-2.0 | Apache-2.0 | none ✓ |
| `planetar-ui` | shell | AGPL-3.0 | AGPL-3.0 | none ✓ |
| `planetar-ais` | detector | AGPL-3.0 | AGPL-3.0 | none ✓ |
| `planetar-sat` | detector | AGPL-3.0 | AGPL-3.0 | none ✓ |
| `planetar-eo` | detector | AGPL-3.0 | AGPL-3.0 | none ✓ |
| `planetar-acoustic` | detector | AGPL-3.0 | AGPL-3.0 | none ✓ |
| `planetar-ontology` | entity graph | **none** | **AGPL-3.0** | ⚠️ add LICENSE |
| `planetar-registry` | codegen SSOT | **none** | **AGPL-3.0** | ⚠️ add LICENSE |

**Why permissive for the bus + envelope:** they're the *interoperability substrate*.
Maximum reuse makes the envelope a de-facto standard and is what OSS funders (NLnet) want
to back. **Why AGPL for the platform:** the detectors/fusion/entity-graph/shell are the
value-add; AGPL keeps network-deployed forks open *and* is **dual-licensable** — a
commercial/defence customer who can't accept copyleft buys a commercial license. Upside
preserved (see D2 note vs. `MOAT-STRATEGY.md`).

## Steps (each repo)

### 1. Relicense `planetar-broker` AGPL → Apache-2.0
Clean because it's **sole-authored** (`sness` only, verified via `git log`). No CLA / no
third-party contributors to clear. Per repo:
- Replace `LICENSE` with the Apache-2.0 text.
- Update any license headers / `README` badge / `package`-style metadata referencing AGPL.
- Add a `NOTICE` file: `planetar-broker — Copyright (c) 2026 Steven Ness / Zax Analytics. Licensed under Apache-2.0.`
- Commit: `Relicense planetar-broker from AGPL-3.0 to Apache-2.0 (interoperability substrate)`.
- ⚠️ *The 2026-05-15 AGPL release stays in git history — that's expected and fine; new
  releases are Apache-2.0. Confirm you're the sole copyright holder before pushing.*

### 2. Add `LICENSE` (AGPL-3.0) to `planetar-ontology` and `planetar-registry`
They're public **without a license = "all rights reserved"** (nobody may legally use them
despite being visible). Add the AGPL-3.0 `LICENSE` text + a one-line header note so they
match the rest of the platform. Commit: `Add AGPL-3.0 LICENSE (was unlicensed)`.

### 3. Dual-license note on AGPL repos (enables the commercial path)
Add to each AGPL repo's `README`:
> **Licensing.** Licensed under AGPL-3.0. **Commercial licenses** (for use without AGPL
> obligations) are available — contact sness@sness.net. *(matches the note already
> shipped on `planetar-registry`/`-ontology`, per C3)*

This one line is what turns AGPL into a revenue path ([`../05-community-revenue.md`](../05-community-revenue.md)).

### 4. SPDX headers (optional, recommended)
Add `// SPDX-License-Identifier: Apache-2.0` (bus/envelope) or `AGPL-3.0-only` (platform)
to source file headers — makes the license machine-readable and per-file unambiguous.

## Funding rails (turn on with the public push)

### `FUNDING.yml`
A ready file is in [`FUNDING.yml`](FUNDING.yml) — drop it at `.github/FUNDING.yml` in each
public repo (or in a `.github` org repo to apply org-wide). Fill the `[TODO]` handles
once GitHub Sponsors + Open Collective exist.

### Setup tasks
- [ ] **Enable GitHub Sponsors** for the `sness23` / `planetarx` account (`[TODO]`).
- [ ] **Create an Open Collective** under the **Open Source Collective** fiscal host so
      companies can sponsor without a contract (`[TODO]`).
- [ ] Add scoped sponsor tiers (e.g., "48-hr priority issue response", "logo in README",
      "monthly office hours") — specificity converts ([`../05-community-revenue.md`](../05-community-revenue.md)).
- [ ] Add a **Support** section to each `README` and a **Support page** on the website
      (Sponsors + Open Collective links + the one-paragraph "why this is open infrastructure").

## Apply-now checklist (C3 approved 2026-06-03)
- [x] Confirm sole copyright on `planetar-broker` (sole author `sness` confirmed via `git log`).
- [x] Relicense broker → Apache-2.0 (+ NOTICE). **Pushed** (`bda6cb4`).
- [x] Add AGPL-3.0 LICENSE to `registry` (+ dual-license note). **Pushed** (`f9140a4`).
- [x] Add AGPL-3.0 LICENSE + dual-license note to `ontology` — committed on the
      `add-ontology-service` branch (`1aef5de`) where the actual code lives. **Not pushed**:
      origin/main is a 1-commit README stub; the code+LICENSE go public when you push/merge
      that branch (your call). WIP left untouched.
- [ ] Add dual-license note to the other 5 AGPL repos (ui/ais/sat/eo/acoustic READMEs)
      — same one-liner, contact `sness@sness.net` (confirm/replace email).
- [ ] Add `.github/FUNDING.yml` everywhere — **blocked**: needs GitHub Sponsors + Open
      Collective to exist first (manual account creation; handles are still `[TODO]`).
- [ ] (Optional) SPDX headers.

> Say the word and I'll prepare the exact file changes as commits across the repos for
> your review before anything is pushed.
