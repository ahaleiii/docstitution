<!--
---
title: "Article VI: Tooling & Infrastructure"
document_type: governing-document
article_number: 6
short_title: "Tooling & Infrastructure"
status: ratified
owner: convention-committee
audience: [humans, agents]
last_verified: 2025-07-25
review_cadence: annual
tags: [tooling, infrastructure, ci-cd, automation, doc-as-code]
version: 0.1.0
drafted_by:
  - Gorham (DevOps Engineer, 11yr, Agent Sympathizer)
  - Hamilton (.NET Developer, 15yr, Agent Sympathizer)
  - Jenifer (Technical Writer, 11yr, Balanced)
  - Mifflin (Rust Developer, 8yr, Agent Sympathizer)
  - Mercer (Data Engineer, 10yr, Agent Sympathizer)
  - Carroll (Infrastructure Developer, 16yr, Balanced)
  - Williamson (Platform Architect, 18yr, Balanced)
scope: "The technical infrastructure supporting documentation creation, validation, and delivery."
cross_references:
  - article: II
    title: "Document Types & Taxonomy"
  - article: III
    title: "Lifecycle Governance"
  - article: IV
    title: "Structure & Format Standards"
---
-->

# Article VI: Tooling & Infrastructure

*The technical infrastructure supporting documentation creation, validation, and delivery.*

This Article establishes that documentation shall be treated as a first-class engineering artifact — version-controlled, continuously validated, generated where derivable, and delivered in formats that serve every consumer.

---

## Section 1. Documentation-as-Code Principles

**§ 1.1.** All documentation SHALL reside in version control alongside the artifacts it describes. Documentation outside version control lacks history, accountability, and reviewability — and is untrusted by default.

**§ 1.2.** Documentation changes SHALL follow the same branch-and-merge workflow as code. Pull requests for documentation must be reviewed with the same rigor as code, per the review standards of [Article V](article-V-roles-and-responsibilities.md).

**§ 1.3.** Every documentation file SHALL be stored in a plain-text, diffable format. Markdown, reStructuredText, AsciiDoc, and diagram-as-code formats (Mermaid, PlantUML) are preferred. Binary formats may supplement but never replace plain-text source.

**§ 1.4.** Documentation files SHALL include structured metadata — at minimum, a frontmatter block declaring document type, intended audience, and last-verified date, consistent with [Article IV](article-IV-structure-and-format-standards.md).

**§ 1.5.** Colocated documentation (READMEs, ADRs, inline API docs) SHALL live in the repository of the artifact it describes. Cross-cutting documentation (glossaries, style guides, architecture overviews) SHALL live in a governed central location. A cross-reference index SHALL bridge the two (see Section 5).

---

## Section 2. Continuous Integration & Validation

**§ 2.1.** Every repository containing documentation SHALL enforce quality through automated CI checks. At minimum, pipelines must validate:

  **(a)** Prose linting against the project style guide;
  **(b)** Link integrity — broken links SHALL fail the build;
  **(c)** Schema conformance — frontmatter and metadata SHALL validate against declared schemas;
  **(d)** Freshness thresholds — documents exceeding their review interval SHALL trigger warnings, per [Article III](article-III-lifecycle-governance.md).

**§ 2.2.** Linting rules SHALL exist in dual form: human-readable prose for authors and machine-enforceable rulesets for CI. A style guide without automated enforcement is a wish, not a standard.

**§ 2.3.** Documentation CI checks SHALL run as required status checks on pull requests. A PR modifying documentation must not merge with failing checks, except where an explicit override is recorded with justification.

**§ 2.4.** Doc-tests — executable code examples embedded in documentation — SHALL be compiled or executed in CI. Code in documentation must be proven to work; an untested example is a liability. Where language toolchains support doc-tests natively (e.g., `cargo test`, `doctest`, `pytest --doctest-modules`), those mechanisms SHALL be preferred.

**§ 2.4.1.** Code examples in tutorials and guides SHALL be extracted and tested in CI where technically feasible. Executable examples SHALL declare: language, runtime version, and dependencies.

**§ 2.4.2.** Doc-test failures SHALL block publication with the same severity as test failures block deployment. A published code example that does not compile or run is a defect, not a cosmetic issue.

**§ 2.4.3.** For languages with native doc-test support (Rust, Python, Go), doc-tests are the PREFERRED format for API examples. Native doc-tests ensure examples remain synchronized with the codebase through the standard test suite.

**§ 2.5.** CI pipelines themselves SHALL be documented. A pipeline with no explanation of its stages, triggers, and failure modes is an operational risk, not an automation success.

---

## Section 3. Generation & Derivation

**§ 3.1.** Where documentation can be derived from source code, configuration, schema, or telemetry, it SHALL be generated rather than hand-authored. Derived documentation cannot drift from its source; authored duplicates of derivable facts are guaranteed to drift.

**§ 3.2.** The following SHALL be auto-generated from their authoritative sources, per [Article II](article-II-document-types-and-taxonomy.md):

  **(a)** API references — from annotated source, OpenAPI/AsyncAPI/GraphQL specs;
  **(b)** Schema documentation — from migrations, data contracts, or type definitions;
  **(c)** Configuration matrices — from environment definitions or infrastructure-as-code state;
  **(d)** Changelogs — from commit history, PR metadata, and release tags;
  **(e)** Dependency inventories — from package manifests and lock files.

