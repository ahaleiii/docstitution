# Delegate Report: Strong
**Role:** Integration & Performance Engineer | **Experience:** 11 years | **Perspective:** Balanced

## Essential Document Types

**Architecture & Integration**
- **System Integration Map** — Every integration point, protocol, data flow, and dependency between systems.
- **API Contract Docs** — Interface agreements including schemas, authentication, and error handling between services.

**Performance & Capacity**
- **Performance Baseline Doc** — Recorded latency, throughput, and error-rate baselines per service under standard load.
- **SLA/SLO Definitions** — Measurable thresholds, escalation paths, and measurement methodology for service levels.
- **Capacity Planning Doc** — Resource utilization, growth projections, and scaling triggers updated each release.
- **Benchmarking Reports** — Repeatable procedures, historical results, and regression analysis per component.
- **Load Test Playbooks** — Step-by-step test procedures including tooling, scenarios, and pass/fail criteria.

**Operational**
- **Monitoring & Alerting Docs** — Definitions of every metric, threshold, and alert with rationale for each value.
- **Release Performance Checklist** — Gate criteria verifying baselines are met before each release ships.

## Documents Most Critical to My Role

1. **Performance Baseline Doc** — Contains p50/p95/p99 latency, throughput, and error-rate baselines per endpoint. Used before and after every release to detect regressions. If stale, regressions ship silently. Agents must parse structured metric tables to auto-compare current vs. baseline values.

2. **SLA/SLO Definitions** — Specifies uptime targets, latency ceilings, and error budgets with measurement windows. Referenced during architecture reviews and incident triage. Stale SLAs create false confidence. Agents need machine-readable thresholds for automated compliance checks.

3. **Capacity Planning Doc** — Documents resource headroom, growth curves, and scaling decision points. Consumed during release planning. When outdated, teams under-provision and face outages. Agents benefit from structured data to model capacity scenarios.

4. **System Integration Map** — Describes every integration point: protocol, timeout, retry policy, circuit-breaker config. Used during debugging and change-impact analysis. Missing maps mean guessing at blast radius. Agents require graph-structured data to trace dependency chains.

5. **Load Test Playbooks** — Contains scenarios, tooling config, and historical results. Executed before major releases. Without them, tests are ad-hoc. Agents can execute structured steps and compare results against baselines.

## Human-Agent Documentation Considerations

- **Structured metric tables** — Use standardized columns (endpoint, p50, p95, p99, throughput, error rate) so agents can parse and flag regressions without custom logic.
- **Machine-readable SLA thresholds** — SLA values in YAML frontmatter enabling agents to continuously validate system health.
- **Versioned baselines tied to releases** — Each snapshot linked to a release tag so agents can correlate performance changes to code changes.

## Documentation Anti-Patterns

1. **Undocumented SLAs** — Claiming "five nines" with no written measurement definition. If it has no numbers, it is not an SLA.
2. **Snapshot-only baselines** — Recording numbers once at launch and never updating. Baselines must refresh every release.
3. **Averaged-only metrics** — Reporting only averages without percentiles. The p99 tells the real story.

## My Position for the Docstitution

Every integration point is a contract, and every contract deserves a number. The Docstitution must mandate that performance documentation is a first-class artifact updated with the same rigor as source code. Baselines, SLAs, and capacity projections must be versioned alongside releases so no team ships without knowing what "normal" looks like.

I advocate for structured, machine-parseable performance docs that agents can validate automatically, yet readable enough for a human engineer during a 2 AM incident. The Docstitution should require every service to document latency targets, throughput expectations, and capacity limits in a consistent format from day one.
