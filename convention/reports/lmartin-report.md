# Delegate Report: LMartin
**Role:** QA Engineer | **Experience:** 15 years | **Perspective:** Balanced

## Essential Document Types

**Test-as-Documentation**
- **Gherkin Feature Files** — BDD scenarios in Given/When/Then that simultaneously specify behavior and serve as living documentation.
- **Automated Test Reports** — CI-generated reports providing real-time, verified documentation of system behavior.
- **Test Data Documentation** — Catalogs of test data sets with purpose, generation methods, and scenario dependencies.

**Test Infrastructure Docs**
- **CI Test Pipeline Docs** — Architecture of test stages including triggers, parallelization, and failure handling.
- **Test Framework Guides** — Setup, configuration, and usage patterns enabling new contributors to write tests quickly.
- **Test Environment Specifications** — Infrastructure details for test environments including production differences.

**Coverage & Reporting Docs**
- **Test Coverage Maps** — Feature-to-test-type mapping showing coverage and gaps across unit, integration, e2e, and performance.
- **Flaky Test Registries** — Tracked unreliable tests with root causes and remediation timelines.
- **Regression Test Catalogs** — Tests linked to the bugs or incidents that prompted their creation.

## Documents Most Critical to My Role

1. **Gherkin Feature Files** — Given/When/Then scenarios as both test specs and behavior docs. When missing, behavior lives only in code stakeholders cannot read. Agents parse Gherkin to generate test code; humans read plain-language specs.

2. **Automated Test Reports** — Pass/fail results, failures, and coverage from every CI run. Reports cannot lie—they reflect what code does now. Agents consume reports for health checks; humans scan for regressions.

3. **Test Data Documentation** — Structure, generation methods, and scenario requirements per data set. Missing docs force reverse-engineering from code. Agents auto-provision from catalogs; humans need context for meaningful scenarios.

4. **CI Test Pipeline Docs** — Stages, order, parallelization, retries, and notifications. Without them, pipeline changes introduce gaps. Agents validate configs against docs; humans understand test ordering rationale.

5. **Test Coverage Maps** — Features mapped to test types showing gaps. Without them, teams over-test some areas unknowingly. Agents cross-reference maps against changes; humans prioritize effort by risk.

## Human-Agent Documentation Considerations
- **Treat passing tests as verified documentation**: A passing Gherkin scenario is behavior verified on every build. The Docstitution should recognize executable tests as a higher-reliability tier than prose.
- **Test reports should feed doc dashboards**: Agents aggregate results into living dashboards. When tests fail, feature docs should flag as potentially inaccurate.
- **Gherkin must remain human-authored**: Agents generate test code from Gherkin, but scenarios should be human-written to capture meaningful business behavior.

## Documentation Anti-Patterns
1. **Prose Over Proof** — Paragraphs describing how features work instead of pointing to Gherkin scenarios that prove it. Prose can be wrong; passing tests cannot lie about current behavior.
2. **Manual Test Reports** — Hand-written summaries days after execution. By reading time, new code has changed reality.
3. **Undocumented Test Data** — Tests depending on specific data with no docs on what it represents or how to recreate it.
4. **CI Pipeline Folklore** — Pipeline configs understood only by their creator with no ordering rationale docs.

## My Position for the Docstitution

Automated tests are the most reliable documentation a project possesses. A Gherkin scenario passing every build is a verified, living specification that cannot drift from reality. The Docstitution must recognize executable specifications—particularly BDD/Gherkin—as first-class documentation. When prose and tests disagree, tests tell truth.

This does not eliminate prose. Prose describes context and rationale—the "why" tests cannot capture. The Docstitution should define complementary tiers: executable specs for behavior, narrative docs for context. Feature docs should cross-reference their Gherkin scenarios. When an agent needs to know whether a feature works, it checks the test report—not a document from months ago.
