# 01 — What is NRC IRAP?

## The program in one paragraph

**NRC IRAP** = the **Industrial Research Assistance Program**, run by the **National
Research Council of Canada (NRC)**. It is Canada's flagship innovation-assistance program
for small and medium technology firms. It provides two things: **(1) advisory services** —
hands-on technical and business mentorship from a field network of **250+ advisors across
130 offices**, and **(2) non-repayable financial contributions** — it pays a percentage of
the salaries of the technical staff doing an approved R&D project. It has existed for
decades and is widely regarded as the most founder-friendly federal R&D program because the
money is a **grant-like contribution, not a loan or an equity stake**, and because every
client gets a dedicated human advisor.

## Who runs it / how it's structured

- **Funder/operator:** National Research Council of Canada (a federal agency).
- **Your point of contact:** an **Industrial Technology Advisor (ITA)** — an NRC employee,
  usually a former technologist or entrepreneur, assigned to your region/sector. The ITA is
  simultaneously your mentor *and* your internal sponsor: they help scope the project, then
  advocate for funding it inside NRC. **The ITA relationship is the program.**
- **First touch:** a bilingual contact centre at **1-877-994-4727**, which routes you to a
  **Client Engagement Advisor (CEA)** who decides if you're ready to be matched to an ITA.

## What it funds

R&D and innovation activities aimed at **developing and commercializing innovative,
technology-driven products or services** in Canada. In practice the money flows as a **wage
subsidy** against the salaries of the technical people performing the work, plus a portion
of contracted/subcontracted technical work.

**It does NOT fund:** day-to-day operating costs, non-technical activities (general
marketing, admin), offshore/out-of-Canada work, or research with no commercialization path.

## Scale of the program (context)

- FY2024-25: **~$393.1M** disbursed to **~3,136 SMEs** (arithmetic average ≈ **$125K/firm**).
- Decades of operation; the default "first government money" for Canadian deep-tech startups.

## Special streams relevant right now

NRC has stood up **targeted streams** on top of base IRAP. Two are direct hits for planetar
(full analysis in [`05-STREAMS-FIT.md`](05-STREAMS-FIT.md)):

| Stream | What it funds | Money behind it | planetar fit |
|---|---|---|---|
| **AI Assist** | GenAI + **deep-learning** R&D in SMEs | $100M (Budget 2024, 5 yrs) | Direct — the fusion model is deep learning |
| **DI Assist** (Defence Industry Assist) | **Defence & dual-use** tech for CAF needs; surveillance, autonomous systems | $244.2M (from FY2025-26) | Direct — maritime dark-vessel detection is dual-use surveillance |

There are also legacy/parallel streams (Clean Tech, Youth Employment Program) — YEP is
useful as a cheap on-ramp (see [`06-ACTION-PLAN.md`](06-ACTION-PLAN.md)).

## Why IRAP fits planetar specifically

- **planetar is a software/AI R&D project by a Canadian tech micro-firm** in Victoria BC —
  exactly IRAP's target profile (assuming incorporation; see [`02-ELIGIBILITY.md`](02-ELIGIBILITY.md)).
- **The science is deep learning** (learned cross-modal fusion). → AI Assist.
- **The application is defence/maritime-security dual-use.** → DI Assist.
- **There is already a credible, auditable spine** — the IDEaS CH13 submission
  (`../../planetar/`), real services (`planetar-broker`, `-ui`, `-ais`, `-eo`, `-sat`,
  `-acoustic`), a published benchmark, and a working architecture. IRAP ITAs reward
  evidence of execution capacity, and this is strong evidence.
- **IRAP and IDEaS stack.** IDEaS is a DND contract for a specific challenge; IRAP funds the
  underlying R&D/commercialization of the company's core technology. They are not mutually
  exclusive (watch only for double-counting the *same* eligible costs — the ITA will police
  stacking limits).

## Relationship to SR&ED (worth knowing)

**SR&ED** (Scientific Research & Experimental Development) is the federal **tax-credit**
program for R&D. IRAP (a contribution) and SR&ED (a tax credit) are **complementary** and
commonly used together: IRAP funds the project's labour up front; SR&ED claims the remaining
eligible R&D spend at tax time. The ITA can advise on sequencing so the two don't conflict.
This is a reason to keep clean, project-tagged time/expense records from day one.
