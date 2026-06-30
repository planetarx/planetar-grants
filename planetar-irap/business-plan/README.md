# IRAP Business Plan — working folder

> **Purpose.** An ITA-facing **business plan** for Zax Analytics / planetar, assembled from
> the existing IDEaS CH13 proposal material + the venture/market docs. IRAP requires a
> business plan as part of the application package (see `../02-ELIGIBILITY.md`). This folder
> captures **what an IRAP business plan needs**, **where each piece comes from** (provenance),
> and the **draft itself**.

- **The draft:** [`BUSINESS-PLAN.md`](BUSINESS-PLAN.md)
- Built 2026-06-29 from source docs in `../../../planetar/` and `../../../planetar-market/`.

## What IRAP / an ITA wants in a business plan

IRAP assessment is holistic (technical merit + **management/business/financial capacity** +
likelihood of success + **commercialization** + **benefit to Canada**). A business plan that
answers those axes — *not* a pitch deck — is what moves a file. Structure used in the draft:

1. **Executive summary** — company, product, the ask, why IRAP.
2. **Company & management** — legal entity, history, the founder, capacity (the solo-founder
   question answered head-on).
3. **Technology & product** — what planetar is, what's already built vs. what's R&D.
4. **The R&D project** — the IRAP-fundable work (the learned fusion model), framed for
   **AI Assist** + **DI Assist**, with TRL trajectory and milestones.
5. **Market & opportunity** — dual-use: defence/MDA + commercial maritime + data marketplace.
6. **Competition & moat** — architecture lock-out, earned secret, IP.
7. **Commercialization plan** — path to revenue, the venture bridge.
8. **Financials** — cost structure, the IRAP cost-share ask, runway *(needs founder input)*.
9. **Benefit to Canada** — sovereign AI, Canadian IP, jobs.
10. **Risks & mitigations.**

## Source map (provenance — every claim traces here)

| Plan section | Primary sources |
|---|---|
| Company / founder / IP | `planetar/04-PORTFOLIO.md` (Applicant, patents, publications); `planetar/docs/submission-record.md` |
| Technology / built spine | `planetar/02-STRATEGY.md` ("What's actually built"); `planetar/docs/built-services-inventory.md`; `planetar/04-PORTFOLIO.md` (Working code) |
| Thesis / the model | `planetar/docs/recenter-learned-fusion.md` (SSOT) |
| R&D project / TRL / milestones | `planetar/docs/recenter-learned-fusion.md`; `planetar/proposal/PRC-7_budget.md` (M1–M6); `planetar/04-PORTFOLIO.md` (TRL evidence) |
| Impact / benefit to Canada | `planetar/proposal/PRC-3_impact.md` |
| Market / commercialization | `planetar-market/THESIS.md`; `planetar/MOAT-STRATEGY.md` (venture bridge) |
| Moat / competition | `planetar/MOAT-STRATEGY.md`; `planetar/02-STRATEGY.md` (Moats section) |
| Financials | `planetar/proposal/PRC-7_budget.md`; `planetar/docs/compute-estimate.md`; `planetar/docs/submission-record.md` |
| AI Assist / DI Assist fit | `../05-STREAMS-FIT.md` |

## Key facts captured (for fast reference / reuse)

**Company / founder**
- **Zax Analytics** — incorporated in Canada (~2015); Victoria, BC; for-profit; **pre-revenue; solo founder, no employees, no hiring planned; founder not yet on payroll.** DUNS in progress.
- **Steven Randolph Ness, PhD** (Computer Science, UVic 2013; thesis *The Orchive*, supervisor George Tzanetakis). Canadian citizen.
- Scholar metrics (per applicant): **h-index 15, ~1,300 citations, i10-index 21**.
- Ex-Salesforce (to 2021); **named inventor on US 10,936,582 B2 (2021) and US 11,442,952 B2 (2022)** — *Salesforce-assigned background IP, NOT owned by applicant* (framing rule, see `../../../planetar/CLAUDE.md`).

**Technology**
- planetar = **learned cross-modal fusion model** for maritime domain awareness; flagship = **dark-vessel (AIS-off) detection**. Six modalities: AIS, SAR, EO, acoustic, RF, text.
- **Built spine: ~13k LOC across 9 open-source repos** (broker, zmesg, ais, sat, eo, acoustic, ontology, registry, ui), all gitleaks-clean, on GitHub.
- Benchmark (conservative): **SHM p50 80–140 ns / p99 400–900 ns**; TCP path p50 34 µs / p99 424 µs.
- **R&D = the fusion model itself** (TRL 2→3): self-supervised on AIS-on co-occurrence → re-identify AIS-off vessels; uncertainty + conformal calibration; native explainability.

**Track record (R&D credibility)**
- Peer-reviewed semi-supervised hydrophone ML: **Sattar et al. 2011 (95% on NEPTUNE Canada/ONC data)**; **ORCA-SLANG (Interspeech 2021)**.
- doibio entity-resolution POC (~20k LOC, 18 mo); production successor `planetar-ontology` (2,323 LOC, 30 tests).

**Financials (from IDEaS bid — anchors, not IRAP figures)**
- IDEaS CH13 bid total **$157,924** over 6 months; rate **$140/hr fully-loaded**, 925 hrs; compute **$18,000**; one MacBook Pro $7,924.
- IDEaS CH13 **submitted** (CP6-132484, 2026-06-01); TRL 2→3; outcome pending (eval 3–6 mo).

**IRAP fit**
- **AI Assist** (deep learning) + **DI Assist** (defence dual-use: surveillance/autonomous) — planetar hits both. See `../05-STREAMS-FIT.md`.

## Founder input received (2026-06-29) + remaining open items

**Answered by Steven:**
1. **Revenue:** none — Zax Analytics is **pre-revenue**.
2. **Revenue lines:** none currently.
3. **Payroll:** founder will go on **T4 payroll once there is revenue** → **not on payroll
   today.** This is the pivotal fact: IRAP reimburses *paid* salary, so the contribution
   mechanics for a pre-revenue/no-payroll company are the central thing to solve with the ITA
   (see draft §8.2).
4. **IRAP project scope:** **not yet decided** — to be shaped with the ITA (still `[CONFIRM]`).
5. **Hiring:** **none — solo; the founder is the technical hire.** (YEP / first-hire framing
   removed from the plan accordingly.)

**Still open (`[CONFIRM]` in the draft):**
- **Working-capital source** to seed payroll + float the reimbursement gap: IDEaS award (if
  won) / founder capital injection / small bridge. (Draft §8.2, §8.4.)
- **Current cash on hand.**
- **The specific IRAP project scope & budget** (item 4 above).
- **DUNS number** once issued.

## Status

⏸️ **PARKED (2026-06-30) — IRAP on hold until cash flow** (see `../DECISION-hold.md`). The
plan is **DRAFT v0.1, complete and ready**: it reflects a pre-revenue, no-payroll, **solo**
company and foregrounds the **financing structure** (not the R&D) as the key work item with the
ITA. Remaining `[CONFIRM]` items (working-capital source, current cash, project scope/budget)
are deliberately deferred — they get filled in at re-engage time, when the answers will exist.