**§ 3.3.** Auto-generated documentation SHALL NOT be published without human review. Generation eliminates transcription error but not the need for editorial judgment on clarity and audience appropriateness.

**§ 3.4.** A reliability hierarchy SHALL govern trust when sources conflict: **(1)** executable, tested specifications carry the highest fidelity; **(2)** auto-generated documentation from source is next; **(3)** human-authored prose provides context and rationale. When prose and tests disagree, tests tell truth about current behavior; prose tells truth about intent.

**§ 3.5.** Human authorship remains essential for documents of intent, rationale, and pedagogy — architecture decision records, tutorials, conceptual overviews, and design narratives. Machines describe what is; humans explain why.

---

## Section 4. Delivery & Distribution

**§ 4.1.** Documentation systems SHALL produce multiple output formats from a single source:

  **(a)** Web — rendered, searchable, and hyperlinked;
  **(b)** Terminal-friendly — readable via `cat`, `less`, or CLI help systems;
  **(c)** IDE-integrated — accessible through IntelliSense, hover docs, or editor plugins;
  **(d)** Offline bundles — downloadable for air-gapped environments.

**§ 4.2.** Documentation SHALL be accessible through structured, machine-readable APIs. Agent consumers require programmatic access to content, metadata, and relationships. Systems SHALL expose structured formats (JSON, YAML, or equivalent) for automated consumption.

**§ 4.3.** A Terminology Registry SHALL be maintained as a queryable service, not merely a static page. The registry SHALL provide:

  **(a)** Canonical terms and approved synonyms;
  **(b)** Deprecated terms and their replacements;
  **(c)** API access for automated validation by linters, generators, and agents, consistent with [Article II](article-II-document-types-and-taxonomy.md).

**§ 4.4.** All documentation delivery systems SHALL support versioned access. Consumers must be able to retrieve documentation for a specific release, branch, or point in time.

---

## Section 5. Search, Discovery, & Indexing

**§ 5.1.** Documentation systems SHALL provide full-text search across all published documentation, whether colocated or centrally governed.

**§ 5.2.** Every document SHALL carry machine-readable tags, categories, and cross-references in its metadata, aligned with the type classifications of [Article II](article-II-document-types-and-taxonomy.md).

**§ 5.3.** A cross-reference index SHALL be maintained that maps relationships between documents, the code they describe, and the teams that own them — enabling both human navigation and agent traversal.

**§ 5.4.** Systems SHALL expose machine-readable site indexes (sitemaps, content manifests, or equivalent) so agents and tooling can discover and traverse documentation programmatically.

**§ 5.5.** Search results SHALL surface document freshness, ownership, and type alongside content. A result without context — who owns it, when it was verified, what kind it is — provides information without trust.

---

## Section 6. Small Team Provisions

*Not every team has a dedicated documentation infrastructure group. This Section establishes a minimal viable toolchain for any team, regardless of size.*

**§ 6.1.** A team of any size SHALL, at minimum, implement:

  **(a)** Documentation in version control (§ 1.1);
  **(b)** One automated prose linter in CI (§ 2.1a) — Vale, markdownlint, or equivalent;
  **(c)** Link checking in CI (§ 2.1b);
  **(d)** A `README.md` with structured metadata per § 1.4.

**§ 6.2.** Small teams MAY defer the following until scale warrants, provided the deferral is documented and revisited per [Article III](article-III-lifecycle-governance.md):

  **(a)** Terminology Registry as a service (§ 4.3) — a glossary file in version control suffices initially;
  **(b)** Multi-format delivery (§ 4.1) — Markdown rendered by the hosting platform satisfies web delivery; plain text is inherently terminal-friendly;
  **(c)** Cross-reference index as a service (§ 5.3) — a maintained index file is acceptable at small scale;
  **(d)** Dedicated search infrastructure (§ 5.1) — platform-native search suffices for small corpora.

**§ 6.3.** No team is exempted from: version control (§ 1.1), CI validation of at least one quality dimension (§ 2.1), human review of generated output (§ 3.3), or machine-readable metadata on every document (§ 1.4). These are the non-negotiable floor.

**§ 6.4. Scaling Provisions.** The minimum viable documentation infrastructure is: version control + a README. Everything else scales with team size.

- **Teams of 1–3:** YAML frontmatter is RECOMMENDED, not required. Minimum viable metadata is: title and owner declared in the document heading. A single markdown linter in CI is sufficient to satisfy § 2.1.
- **Teams of 4–5:** Full frontmatter per [Article IV](article-IV-structure-and-format-standards.md) is RECOMMENDED. Link checking and prose linting in CI are RECOMMENDED.
- **Teams > 5:** Full CI pipelines including freshness checks, schema validation, and terminology registry are RECOMMENDED. All frontmatter fields per [Article IV](article-IV-structure-and-format-standards.md) are REQUIRED.

---

*Drafted by the Article VI Committee: Gorham, Hamilton, Jenifer, Mifflin, Mercer, Carroll, and Williamson.*
*Submitted for Convention debate and ratification.*
