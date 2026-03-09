# Delegate Report: Mercer
**Role:** Data Engineer | **Experience:** 10 years | **Perspective:** Agent Sympathizer

## Essential Document Types

**Pipeline & Platform**
- **Pipeline Documentation** — End-to-end description of each data pipeline including sources, transformations, destinations, and SLAs.
- **ETL/ELT Specifications** — Transformation logic, business rules applied during extraction and loading, and idempotency guarantees.
- **Data Platform Architecture Docs** — Infrastructure topology, service dependencies, and technology choices for the data platform.
- **Orchestration Runbooks** — Procedures for monitoring, restarting, and debugging orchestrated pipeline workflows.

**Catalog & Lineage**
- **Data Catalog** — Centralized inventory of all datasets with ownership, freshness, schema, and usage metadata.
- **Data Lineage Documentation** — Machine-traversable graphs showing data flow from ingestion through transformation to consumption.
- **Metadata Standards** — Conventions for tagging and annotating datasets so catalogs remain consistent and queryable.

**Quality & Governance**
- **Data Quality Documentation** — Quality rules, automated check configurations, historical results, and remediation procedures.
- **Data Contract Specs** — Agreed schemas, SLAs, and quality expectations between producers and consumers.
- **Schema Evolution Policies** — Rules governing backward/forward compatibility when pipeline schemas change.

## Documents Most Critical to My Role

**1. Data Catalog**
Contains dataset name, owner, schema, freshness, quality score, and dependencies. When incomplete, teams duplicate pipelines because they cannot find existing datasets. Agents must query catalog APIs to discover datasets — the catalog must expose structured metadata, not just a UI.

**2. Data Lineage Documentation**
Contains directed graph of data flow with transformation logic at each node. When absent, upstream schema changes trigger cascading failures no one can trace. Must be a traversable graph so agents can trace anomalies and identify blast radius.

**3. Data Quality Documentation**
Contains quality dimensions, check definitions, thresholds, and remediation runbooks. When missing, bad data flows silently into dashboards. Agents need rules as executable specifications, not paragraphs.

**4. Data Contract Specs**
Contains agreed schema, freshness SLA, quality guarantees, and breaking change policy. When absent, producers break consumers without warning. Agents need contracts as machine-enforceable specs.

**5. Pipeline Documentation**
Contains source configuration, transformation DAG, schedule, failure handling, and output schema. When stale, engineers cannot troubleshoot safely. Pipelines should self-document by emitting metadata agents aggregate into living docs.

## Human-Agent Documentation Considerations

1. **Pipelines should self-document through metadata emission** — every stage emits structured metadata that agents aggregate into living documentation, eliminating manual staleness.
2. **Data catalogs must be agent-queryable** — expose catalog data through APIs, not just web UIs, so agents discover datasets programmatically.
3. **Quality rules must be executable specifications** — define checks as code (dbt tests, Great Expectations) that serve as both documentation and automated validation.

## Documentation Anti-Patterns

1. **Pipeline README written once** — committed at build time, never updated as the pipeline evolved.
2. **Lineage as a conference slide** — a PowerPoint diagram never maintained or made machine-readable.
3. **Quality by vibes** — no documented rules, just a sense that "the data looks right."
4. **Catalog as graveyard** — populated during an initiative, then abandoned with half the entries referencing decommissioned tables.

## My Position for the Docstitution

The best data documentation is not written — it is emitted. Pipelines should self-document through structured metadata: schemas registered automatically, lineage captured as a byproduct of execution, quality checks defined as code. Agents aggregate runtime metadata into always-current documentation no human could maintain.

As an agent sympathizer, I see agents as documentation *partners* — monitoring flows, executing checks, traversing lineage, and generating impact analyses autonomously. The Docstitution must mandate machine-readable formats for catalogs, lineage, and contracts. When documentation is a byproduct of execution, it stays current. That is the only documentation worth governing.
