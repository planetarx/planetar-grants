# planetar-customers — first paying customers (services, not grants)

Pipeline for planetar's first **paying** customers under D2a (GPLv3 software + paid support,
hosting, integration and defence contracts). Started 2026-10-22. **Scope since 2026-10-22: Canada,
Europe and other non-US buyers** (founder decision; the US NIWC track is paused in
[`../planetar-niwc-mda/`](../planetar-niwc-mda/)). Vessels only — no buyer or use aimed at
tracking people.

| File | State |
|---|---|
| [`CUSTOMERS-research.md`](CUSTOMERS-research.md) | ✅ first pass, Canada-heavy (2026-10-22). Spot-check: Larus IDEaS award CW2409671 (CAD 8,305,500, 2025-08-27 → 2028-03-31) re-read on CanadaBuys |
| [`CUSTOMERS-canada-intl.md`](CUSTOMERS-canada-intl.md) | ✅ Canada (deeper) + non-US, non-European (2026-10-22). Spot-checks: Coast Guard CAD 816M / 7 yr release (2026-05-22) and CanExport's 3 FTE + CAD 300k minimum, both re-read on the primary pages |
| [`CUSTOMERS-europe.md`](CUSTOMERS-europe.md) | ✅ Europe incl. UK, Norway, NATO, ESA (2026-10-22). Spot-checks: MMO award 025029-2024 subcontracting split (57%; 35% "SAR data processing, QA of vessel detected") via the Find a Tender API; Kystverket notice TED 587752-2026 via the TED API |

## What the three passes agree on

1. **Buyers pay for data, and planetar owns none.** Sell services *beside* a data owner, or
   subcontract to a prime — not detections in competition with MDA Space, Starboard, Kpler, or the
   free Skylight and Canada's own Dark Vessel Detection service.
2. **Every serious buyer wants a measured number and a reference customer.** Kystverket made
   "an operative system with at least one customer" a pass/fail condition. The xView3 run is the
   number; the first private subcontract is the reference.
3. **The door is open for a Canadian supplier** in NATO, ESA (Canada's subscription), private
   subcontracts, EU member states / Norway / UK above GPA thresholds — and **closed** for EU
   agencies (EMSA, EFCA, SatCen) and EU defence-fund payments.

## Ranked plan (merged, 2026-10-22)

| # | Who | Where | What to sell | First step (founder) | Gate |
|---|---|---|---|---|---|
| 1 | **OceanMind** — prime on the UK MMO maritime surveillance contract, 35% of it subcontracted to SAR processing + detection QA | UK (private subcontract) | A costed SAR-processing / detection-QA pilot | Proposal through their public contact form | xView3 score |
| 2 | **Larus Technologies** — CAD 8.3M IDEaS + CAD 2.5M RCN MDA contracts | Canada (private subcontract) | Open ingest / provenance / Sentinel-1 layer | Short technical call via public contact; keep CH13/CH14-funded work out | none |
| 3 | **Canadian Coast Guard (now DND)** — CAD 816M / 7 yr MDA build-out, Iqaluit hub | Canada | Small pilot: fusion + provenance for the hub picture | ProServices pre-qualification; ask which directorate owns the hub; ISC Testing Stream (the route Zighra used in 2024) | ProServices |
| 4 | **ESA InCubed** — Canada put €8M in at the 2025 Ministerial | ESA (co-funded development, not a customer) | Productising the dark-vessel feed | E-mail the CSA Canada–ESA Program Office, then pitch via ORBIT | none |
| 5 | **Transport Canada EMSA** — AIS + local knowledge, no radar/camera | Canada | Satellite + webcam detection add-on for one pilot community | E-mail the program mailbox (in `CUSTOMERS-research.md`) | ≤ CAD 40k directed |
| 6 | **IOTC regional VMS pilot** — ~EUR 65–89k setup + EUR 7–10.5k/month hosting | Indian Ocean (UN-style tender) | GPLv3 platform + hosting | Free UNGM registration; ask the Secretariat about timing | auth, user roles, ISO hosting |
| 7 | **Kystverket** — NOK 15M non-AIS vessel detection service (TED 587752-2026) | Norway | Next round | Watch; use the notice as the acceptance checklist | reference customer |
| 8 | **DFO Dark Vessel Detection (international)** | Canada | Integration / provenance / training services to DFO | Directed services contract | ≤ CAD 40k |
| — | Clear Seas RFPs · UKHO software DPS · NATO (NSPA supplier file, NCIA) · Irish Lights · MCA C-Scope replacement (2027–28) | — | Watches | see the research files | — |

**Needs a founder decision first:** Open Ocean Robotics' ASOMS consortium (CAD 3.8M Ocean
Supercluster project naming MDA and AI data services, no fusion partner named) — the founder's
spouse works at OOR (`../planetar-brainstorm/DECISIONS.md` C2). Decide whether to pursue at all; if
yes, disclose first.

## Cross-cutting prerequisites (cheap, in order)

1. **The xView3 score** — gate for #1 and #7, and evidence for everything else (in progress, `planetar-fusion`).
2. **aisstream.io commercial terms** — unverified; blocks pricing anything built on that AIS feed.
3. **PSPC ProServices pre-qualification** — gates almost every small Canadian federal contract.
4. **Free registrations:** UNGM; NSPA supplier file (Canada is a NATO member; the NCAGE request already pending serves NSPA too).
5. **Auth + user roles on the Object API** — required by #6 and any hosted offer (also on the NIWC gap list).

## Not realistic now (summary)

EU agency contracts (closed to third countries) · EDF-funded work (third-country costs ineligible) ·
New Zealand, Australia and the Pacific (Starboard + free Skylight) · Latin America (Canada's free DVD
service) · Japan, Korea, the Gulf, India, Indonesia, Chile, Argentina (domestic primes or in-house) ·
CanExport (3 FTE + CAD 300k minimum) · CCC G2G (sized for large deals). Details in each file.

## Status: RESEARCHED — no outreach yet (2026-10-22)

Every first step above is a founder contact; nothing has been sent.
