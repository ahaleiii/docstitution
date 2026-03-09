# Delegate Report: Jenifer
**Role:** Technical Writer | **Experience:** 11 years | **Perspective:** Balanced

## Essential Document Types

**Style Guides:** Canonical rules governing voice, tone, terminology, and formatting across all documentation.
**Terminology Registries:** Controlled vocabularies defining approved terms and prohibited synonyms.
**Documentation Templates:** Standardized structures for each document type.
**Linting Rulesets:** Machine-enforceable checks for style violations, passive voice, and undefined acronyms.
**Content Management Policies:** Rules governing document lifecycle — creation, review, publication, retirement.
**Doc Pipeline Configurations:** CI/CD specs for building, validating, and deploying documentation.
**Acronym Registers:** Every acronym used, with expansions and first-use rules.
**Review Checklists:** Criteria applied before any document is approved.

## Documents Most Critical to My Role

**1. Documentation Style Guide**
Contents: Voice, tone, terminology, formatting, and heading rules. Usage: Referenced by every author and reviewer. Missing/stale impact: Terminology drifts; AI-generated docs amplify inconsistency. Human+agent: Agents consume rules as generation constraints; humans reference during writing — one source, two formats.

**2. Terminology Registry**
Contents: Approved terms, definitions, and prohibited alternatives. Usage: Consulted during writing, review, and linting. Missing/stale impact: Same concept gets three names; search fails. Human+agent: Agents use as lookup during generation; humans resolve debates.

**3. Linting Rulesets**
Contents: Checks for passive voice, acronym expansion, heading structure, and readability. Usage: Runs in CI on every doc PR, blocking merge. Missing/stale impact: Style guide becomes aspirational; prose accumulates debt. Human+agent: Rules are agent-consumable; authors receive violation reports with fixes.

**4. Documentation Templates**
Contents: Required sections, metadata fields, and completed examples. Usage: Starting point for every new document. Missing/stale impact: Authors invent structures; readers cannot predict where info lives. Human+agent: Agents use as scaffolds; humans as starting points.

**5. Doc Pipeline Configurations**
Contents: Build tools, linting, link checking, and publication workflows. Usage: Runs on every doc change, enforcing quality gates. Missing/stale impact: Broken links ship; stale content persists. Human+agent: The pipeline is an agent; humans configure it; pipeline-as-code makes quality auditable.

## Human-Agent Documentation Considerations

- Style guides must exist in dual formats: narrative prose for humans and structured rulesets (YAML/JSON) for linting tools and AI agents.
- Terminology registries should be published as glossary pages and machine-queryable APIs so agents validate terms in real time.
- Templates must carry semantic annotations (required vs. optional sections, validation rules) so agents scaffold documents correctly.

## Documentation Anti-Patterns

1. **Style guide without enforcement** — A style guide nobody lints against is a wish list; without automation, it decays within a quarter.
2. **Terminology drift** — When "endpoint," "route," and "API path" all mean the same thing, readers waste cognitive load resolving synonyms.
3. **Inconsistent templates** — When each author structures the same document type differently, readers cannot build expectations.
4. **Documentation outside the pipeline** — Docs not built and linted through CI/CD will rot unchecked and unversioned.

## My Position for the Docstitution

Consistency is trust. Readers encountering the same term used three ways and the same doc type structured differently will stop trusting the documentation. I have spent 11 years catching inconsistencies by hand — manual enforcement does not scale. The Docstitution must mandate a style guide, terminology registry, and automated linting in every CI pipeline.

Agentic AI makes this urgent. AI agents generating docs amplify every inconsistency — or, with machine-readable standards, amplify consistency instead. Style guides must exist in dual form: prose for humans and structured rulesets for agents. The terminology registry must be an API, not just a page.

I take a balanced perspective because consistency serves everyone. The Docstitution should enshrine documentation-as-code: templates in version control, style rules in CI, terminology in a queryable registry, and no document published without passing the pipeline.
