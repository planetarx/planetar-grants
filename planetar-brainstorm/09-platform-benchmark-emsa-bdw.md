# 09 — Platform benchmark: EMSA "Blue Data Warehouse" requirements → planetar parity matrix (2026-10-06)

**What this is.** A real platform buyer's capability checklist, mapped onto
`../../planetar-platform/20-PARITY-MATRIX/` to show where planetar stands as a *platform*, in a
buyer's words rather than Palantir's feature names. It is a benchmark, **not a pursuit**: the
tender closed on 2026-02-18 and Zax could not have bid (see "Why it could not be bid").

**Why this tender.** It is the only platform-class candidate in the 2026-10-06 scan
([`08-procurement-scan-2026-10-06.md`](08-procurement-scan-2026-10-06.md)) whose full capability
list is public, and it is maritime: the European Maritime Safety Agency consolidating vessel,
company, inspection, port-call and emissions data. It concerns ships and organisations, not
individuals.

**Sources (read 2026-10-06).** Procedure `EMSA/2025/OP/0038`, TED notice 851191-2025
(https://ted.europa.eu/en/notice/-/detail/851191-2025); documents on the EU Funding & Tenders
portal
(https://ec.europa.eu/info/funding-tenders/opportunities/portal/screen/opportunities/tender-details/8e29678c-6a2a-4fd8-bcbe-25d2b76aa730-CN).
Read: Tender Specifications V1, Appendix 1 "use cases for the award criteria" (complete),
Appendix 3 "BDW Guidelines" (governance and lineage sections), Invitation to tender. Not read:
the financial and technical-capacity spreadsheets, the draft contract, the 118 published
questions and answers.

**How to read the status column.** It is this note's assessment of **planetar as of
2026-10-06**, using the matrix legend (built · partial · designed · planned). Where it differs
from the matrix's own status, the difference is stated. Repo facts were read or run today
unless a date is given.

---

## Scorecard

| Group | Items | built | partial | designed | planned |
|---|--:|--:|--:|--:|--:|
| Use Case 1 — acquire, process, select, fuse | 10 | 2 | 6 | 2 | 0 |
| Use Case 2 — expose and visualise | 10 | 1 | 3 | 5 | 1 |
| Governance guideline | 4 | 0 | 4 | 0 | 0 |
| Security and operations | 2 | 0 | 0 | 2 | 0 |
| **Total** | **26** | **3** | **13** | **9** | **1** |

**Read:** planetar would answer the fusion half of this tender from working code and the
exposure half from design documents. Nothing in the governance guideline is beyond the platform
core that already runs, but none of it is in the live service.

## Use Case 1 — acquiring, processing, selection and fusion of data

Titles are the tender's own ("blueDW: …"); quotes are from Appendix 1.

| # | Requirement | planetar today | Parity-matrix rows (matrix status) | Status | Gap |
|---|---|---|---|---|---|
| UC1-1 | **fusing data** — the user defines "the relationships between the different data sources, e.g. by defining the primary and foreign keys", and the solution stores them | Link types and match rules are declared in the registry and stored (`planetar-ontology/src/registry/registry.ts`, `planetar-registry`) | Link Types (built / partial); Schema / dataset registry (built); Ontology Manager — governance of types (partial) | partial | A developer edits registry files; there is no operator-facing way to declare a relationship |
| UC1-2 | **onboarding data with additional development** — "database connections, APIs and ETL pipelines for connections to stores such as FTP servers"; minimum development preferred | Four bespoke detector services publish to the bus; every new source is new code | JDBC / database connector (designed); Batch file/object connector (designed); Webhook / push connector (partial); Live sensor / detector connectors (built) | designed | Cross-cutting gap #9, connectors at breadth |
| UC1-3 | **acquiring data as a standalone input** — operator upload of "Excel, CSV and GeoJSON" | None in planetar | CSV / flat-file import (built); Bulk / batch import (built) | designed | **The matrix's "built" is backed by `doibio`**, the private sandbox, not by a planetar repo |
| UC1-4 | **quality control when onboarding data** — "data validation, error detection and cleaning" | Typed registry; ingest classifies by schema; cross-source disagreements land in the `discrepancy` table | Data health / expectations / checks (designed); Schema-on-ingest / typed parsing (partial) | partial | No declarative expectations, no rejected-record report |
| UC1-5 | **fusing data #2** — "different attributes of an individual entity from multiple data sources … in a single response" | `GET /objects/:type/:id` returns the resolved entity with per-field provenance; `npm test` 48/48 | Golden record / 360 view (built); Per-field provenance (built); Identity resolution (built) | **built** | Only for the sources actually ingested (AIS, SAR, EO, acoustic); no registry-type sources |
| UC1-6 | **unified spatial-temporal view** — "a unified history of an entity"; "all vessels which were present in polygon x during timeframe y" | Observations are stored per entity with nanosecond timestamps and indexed by entity and time. The platform's `sqlite` timeseries-geo adapter offers `range`, `downsample` and `within` (radius + time window) | Time-series / Geotime properties on objects (partial); Geotemporal playback (partial); Distance / proximity / co-location (partial) | partial | **No polygon query**, and the live Object API has no time-range parameter at all. Retention is bounded (500,000 observations by default), which truncates "history" |
| UC1-7 | **resolving conflicts** — "flagging and resolving inconsistencies such as duplicates or different values for the same attribute(s)" | Identity resolution merges duplicates; the `discrepancy` table records the competing values, the chosen value and the policy | Entity resolution / dedup (built); Conflict / discrepancy provenance (built); Conflict / discrepancy surfacing (partial) | **built** | Resolution is by merge policy; an operator cannot review and override a conflict in the shell |
| UC1-8 | **geospatial data** — "points, lines, polygons and multi-geometries"; within bounds, proximity, distance, overlap | Points, great-circle distance, radius search | Geospatial analytics (partial); Geo/temporal data prep (partial) | partial | Lines, polygons, multi-geometries and overlap need a real spatial engine (roadmap Phase 6) |
| UC1-9 | **temporal data** — between, after, before; minute to year, week, quarter, semester | Timestamps and a time index exist; the platform adapter takes a time window and buckets by seconds | Time-series analysis stack (partial) | partial | Not exposed on the live API; no calendar granularities |
| UC1-10 | **data structure** — flat views for consumers; raw nested data kept separately | Raw envelopes are retained (broker write-ahead log, `envelope` table); canonical entities are the cleaned layer | Dataset = immutable versioned transaction (built); SQL transforms (partial); Zero-copy federation / virtual tables (designed) | partial | Entity bodies are JSON documents, not flat SQL views a BI tool can read |

## Use Case 2 — exposure and visualisation of results

| # | Requirement | planetar today | Parity-matrix rows (matrix status) | Status | Gap |
|---|---|---|---|---|---|
| UC2-1 | **building reports** — operator configures and saves reports | None | Dashboards / report builder (designed) | designed | Cross-cutting gap #4 |
| UC2-2 | **sharing reports** — share with other operators or keep private | None | App publishing / sharing (designed); Row-level / record sharing (designed) | designed | Needs principals first |
| UC2-3 | **dashboarding results** — tables, pie, line and bar, "fully filterable" | The shell has channel and map views, not configurable charts | Charting / visualizations (partial); Dashboards / report builder (designed) | designed | Gap #4 |
| UC2-4 | **dashboarding with geospatial elements** — map dashboards; integrate with "GIS tools that expose map layers, such as ArcGIS Online" | `planetar-ui` map with live AIS tracks (per the matrix; not re-checked today) | Map application (built / partial); Map / geospatial view (partial) | partial | No stored polygons or density layers; no standard map-layer output for a GIS tool |
| UC2-5 | **exporting results as files** — PDF, CSV, KML, GeoJSON, "without any limitations on the volume" | None in planetar | CSV / dataset export (built); Briefing / export package (designed) | designed | **The matrix's "built" is `doibio`'s.** The same gap as bulk download in the NIWC call |
| UC2-6 | **exporting results as an API** — downloadable "only by the operator that created the query or other operators that are authorised" | REST Object API | Object API (REST) (built); Token-scoped service access (partial); Authorization decision (partial) | partial | The live API has **no authentication or authorisation** |
| UC2-7 | **automated email notifications** — scheduled dispatch to a mailing list | None | Scheduled reports / exports (designed) | designed | |
| UC2-8 | **exporting results triggered by conditions** — condition-triggered e-mail or push | The platform flow engine runs condition → action flows off the stream (`npm run automation` 8/8 today); the ontology publishes `entity.<kind>.updated` events | Automate / event-driven rules (partial); Alerts / triggers on data change (designed); Webhooks / outbound events (built) | partial | No e-mail or push channel; the flow engine is not wired to the live service |
| UC2-9 | **report refresh** — at least every 15 minutes; streaming "is not required" | The live feed is continuous (WebSocket `/subscribe`) | Object API live feed (WebSocket) (built) | **built** | Applies to data, not to reports, which do not exist |
| UC2-10 | **interaction with standard business intelligence tools** — "such as Microsoft PowerBI", via views, APIs, push | REST JSON only; untested with any BI tool | Export to BI / external tools (planned) | planned | Depends on UC1-10 flat views |

## Governance guideline (Appendix 3) and common requirements

| # | Requirement | planetar today | Parity-matrix rows (matrix status) | Status | Gap |
|---|---|---|---|---|---|
| GOV-1 | A central catalogue as "the single point of truth for defining and enforcing data access policies"; governance board and data owners | The registry is the single source of types and fields, served at `GET /schema` | Ontology Manager (built); Metadata-driven schema (built); RBAC (partial); Source / connection registry (partial) | partial | The catalogue holds schema, not access policy; no roles or owners |
| GOV-2 | "granular permissions (SELECT, MODIFY, CREATE, etc.) on catalogs, schemas, tables, and even columns from a central location" | `planetar-platform/spine/governance.ts`: per-principal row filter and per-field redaction, driven by one policy object (`npm run governance` 8/8 today) | Field-level security (designed); Restricted views / row-column security (designed); Markings (designed) | partial | **Matrix is stale here** — it predates the core by a day. Not in the live service; search and one flow step bypass it (`../../planetar-platform/91-HANDOFF.md` §6, confirmed today) |
| GOV-3 | Lineage tracked through raw → prepared → served layers, and "validated by Data Owner" (Guideline 012) | Per-field provenance on every entity; `GET /trace/:id` causal lineage per envelope; a lineage role with marking propagation in the platform | Field-level / per-field provenance (built); Data Lineage — dataset graph (partial); Proposals / review & approval (designed) | partial | No dataset-level lineage view; no owner sign-off step |
| GOV-4 | Each source's business officer "is in charge of creating and updating the metadata" (Guideline 001) | Type and field metadata live in the registry, edited through git | Metadata-driven schema (built); Field-id dictionary (partial); Source / connection registry (partial) | partial | No per-source ownership; no metadata-quality check |
| SEC-1 | Security baseline, quality plan, the agency's ICT security procedures (Tender Specifications 2.2.1) | — | Encryption at rest (designed); Encryption in transit (partial); SSO (designed); Secrets management (designed) | designed | Also organisational: certifications and procedures a one-person company does not hold |
| OPS-1 | Cost monitoring per source and environment, alerting, backup and recovery, SLA-driven incident handling (2.3.1) | `GET /health`; pm2 | Health / liveness (built); Connection health / sync monitoring (designed); Fleet / deploy delivery (designed) | designed | Also organisational: a staffed service desk |

## What the benchmark says

1. **Fusion is real; exposure is paper.** Six of the ten Use Case 2 items have no running
   code behind them. That is the matrix's cross-cutting gap #4 (analytics and report builder)
   and #8 (configurable UI), seen through a buyer's award criteria: the two use cases together
   carried 40% of the award score.
2. **Geospatial and temporal query is the hole inside the strong half.** UC1-6, UC1-8 and
   UC1-9 all fail on the same thing: no polygon, geometry or time-range query on the live API,
   plus bounded retention. A maritime buyer asks "which vessels were in this polygon in this
   window" first. The roadmap schedules the spatial engine in Phase 6; this benchmark argues
   for a narrow version much sooner.
3. **The governance ask is modest and close.** A catalogue, column-level permissions and
   lineage — all four items are "partial", and the column-level mechanism already runs in the
   platform core. What is missing is enforcement on every path and its presence in the live
   service, which is exactly the governance workstream's jobs A and B.
4. **Authentication is a prerequisite for a third of the list.** UC2-2, UC2-6, GOV-1 and GOV-2
   all need principals, and the live service has none.
5. **Three matrix "built" rows are not planetar's.** CSV import, bulk import and CSV export
   are backed by `doibio`. For any planetar bid they are unbuilt. The governance rows are
   stale in the other direction. The matrix is dated 2026-06-09 and should be re-stamped
   before it is cited externally.

## Why it could not be bid (and what that implies)

All read on the primary documents:

- Participation limited to operators established in EU Member States and nine listed
  neighbouring states; Canada is not listed (Invitation to tender, point 22).
- Minimum yearly turnover of EUR 1,000,000 in each of the last two years (15.4.1).
- At least three Databricks projects of at least EUR 100,000 each in the last five years (15.5.1 A).
- Thirteen named CVs across four profiles (15.5.1 B).
- "The technology adopted to implement the BDW is Databricks" (2.1.2).

A capability-complete planetar would still have been excluded on every one of these. Platform
contracts at this tier buy an incumbent technology and a company of a certain size; the
capability checklist is the tie-breaker among firms that already qualify. For Zax the route in
is the one the scan found: innovation calls and subcontracting, building references first.
