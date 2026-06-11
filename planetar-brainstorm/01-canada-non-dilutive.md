# 01 — Canadian non-dilutive funding

Government grants/contributions and tax credits — money you don't give equity for.
Most of the high-$ options require a **Canadian incorporated for-profit** (see
[`00-FRAMING.md`](00-FRAMING.md) § Eligibility). Sorted roughly by fit-to-effort.

---

## NRC IRAP — Industrial Research Assistance Program ★ high $, prerequisite

The flagship federal R&D grant for SMEs. Non-repayable, covers salaries/contractor
costs for technically-uncertain development.

- **Amount:** $75K–$1M+ per project; first-timers typically **$75K–$200K**.
- **Eligibility:** incorporated Canadian **for-profit**, <500 FTE, profit-oriented,
  genuine technical uncertainty. *Sole props / non-profits do not qualify.*
- **Software fits well** — novel algorithms / architectures / unsolved technical
  problems qualify; routine app dev does not. planetar's ns-bus + fusion + entity
  resolution is squarely eligible *once incorporated*.
- **2026 — new streams worth noting:**
  - **AI Assist Program** — $100M over 5 yr for AI-focused SMEs. ← planetar's fusion/AI face.
  - **Defence Industry Assist** — launched Jan 2026, $244.2M. ← dual-use face.
- **First step:** a senior exec calls **1-877-994-4727**; the centre routes you to an
  Industrial Technology Advisor (ITA). Getting an ITA relationship is the real unlock.
- **Action:** confirm incorporation → call the line → frame against AI Assist.

## SR&ED — Scientific Research & Experimental Development tax credit ★ recurring engine

Canada's largest R&D incentive; refundable tax credit (cash back for CCPCs) on
eligible R&D salaries, materials, and some contractor costs.

- **Why it matters:** stacks with IRAP and runs *every year* you do R&D — it's a
  recurring engine, not a one-shot. A CCPC can get a refundable credit (commonly up
  to 35% on the first tranche of qualified expenditures).
- **Eligibility:** practically needs a **Canadian corporation** to claim the
  refundable portion; software R&D with technical uncertainty qualifies (same test as IRAP).
- **Action:** incorporate → keep contemporaneous R&D records (the docs are the claim)
  → file with the tax return. Pairs naturally with IRAP-funded work.

## Innovative Solutions Canada (ISC) — Challenge Stream ★ same TRL band as CH13

Pre-commercial R&D *contracts* (not grants) to prove feasibility and build a prototype.

- **Amounts:** Phase 1 **≤$150K / 6 mo** (feasibility report); Phase 2 **≤$1M / 2 yr**
  (prototype). TRL 1–6 — the *right* band for planetar (unlike the Testing Stream we
  no-bid).
- **Eligibility:** Canadian small business; incorporation expected.
- **Watch for fitting problem statements.** Live AI/data ones seen 2026:
  - *Advanced technologies for open-source-intelligence due diligence* (NRC) — LLM +
    big-data analytics for OSINT. **Plausible planetar fit** (entity resolution /
    fusion). Verify it's still open and read the criteria.
  - *Multi-modal AI for advanced situational decisions* (DND) — this is **CH13 itself**
    routed through the ISC site; already being bid.
- **Action:** set a standing watch on the Challenge Stream list; enter any data-fusion /
  MDA / OSINT statement. Same writing muscles as the CH13 narratives.
- Challenges list: https://ised-isde.canada.ca/site/innovative-solutions-canada/en/challenges

## Mitacs Accelerate — research internships ★ cheap, needs a university

- **Amount:** **$15K per 4–6 mo internship**; partner org contributes **$7,500**,
  Mitacs matches. Stackable across multiple interns.
- **Catch for a solo startup:** the **partner org must receive >50% of funds from
  non-government sources** — a pre-revenue, grant-funded startup may fail this test.
  Also requires an **academic supervisor + student**.
- **Use case:** if you partner with a UVic/SFU/UBC lab (e.g., on entity resolution or
  hydrophone ML), Accelerate funds the student cheaply and builds an academic citation
  trail for other grants. ONC is UVic-based — natural bridge (see [`04-ocean-maritime.md`](04-ocean-maritime.md)).

## PacifiCan / Innovate BC — regional (BC-local) ★ local, mixed terms

- **Innovate BC** grants: roughly **$50K–$250K** for BC tech SMEs — genuinely
  non-dilutive, smaller, BC-focused.
- **PacifiCan Business Scale-up & Productivity:** large ($200K–$5M) but **repayable
  (0% interest)** — debt, not a grant. Usually wants 2+ yrs operating + 20%+ revenue
  growth — too mature for planetar today. Note for later.
- **Signal:** May 2026 — PacifiCan put **$17M into 8 BC companies on AI & quantum**;
  it actively funds BC AI. Worth a relationship.
- **BC Interactive Digital Media Tax Credit** (17.5% of eligible labour) — check if the
  operator-shell UI work qualifies.
- **Action:** scan Innovate BC's open calls; lighter lift than the federal programs.

## IDEaS — DND (the live channel)

The program planetar is already bidding (CH13). Keep watching the standing CFP
umbrella **W7714-248676** and Army **MINERVA** for the *next* software/AI-essential
challenge. Detail in [`03-defence-dualuse.md`](03-defence-dualuse.md).

---

## Stacking strategy

The classic Canadian non-dilutive stack for a software startup:

```
incorporate ──► IRAP (project salaries, non-repayable)
                 + SR&ED (tax credit on the same R&D, recurring)
                 + ISC / IDEaS (milestone contracts on specific problem statements)
                 + Mitacs (cheap academic labour, citation trail)
```

IRAP + SR&ED are designed to coexist; ISC/IDEaS add problem-specific cheques; Mitacs
adds subsidized research labour. **Incorporation is the key that turns most of these on.**

## Sources

- [GrantOps — IRAP Funding 2026 guide](https://grantops.ai/en/blog/irap-funding-guide-2026/) · [NRC — IRAP financial support](https://nrc.canada.ca/en/support-technology-innovation/financial-support-technology-innovation)
- [ISED — ISC Challenge Stream](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/challenges) · [ISC — OSINT due-diligence challenge (NRC)](https://ised-isde.canada.ca/site/innovative-solutions-canada/en/advanced-technologies-open-source-intelligence-due-diligence)
- [Mitacs — Accelerate](https://www.mitacs.ca/our-programs/accelerate-entrepreneur/)
- [Techcouver — PacifiCan $17M to BC AI/quantum (2026-05)](https://techcouver.com/2026/05/12/government-invests-bc-companies-innovating-ai-quantum/) · [PacifiCan funding](https://www.canada.ca/en/pacific-economic-development/services/funding.html)
- [GrantCompass — BC grants index](https://grantcompass.ca/british-columbia-grants.html)
