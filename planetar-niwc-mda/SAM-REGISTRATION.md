# SAM.gov registration for Zax Analytics — checklist

> Written 2026-10-22. Needed **before award**, not before the Step-1 brief (CSO §6.1), but it has
> lead time and the DIANA window was lost to a registration blocker (2026-07-13). Start now.
> Founder-only facts are `[TODO]`. Re-verify on sam.gov before each step; the forms change.

## Order of operations

The order matters: **a non-US entity cannot start SAM.gov registration without an NCAGE code**
("If your entity is based outside of the U.S., you must go to the NCAGE Request Tool and request an
NCAGE code before starting a SAM.gov registration" — SAM.gov Entity Registration Checklist, p. 3).
The name and address you give NCAGE must match what you later give SAM.gov exactly; mismatches
are the common cause of failed entity validation.

| # | Step | Where | Notes |
|---|---|---|---|
| 0 | **Pin the legal facts** | Corporations Canada / provincial registry `[TODO: which]` | Exact legal name (not a trade name), registered physical address (no PO box), incorporation date, jurisdiction, business number. Per `../planetar-brainstorm/DECISIONS.md` C1 the corporation is registered in the founder's spouse's name with Steven as CEO — enter ownership and officer details exactly as the registry shows them, and confirm Steven is authorised to act for the entity. |
| 1 | **Check for an existing code, then request an NCAGE code** | NATO NCAGE Request Tool (linked from the SAM.gov checklist; NSPA e-portal) | Free. Turnaround not verified — budget weeks. |
| 2 | **Login.gov account** for the person registering | login.gov | Individual identity; Steven. |
| 3 | **Get the Unique Entity ID** — purpose "All Awards" (contracts, not grants-only) | sam.gov → Register Entity | Enter legal name, physical address, incorporation date, and the non-US "alternate information" in place of a US state. SAM.gov validates the entity; if it fails, open a ticket with the Federal Service Desk (fsd.gov) from the page and expect to upload a registration certificate or articles of incorporation. |
| 4 | **Complete the full registration** (Core Data, Assertions, Reps & Certs, DFARS questionnaire, POCs) | sam.gov | See "Facts to gather" below. A US TIN and IRS consent are US-only; EFT banking is optional for non-US entities. |
| 5 | **Record the UEI + CAGE/NCAGE** here and on the brief's title page | this file, `BRIEF-outline.md` | The brief asks for a CAGE code "if available" (§4.1). |
| 6 | **Renew** | sam.gov | Registration lapses unless renewed (annually — confirm the expiry date shown on the dashboard). Calendar it. |
| 7 | Later, at award only: **WAWF/PIEE** for invoicing (CSO §6.2) | piee.eb.mil | Not needed for the brief. |

## Facts to gather for step 4

From the SAM.gov Entity Registration Checklist (All Awards):

- **Core data:** organisation start date; fiscal year end; website; mailing address; MPIN (created
  during registration); owned or controlled by another entity (and its NCAGE if so); predecessor
  holding a federal award in the last three years (no).
- **General:** country of incorporation (Canada); organisation factors (**foreign-owned**); entity
  structure (corporate, not tax exempt); profit structure (for-profit); company / employee
  security clearance (optional — none).
- **Assertions:** NAICS codes `[TODO: choose; candidates to check on census.gov/naics —
  541715 R&D in physical/engineering/life sciences, 541511 custom programming, 518210 data
  processing/hosting]`; optional PSC codes; worldwide size (annual receipts `[TODO]`, employees `[TODO]`).
- **Reps & Certs:** person responsible for pricing (Steven); debarment, fraud, tax-delinquency and
  termination questions (expected "no" across the board — answer from fact, not expectation).
- **DFARS questionnaire:** applies, since NIWC is DoD.
- **Points of contact:** electronic business POC and government business POC `[TODO: Steven plus a
  second person if one exists]`.

## Open questions

- Does the CSO accept a brief from an entity whose SAM registration is still in progress? The
  notice says registration is needed "before award" (§6.1) — asked in `QUESTIONS-email.md`.
- Export-control and Controlled Goods Program implications of a Canadian company delivering
  analytics to DoD — unverified (FIT risk 6). Ask an advisor before pricing.

## Log

| Date | Event |
|---|---|
| 2026-10-22 | Checklist written. Nothing filed yet. |

## Sources

- SAM.gov, *Entity Registration Checklist* (GSA, file dated 2024-11): https://sam.gov/sites/default/files/2024-11/entity-checklist.pdf — read 2026-10-22 (pp. 1–6).
- CSO `N66001-26-S-C036` §4.1, §6.1, §6.2 — [`CHALLENGE.md`](CHALLENGE.md).
- Secondary, not relied on for any step above: Canadian Commercial Corporation knowledge base,
  "How do I register for SAM.gov as a Canadian business?" (page returned 403 on 2026-10-22).
