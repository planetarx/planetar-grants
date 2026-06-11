# 00 — Framing: how to pitch planetar, and who can actually take the money

Before chasing any specific program, get three things straight: (1) which *face* of
planetar a given funder cares about, (2) whether the applicant is *eligible*, and
(3) how the website + YouTube + OSS repo compound into fundraising leverage.

## The three faces of planetar (pitch the one the funder funds)

planetar is one system — a nanosecond message bus + typed envelope (zmesg) +
multi-sensor fusion (AIS/SAR/EO/hydrophone/RF) + entity graph + operator shell —
but it reads as a different thing to different funders. Lead with the face that
matches the cheque:

| Face | Frame it as | Who funds this face |
|---|---|---|
| **Open digital infrastructure** | "An open, auditable real-time data fabric for sensor streams — the missing open standard for low-latency multi-sensor messaging." | NLnet/NGI Zero, Sovereign Tech, Linux Foundation, GitHub Sponsors |
| **Dual-use defence / MDA** | "A sensor-to-decision backbone for maritime domain awareness; dark-vessel detection & re-ID." | IDEaS, NATO DIANA, ISC, BDC StrongNorth, RDII |
| **Blue-economy / ocean safety** | "Open maritime situational awareness for illegal-fishing, SAR, and pollution response — civilian first." | Ocean Supercluster, Ocean Startup Project, ONC, COVE |
| **Applied AI** | "Explainable multi-modal fusion + entity resolution with uncertainty, human-in-the-loop." | IRAP AI Assist, ISC AI/OSINT challenges, AI accelerators |

**Key move:** the *civilian* maritime framing (illegal fishing, search-and-rescue,
oil-spill / pollution monitoring, whale-strike avoidance) is not spin — it's the
honest dual-use story, and it unlocks ocean/climate funders who won't touch a
defence-only pitch. Keep both stories ready; lead with the one in front of you.

## Why "open source" is an asset here, not a liability

Funders increasingly *prefer* open infrastructure, and a few only fund it:

- **OSS-native funders** (NLnet, Sovereign Tech) *require* a free/open license.
- **Government** likes auditable, sovereign, non-vendor-locked tooling — an open bus
  is a feature in a "digital sovereignty" pitch, not a giveaway of the moat.
- **The moat isn't the code.** It's the patent-covered entity-resolution architecture
  (US 10,936,582, applicant a named inventor), the measured ns-scale benchmark, the
  domain integration, and *you*. Open-core / dual-license keeps the upside (see
  [`05-community-revenue.md`](05-community-revenue.md)).

## Eligibility reality-check (resolve before applying)

This is the gate. Most wasted effort comes from applying where you can't qualify.

| Requirement | Programs that demand it | Status to confirm |
|---|---|---|
| **Canadian incorporated for-profit** | IRAP, SR&ED (refundable), ISC, most VC, PacifiCan BSP | ✅ **Zax Analytics is incorporated** (~10 yr, has an accountant). One open item: Steven's legal relationship to it — it's his wife's company (see [`DECISIONS.md`](DECISIONS.md) C1) |
| **<500 FTE, profit-oriented, technical uncertainty** | IRAP | Easily met once incorporated |
| **Academic partner + org gets >50% non-gov revenue** | Mitacs Accelerate | Need a university supervisor; revenue test may bite a pre-revenue startup |
| **Individual / sole inventor OK** | NLnet, IDEaS, some challenges | ✅ unblocked path today |
| **Free/open license on all deliverables** | NLnet, Sovereign Tech | ✅ planetar is OSS |
| **TRL band** | varies — see each file | Honest band is **1–3** |

**Implication.** While incorporation is pending, the *unblocked* moves are the
**OSS funders** (NLnet first) and **individual-eligible challenges** (IDEaS, possibly
ISC depending on the call). Incorporating unlocks the high-$ Canadian programs and
the SR&ED tax-credit engine — treat it as the highest-leverage prerequisite task.

## The creator / OSS flywheel (website + YouTube + repo)

The upcoming **website**, **YouTube channel**, and the **public repo** aren't just
marketing — they are *fundraising infrastructure*. The loop:

```
ship OSS + publish (repo, site, videos)
        │
        ▼
audience + GitHub stars + demo views  ──►  traction evidence in grant apps
        │                                   (reviewers reward real users/usage)
        ▼
GitHub Sponsors / Open Collective / Patreon  ──►  small recurring revenue
        │                                          + proof of community demand
        ▼
credibility ► bigger grants (NLnet → Sovereign Tech → IRAP) ► dual-license deals
```

Concrete asks this enables:
- **On the site:** a "Support / Sponsor" page (GitHub Sponsors + Open Collective links),
  a one-paragraph "why this is open infrastructure," and a roadmap. Reviewers and
  sponsors both read these.
- **On YouTube:** the dark-vessel-detection demo is the hero video. Technical
  build-logs double as evidence of progress for milestone-based grants. (Ad revenue
  is negligible early; the value is *credibility + sponsor conversion*, see
  [`05-community-revenue.md`](05-community-revenue.md).)
- **In the repo:** a `FUNDING.yml` (GitHub Sponsors button), a clear `LICENSE`
  decision (open-core vs. dual-license — pick before the audience arrives), and
  good `README` provenance (benchmark numbers, patent line, dataset URLs) — the same
  "verifiable spine" the proposal relies on.

## Decisions (see [`DECISIONS.md`](DECISIONS.md) for the record)

1. ~~Incorporate Zax Analytics?~~ ✅ **Resolved (D1)** — incorporated. Open sub-item: C1
   (Steven's legal relationship to the company).
2. ~~License model?~~ ✅ **Resolved (D2)** — permissive bus + AGPL platform (dual-license
   keeps the commercial upside). Setup: [`drafts/04-license-and-funding-setup.md`](drafts/04-license-and-funding-setup.md).
3. ~~Defence- or civilian-forward public identity?~~ ✅ **Resolved (D3)** — civilian-forward
   for OSS/ocean funders; defence face reserved for IDEaS/DIANA.
4. **Still open — dilutive or not?** BDC StrongNorth / VC = equity. Grants/sponsors =
   non-dilutive. A solo founder can stay non-dilutive a long way on NLnet + IRAP +
   challenges. `MOAT-STRATEGY.md` advises a venture round on deliverables (late 2026/2027);
   not needed for the near-term moves.
