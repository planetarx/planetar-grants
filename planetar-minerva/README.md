# planetar-minerva — Canadian Army MINERVA Initiative (ISC Challenge Stream, 2026 cycle)

> ⚖️ **DECISION PENDING (2026-09-29): UAS Deconfliction `EN578-24ISC4/94`, closes 2026-10-21 14:00 EDT.**
> First MINERVA call with all-software Essential outcomes — but Phase 2, **TRL 5–9 mandatory**, and
> the application it asks for is unbuilt in planetar (TRL ~2). A solo bid fails Q2. Honest lanes:
> **(A)** subcontractor to an SME prime for the live-conformance half; **(B)** build to TRL 5 for the
> next call. Founder to choose — [`FIT.md`](FIT.md).
>
> 🛑 The five hardware-platform calls (Arctic UAS and siblings) are **NO-BID, decided 2026-09-23**
> — [`DECISION-no-bid.md`](DECISION-no-bid.md).

Workspace for the six **MINERVA** challenges the Canadian Army released through **Innovative
Solutions Canada Call 004** between 2026-08-13 and 2026-09-23. Raw capture (two of the six,
forwarded by D. Huang): [`idea.md`](idea.md). Verified facts for all six: [`CHALLENGE.md`](CHALLENGE.md).
Vehicle: **Zax Analytics** (ISC requires an incorporated Canadian SME; the individual route is out).
Face: defence (D3).

## The six calls

| Challenge | Closes (14:00 ET) | Essentials are… | State |
|---|---|---|---|
| Arctic Uncrewed Air System (`/95`) | 2026-09-24 | an aircraft system | closed · no-bid |
| UGS Surveillance & Reconnaissance | 2026-09-10 | a ground vehicle | closed · no-bid |
| ISR UAS | 2026-09-21 | an aircraft system | closed · no-bid |
| UGS Tactical Cargo Movement (`/97`) | 2026-09-21 | a ground vehicle | closed · no-bid |
| UAS Cargo/Munition Drop | 2026-10-05 | an aircraft system | open · no-bid |
| **UAS Deconfliction (`/94`)** | **2026-10-21** | **software: Windows 4D flight-planning + RF-spectrum deconfliction** | **open · decision pending** |

Common terms: Phase 2 only · TRL 5–9 · up to $500K × ~5 contracts · 15 months · demo at Suffield AB
· 130-point grid, 65 to pass, after three mandatory screens (all Essentials; TRL 5–9 evidence;
innovation definition).

## Key dates

| Date | What |
|---|---|
| **2026-10-11** | Last day for written enquiries to `TPSGC.PASIC-APISC.PWGSC@tpsgc-pwgsc.gc.ca` (Windows question; Phase 2 subcontract cap) |
| **2026-10-21 14:00 EDT** | Deconfliction closes (ISC portal) |
| any time | `MINERVA.Initiative@forces.gc.ca` — Enabling Technologies working group; deconfliction follow-up after the late-September Gagetown industry discussion |

## Why planetar fits — and where it doesn't (short form)

- **Fits:** Additional outcomes 1–2 (real-time collision prevention; real-time conformance to the
  approved 4D trajectory) are exactly the live, provenance-native track fusion planetar already
  runs on maritime feeds. Data-service ingestion (Essential 4) is the existing adapter pattern.
- **Doesn't, yet:** flight-plan authoring, the 4D + spectrum repository, the 4D router, the
  conflict engine, and deconflicted-volume generation (Essentials 2, 3, 5, 6, 7) are net-new.
  "Windows-based" (Essential 1) conflicts with the Linux-only C broker.
- **Landscape:** Kongsberg Geospatial's IRIS Terminal is the Canadian incumbent; its ISC
  eligibility (≤499 FTE incl. affiliates) is unverified. Three firms registered partnering
  interest on the notice: Edgeward, Moon Vault, HiveRadar (unresearched).

## Next actions (depend on the lane)

- **Either lane:** re-verify substrate TRL claims against the repos; read Call 004 for Phase 2
  subcontracting/IP; send the Windows enquiry by 2026-10-11; email MINERVA.Initiative.
- **Lane A:** research the three registered firms; one-page capability sheet (live conformance +
  provenance offer, from [`THESIS.md`](THESIS.md)); outreach this week; record in `OUTREACH.md`.
- **Lane B:** open the build repo (suggested `planetar-airspace`) with the seven Essentials as its
  requirements table; contemporaneous R&D log (Q2 evidence, SR&ED).

## File index

| File | State |
|---|---|
| [`idea.md`](idea.md) | raw Gmail paste of the ISED mailing (2026-08-13; forwarded 2026-08-16) — keep as-is; its "AI Overview" block is not a source |
| [`CHALLENGE.md`](CHALLENGE.md) | ✅ verified research note, all six calls + Deconfliction verbatim + ISC grid (2026-09-23 / 09-29) |
| [`FIT.md`](FIT.md) | ✅ two-screen fit + Essential→asset map + lanes A/B/C (2026-09-29) |
| [`THESIS.md`](THESIS.md) | ✅ **draft** SSOT for the Deconfliction framing (hybrid; planning = core, live = differentiator) |
| [`DECISION-no-bid.md`](DECISION-no-bid.md) | ✅ filed record — five hardware calls, decided 2026-09-23 |
| `OUTREACH.md` | — write if lane A is chosen |
| `proposal/` | — not written (no solo filing; see FIT) |
| [`CLAUDE.md`](CLAUDE.md) | workspace guidance |

## Status: DECISION PENDING — Deconfliction lane (A partner-sub · B build-for-next · stop); hardware calls NO-BID 2026-09-23

Decision owner: Steven Ness. When decided, record it here with the date, add a row to
[`../README.md`](../README.md), and update [`../CLAUDE.md`](../CLAUDE.md).
