# Delegate Report: Butler
**Role:** DBA | **Experience:** 16 years | **Perspective:** Balanced

## Essential Document Types

**Schema & Structure**
- **Schema Documentation** — Auto-generated descriptions of every table, column, index, constraint, and relationship.
- **Entity-Relationship Diagrams** — Visual maps of database structure generated directly from live schema, never hand-drawn.
- **Data Dictionary** — Business-readable catalog mapping technical column names to meanings and valid value ranges.
- **Naming Convention Guide** — Standards for table, column, and index naming that make schemas self-documenting.

**Operations & Change**
- **Migration Documentation** — Records of every schema change including rollback procedures and data impact analysis.
- **Query Optimization Guides** — Documented patterns for efficient data access including index strategies and anti-patterns.
- **Backup & Recovery Runbooks** — Procedures for every recovery scenario with RTOs, RPOs, and tested restore steps.

**Governance & Access**
- **Change Management Procedures** — How schema changes get proposed, reviewed, tested, and deployed.
- **Incident Response Playbooks** — Database-specific procedures for outages, corruption, and replication failures.

## Documents Most Critical to My Role

**1. Schema Documentation**
Contains table definitions, column types, constraints, indexes, and foreign keys — generated from the database catalog, never manually authored. Used by developers and agents generating SQL. When stale, queries target nonexistent columns. Agents must consume structured metadata to generate valid SQL.

**2. Migration Documentation**
Contains migration script, rollback script, pre-migration checklist, and data impact assessment. Used during deployments and emergency rollbacks. When missing, a failed 2 AM migration becomes a data-loss event. Agents need structured pre/post conditions and executable rollback steps.

**3. Entity-Relationship Diagrams**
Contains tables, relationships, cardinality, and constraints — auto-generated from live schema. When manually maintained, they diverge from reality within one sprint. Agents need the underlying graph data to reason about join paths.

**4. Data Dictionary**
Contains technical name, business name, data type, valid values, and sensitivity classification. When absent, BAs guess at column meanings. Must be dual-layered: structured metadata for agents, narrative for humans.

**5. Query Optimization Guides**
Contains recommended access patterns, index guidance, and known expensive queries. When missing, everyone independently rediscovers the same pitfalls. Agents should reference these as constraints to avoid catastrophically slow SQL.

## Human-Agent Documentation Considerations

1. **Schema docs must be generated, not authored** — Extract metadata, enrich with business context, publish structured (JSON/YAML) and visual (ERD) formats.
2. **Migration docs need machine-executable rollback specs** — Agents need rollback as executable steps with preconditions, not narrative paragraphs.
3. **Data dictionaries should bridge technical and business language** — Link each column to its business glossary entry so agents translate between developer and stakeholder vocabularies.

## Documentation Anti-Patterns

1. **Hand-drawn ERDs** — Any ERD in a drawing tool is wrong the moment the next migration runs.
2. **Migration without rollback** — Forward-only migration docs are half a document.
3. **Schema docs in a wiki** — Schema documentation maintained separately from the database drifts immediately.
4. **Column names as documentation** — Assuming `crt_dt` is self-explanatory.

## My Position for the Docstitution

In sixteen years I have learned one truth: the only database documentation you can trust is generated from the database itself. The Docstitution must enshrine that schema docs, ERDs, and data dictionaries are derived artifacts — generated from live metadata, enriched with business context, and regenerated on every schema change.

Every schema change must include its forward script, rollback script, and data impact assessment. Agents will propose and execute migrations — they need machine-readable rollback specs, not prose. No migration should proceed without a tested reversal path. Database docs serve developers, BAs, ops teams, and agents alike — the Docstitution must mandate auto-generation where possible and structured formats that let agents participate safely.
