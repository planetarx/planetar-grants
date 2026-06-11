# 05 — Community & earned revenue (the website + YouTube + repo flywheel)

Grants are lumpy and competitive; community revenue is small but **recurring,
non-dilutive, and founder-controlled** — and, crucially, it produces the *traction
evidence* that makes grant applications win. The upcoming **website**, **YouTube
channel**, and **public repo** are the engine. Treat them as fundraising
infrastructure, not just marketing (see the flywheel diagram in
[`00-FRAMING.md`](00-FRAMING.md)).

---

## Direct sponsorship rails (turn on day one of public repo)

### GitHub Sponsors
- Recurring + one-time sponsorship via a button on the repo/org.
- **What works:** *specific, scoped* tiers — "priority issue response within 48 h",
  "your logo in the README", "monthly office hours" — convert far better than "support
  my work." Documented solo maintainer ranges: **$800–$4,000/mo** *once there's a real
  audience*. Early on it's small; the value is signal + the flywheel.
- **Do:** add a `.github/FUNDING.yml` so the Sponsor button shows the day the repo is public.

### Open Collective (Open Source Collective fiscal host)
- A **transparent treasury** companies can pay into *without* a contract or invoicing
  relationship — important because many corporate sponsors can expense "Open Collective"
  but not a personal account. ~10% fiscal-host fee.
- Can also receive the **GitHub Sponsors payout**. Stand one up alongside Sponsors.

### Patreon / Polar / one-off
- Lower priority; Patreon suits the YouTube-audience crossover (membership perks). Add
  only if the channel builds a following that asks for it.

## Open-source business models (pick the license deliberately — it's the moat decision)

The license you choose *is* the monetization strategy. Decide before the audience arrives.

| Model | How it earns | Fit for planetar |
|---|---|---|
| **Permissive (MIT/Apache)** | Maximize adoption; earn via services/sponsors only | Best for the **bus/envelope** (open infra → NLnet/Sovereign Tech love it; max users) |
| **AGPL + dual-license** | Free + open under AGPL; companies needing proprietary/SLA terms **buy a commercial license** | Best for the **full platform** — AGPL creates the strongest commercial pull; keeps enterprise upside |
| **Open-core** | Core free; advanced features (multi-tenant, RBAC, connectors, SLA) paid | Natural upsell on the **operator shell / enterprise connectors** |
| **Professional services** | Paid integration, custom detectors, support, training | Documented **$2K–$8K/mo** solo without a formal company; uses your domain expertise |

**Suggested split for planetar:** permissive **bus + zmesg envelope** (open
infrastructure, maximize the standard's reach and OSS-funder appeal) + **AGPL/open-core
on the full fusion platform + shell** (the part enterprises and governments would pay to
license or get supported). This keeps the OSS-funder and dual-license revenue stories
*both* open. Confirm none of this conflicts with the patent/architecture posture.

## YouTube & the content channel (credibility first, ad-revenue last)

Ad revenue is **negligible early** (and gated: ~1,000 subs + 4,000 watch-hours before
monetization). Don't optimize for it. The channel's real payoffs:

1. **Hero demo = grant evidence.** The **dark-vessel detection / re-ID** demo video is
   the single most reusable asset — drop it into IDEaS/ISC/DIANA/Ocean applications as
   proof the system is real. Reviewers reward working demos.
2. **Build-logs = milestone evidence.** Technical progress videos double as a public,
   timestamped record of milestones — useful for milestone-based grants and for showing
   momentum to any funder.
3. **Audience → sponsors → bigger grants.** Subscribers and stars are *traction*;
   traction converts GitHub Sponsors and de-risks you in reviewers' eyes. Channel
   sponsorships (a sensor/cloud vendor sponsoring an episode) can beat ad revenue.
4. **Recruiting & partners.** The channel is how a co-maintainer, an academic partner
   (ONC/UVic), or a consortium lead finds you.

**Website "Support" page checklist:** GitHub Sponsors + Open Collective links · one
paragraph "why planetar is open infrastructure" · public roadmap · the hero demo embed ·
a clear `LICENSE` statement. Sponsors *and* grant reviewers both read this page.

## Sequencing

```
public repo + FUNDING.yml + Open Collective   (week 1 — turn on the rails)
        +
website "Support" page + hero demo video       (credibility surface)
        ▼
NLnet grant + first sponsors                   (first non-dilutive $ + proof of demand)
        ▼
traction cited in IRAP / IDEaS / Ocean apps    (bigger grants land easier)
        ▼
dual-license / services revenue                (durable, founder-controlled income)
```

## Sources

- [Markaicode — monetize open source / GitHub income 2026](https://markaicode.com/monetize-open-source-github-income/)
- [The Pragmatic Engineer — creative ways to fund open source](https://blog.pragmaticengineer.com/creative-ways-to-fund-open-source-projects/)
- [TermsFeed — dual licensing vs. open core](https://www.termsfeed.com/blog/dual-licensing-vs-open-core/) · [Business models for OSS (Wikipedia)](https://en.wikipedia.org/wiki/Business_models_for_open-source_software)
- [Open Source Collective — GitHub Sponsors setup](https://docs.oscollective.org/campaigns-and-partnerships/github-sponsors)
