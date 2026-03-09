# Delegate Report: Clymer
**Role:** Data Analyst | **Experience:** 12 years | **Perspective:** Balanced

## Essential Document Types

**Data & Analytics**
- **Metric Definition Docs** — Canonical definitions of every business metric including formula, source, grain, and owner.
- **Dashboard Documentation** — Explains what each dashboard shows, what decisions it supports, and what the data *means*.
- **Data Lineage Maps** — Traces every metric from source system through transformations to final report surface.
- **Data Dictionary** — Human-readable catalog of tables, columns, and their business meaning.
- **Report Specifications** — Requirements for scheduled and ad-hoc reports including audience, frequency, and thresholds.

**Process & Governance**
- **Analytics Style Guide** — Standards for chart types, color usage, labeling, and statistical rigor.
- **Data Quality Runbooks** — Procedures for investigating and resolving data anomalies surfaced in dashboards.

**Reference & Context**
- **Business Glossary** — Cross-functional definitions ensuring "revenue" means the same thing to every team.
- **KPI Hierarchy Docs** — How metrics roll up from operational to strategic, with explicit aggregation rules.

## Documents Most Critical to My Role

**1. Metric Definition Docs**
Contains formula, data source, grain, filters, owner, refresh cadence, and caveats. Used daily by analysts, stakeholders, and agents generating summaries. When stale, two teams report different revenue numbers to the board. Agents need structured metric metadata (YAML/JSON) alongside prose so they can validate computations programmatically.

**2. Data Lineage Maps**
Contains source-to-dashboard transformation chain, join logic, and refresh dependencies. Used when debugging discrepancies. When missing, root-cause analysis takes days. Agents need machine-readable graph formats — static diagrams are insufficient.

**3. Dashboard Documentation**
Contains purpose, audience, metric references, and limitations. When missing, users misinterpret charts and make bad decisions. Agents need semantic annotations linking visualizations to metric definition IDs.

**4. Business Glossary**
Contains term, definition, synonyms, and anti-definitions. When stale, "active user" means three different things across teams. Must be queryable so agents resolve to canonical definitions.

**5. Data Quality Runbooks**
Contains anomaly types, investigation steps, and escalation paths. When absent, analysts reinvent investigation from scratch. Agents can execute steps autonomously if structured as decision trees.

## Human-Agent Documentation Considerations

1. **Metric definitions must be dual-format** — prose for humans explaining business context, plus structured metadata (YAML/JSON-LD) so agents can validate calculations and detect drift.
2. **Lineage docs should be graph-queryable** — agents need traversable node-and-edge formats to trace anomalies upstream programmatically.
3. **Dashboard docs should embed semantic annotations** — link each chart element to its metric definition ID so agents answer "what does this number mean?" without hallucinating.

## Documentation Anti-Patterns

1. **Metric without meaning** — Defining a metric as "count of X" without explaining *why* it matters or what "good" looks like.
2. **Screenshot-as-documentation** — A dashboard screenshot with no explanation of filters, time range, or interpretation.
3. **Tribal glossary** — Business terms defined only in one analyst's head, lost when they leave.
4. **Lineage by rumor** — Data flow understood through oral tradition rather than documented transformations.

## My Position for the Docstitution

Every document that references a number must answer: what does this metric actually mean? I have spent twelve years watching organizations drown in dashboards while starving for understanding. The Docstitution must mandate that every metric links to a canonical definition including formula, source, business context, and limitations.

Data lineage is the backbone of trust. The Docstitution should require traceability from strategic KPI to source table in formats both humans and agents can traverse. I stand balanced: dual-format data documentation — prose with business context for humans, structured metadata for agents, and explicit linkage between the two.
