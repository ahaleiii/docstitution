<!--
---
document_type: governing-document
title: "Article II: Document Types & Taxonomy"
article_number: 2
status: draft
audience: [humans, agents]
owner: convention-committee
last_verified: 2025-07-25
review_cadence: semi-annual
tags: [taxonomy, document-types, tiers, required-core, metadata]
tier: 3
related_articles: [1, 3, 4]
committee:
  - { name: Madison, role: Documentation Architect, focus: taxonomy }
  - { name: Jenifer, role: Tech Writer, focus: templates }
  - { name: CCPinckney, role: Technical Architect, focus: classification }
  - { name: Brearly, role: API Specialist, focus: api_types }
  - { name: RMorris, role: Ops Lead, focus: operational_types }
  - { name: Pierce, role: "BA/SME", focus: domain_types }
  - { name: Randolph, role: Product Owner, focus: product_types }
  - { name: Wythe, role: Compliance Architect, focus: compliance_types }
---
-->

# Article II: Document Types & Taxonomy

*Ratified by the Docstitution Convention*

---

## Section 1. Taxonomy Framework

**Clause 1.** All documentation governed by this Docstitution shall be classified into one of four tiers, ordered by verifiability and reliability. This hierarchy resolves the Convention's central tension between auto-generated and human-authored content ([Madison Synthesis](convention/committees/madison-synthesis.md) §4.1, §4.3) by establishing that both are necessary and that each has a defined place.

**Clause 2.** The four tiers are:

| Tier | Name | Description | Reliability | Authorship |
|------|------|-------------|-------------|------------|
| **1** | **Executable / Verified** | Artifacts validated by automated processes — tests, doc-tests, OpenAPI specs checked in CI, contract tests. When prose and Tier 1 artifacts disagree, Tier 1 tells the truth about current behavior. | Highest | Machine-validated |
| **2** | **Generated / Derived** | Documentation auto-generated from code, configuration, schema, or telemetry — API references, schema docs, environment matrices, changelogs. Accurate by derivation; freshness tied to generation pipeline. | High | Machine-generated, human-reviewed |
| **3** | **Authored / Maintained** | Human-written narrative providing intent, rationale, context, and instruction — ADRs, tutorials, runbooks, design documents. These explain *why*, not merely *what*. | Moderate | Human-authored |
| **4** | **Ephemeral / Ceremonial** | Time-bound artifacts with short useful lifespans — sprint backlogs, meeting minutes, status reports, retrospective notes. Valuable in context; archived, not maintained. | Transient | Either |

**Clause 3.** A document's tier is determined by its verification method, not its subject matter. An API specification validated in CI is Tier 1; the same specification maintained manually is Tier 3. Teams are encouraged to promote documents to higher tiers by adding automated validation (see [Article VI](article-VI-tooling-and-infrastructure.md)).

**Clause 4.** When a document of a lower tier contradicts a document of a higher tier, the higher-tier document shall be presumed authoritative regarding factual accuracy. However, Tier 3 documents remain authoritative regarding intent and rationale — executable tests verify behavior, not purpose.

---

## Section 2. Required Core Document Types

**Clause 1.** Every software project governed by this Docstitution shall maintain, at minimum, the following six document types. This small core reflects the Convention's compromise between minimalists and comprehensive documenters ([Madison Synthesis](convention/committees/madison-synthesis.md) §4.2): a lean mandatory set, rigorously maintained. Teams must justify omitting any core type through a documented exception in their ADR log.

### § 2.1 README

> **Tier:** 3 · **Audience:** Both · **Format:** Markdown (`README.md` at root) · **Owner:** Project lead

The README is the front door. It shall contain: project purpose, quickstart instructions, prerequisites, build commands, links to further documentation, and ownership information. Quickstart steps should be validated in CI where feasible ([Article I](article-I-foundational-principles.md), Verifiability).

### § 2.2 Architecture Decision Record (ADR) Log

> **Tier:** 3 · **Audience:** Both · **Format:** Markdown (`docs/adr/`, numbered) · **Owner:** Technical lead

Each ADR shall record: title, date, status (proposed/accepted/deprecated/superseded), context, decision, and consequences. ADRs prevent decision amnesia ([Madison Synthesis](convention/committees/madison-synthesis.md) §6.2).

### § 2.3 API Specification

> **Tier:** 1 or 2 · **Audience:** Both · **Format:** OpenAPI, AsyncAPI, GraphQL SDL, or gRPC protobuf · **Owner:** Service team

The API specification shall be the single source of truth for service interfaces. Human-readable documentation may be generated from it (Tier 2), but the machine-readable spec is canonical.

### § 2.4 Runbook

> **Tier:** 3 (Tier 1 if steps are executable) · **Audience:** Both · **Format:** Markdown, structured steps · **Owner:** Service-owning team

Runbooks shall be simultaneously human-readable and machine-parseable. Each must include: service name, alert-to-runbook mapping, diagnostic steps, remediation procedures, escalation paths, and rollback instructions.

### § 2.5 Style Guide

> **Tier:** 3 · **Audience:** Both · **Format:** Markdown; linting rules derived where possible (Article VI) · **Owner:** Documentation or engineering lead

The style guide governs documentation conventions: tone, terminology, formatting, heading structure, and metadata requirements. It ensures consistency as defined in [Article IV](article-IV-structure-and-format-standards.md) and prevents the Snowflake Document anti-pattern ([Madison Synthesis](convention/committees/madison-synthesis.md) §6.3).

### § 2.6 Glossary

> **Tier:** 3 (Tier 2 if partially generated) · **Audience:** Both · **Format:** Markdown or structured data (YAML/JSON) · **Owner:** Technical writer or domain expert

The glossary defines project and domain terminology, establishing shared vocabulary between stakeholders, engineers, and agents. Terms shall include: name, definition, context of use, and related terms.

### § 2.7 Getting Started Guide

> **Tier:** 3 (Authored/Maintained) · **Audience:** Humans (primarily), Agents · **Format:** Markdown (`docs/getting-started.md` or equivalent) · **Owner:** Team lead or onboarding coordinator

The Getting Started Guide enables new team member onboarding and is the first document a newcomer reads after the README. It shall contain: prerequisites, environment setup instructions, a first-task walkthrough, and links to deeper documentation. The guide shall be written in step-by-step format with clear success criteria at each stage. *Small team provision:* Teams of fewer than five members may combine the Getting Started Guide with the README, provided the onboarding content is clearly demarcated by heading.

---

## Section 3. Recommended Document Types

**Clause 1.** Beyond the Required Core, the following document types are recommended based on project context. This catalog organizes the Convention's 160+ identified types ([Madison Synthesis](convention/committees/madison-synthesis.md) §1) into functional categories. Teams adopt types as needs arise; no justification is required for omission.

**Clause 2.** Recommended types are organized by functional category:

### § 3.1 Architecture & Design

| Document Type | Tier | Audience | When to Adopt |
|---|---|---|---|
| System Architecture Document | 3 | Both | Multi-service systems |
| Service Dependency Map | 2–3 | Both | 3+ services |
| Technical Design Document | 3 | Humans | Complex features requiring upfront design |

### § 3.2 API, Code & Interface

| Document Type | Tier | Audience | When to Adopt |
|---|---|---|---|
| API Changelog | 2 | Both | Multi-consumer APIs |
| API Error Catalog | 2–3 | Both | Complex error domains |
| CHANGELOG | 2–3 | Both | All projects (strongly recommended) |
| CONTRIBUTING Guide | 3 | Humans | Open-source or multi-team projects |

### § 3.3 Onboarding & Learning

| Document Type | Tier | Audience | When to Adopt |
|---|---|---|---|
| Getting Started Guide | 3 | Humans | Frequent onboarding |
| Tutorials | 3 | Humans | Complex or public-facing domains |
| Troubleshooting Guide | 3 | Both | Production services |

### § 3.4 Operations, Reliability & Deployment

| Document Type | Tier | Audience | When to Adopt |
|---|---|---|---|
| Incident Response Playbook | 3 | Both | Services with SLAs |
| Incident Post-Mortem | 3 | Both | After significant incidents |
| SLO/SLA Definitions | 3 | Both | Reliability targets exist |
| Deployment Guide | 3 | Both | Multi-environment deployments |
| Rollback Procedures | 3 | Both | Production deployments |

### § 3.5 Data, Domain & Schema

| Document Type | Tier | Audience | When to Adopt |
|---|---|---|---|
| Data Dictionary | 2–3 | Both | Significant data models |
| Schema Documentation | 2 | Both | Database-backed services |
| Domain Model / Business Rules | 3 | Both | Domain-driven or complex logic |

### § 3.6 Security, Compliance & Governance

| Document Type | Tier | Audience | When to Adopt |
|---|---|---|---|
| Threat Model | 3 | Both* | Sensitive data handling |
| Compliance Mapping | 3 | Both | Regulated industries |
| Secure Coding Guidelines | 3 | Both | All projects (strongly recommended) |

\* *Security-sensitive documents may require access classification per Article V.*

### § 3.7 Product, Process & AI/ML

| Document Type | Tier | Audience | When to Adopt |
|---|---|---|---|
| Product Requirements (PRD) | 3 | Both | Feature-driven development |
| Decision Log | 3 | Both | Cross-functional teams |
| Definition of Done | 3 | Both | Agile teams |
| Model Cards | 3 | Both | ML model deployments |
| Prompt Documentation | 3 | Both | LLM-integrated systems |

### § 3.8 Agent & Automation Conventions

| Document Type | Tier | Audience | When to Adopt |
|---|---|---|---|
| `CONVENTIONS.md` — Project Conventions for AI Coding Agents | 3 | Agents (primarily), Humans | Any project using AI coding agents |
| `.github/copilot-instructions.md` — GitHub Copilot Workspace Instructions | 3 | Agents (primarily), Humans | Projects using GitHub Copilot |
| Agent Rule Files (`.cursorrules`, `.clinerules`, `rules/`) — IDE-specific Agent Configuration | 3 | Agents (primarily), Humans | Projects using IDE-integrated agents |
| `AGENTS.md` — Agent Capabilities, Boundaries & Delegation Patterns | 3 | Agents (primarily), Humans | Projects with multi-agent workflows |

Agent convention files define how AI coding agents interact with the codebase. They are Tier 3 (Authored/Maintained) because they encode human intent about agent behavior and require human judgment to author and update.

### § 3.9 Knowledge Representation

| Document Type | Tier | Audience | When to Adopt |
|---|---|---|---|
| Knowledge Graphs / Ontologies (JSON-LD, RDF, YAML) | 2–3 | Both | Complex domain modeling, semantic interoperability |
| Domain Model Specifications | 3 | Both | Domain-driven design, cross-team alignment |

Knowledge representation documents may use non-Markdown structured formats (JSON-LD, RDF, YAML, OWL) as their primary format when the content is inherently structured data. These formats are valid primary formats for knowledge-representation documents and are not subject to the Markdown-first requirement of [Article IV](article-IV-structure-and-format-standards.md), provided they include human-readable annotations or an accompanying narrative summary.

---

## Section 4. Document Type Metadata Requirements

**Clause 1.** Every document governed by this Docstitution shall declare structured metadata as specified in [Article IV](article-IV-structure-and-format-standards.md). This reflects the near-universal consensus (25+ delegates, [Madison Synthesis](convention/committees/madison-synthesis.md) §2.6) that metadata is the navigation system, not optional ornamentation.

> **Normative Note:** This Section is the NORMATIVE source for document metadata field definitions. Other Articles (including [Article IV](article-IV-structure-and-format-standards.md) and [Article III](article-III-lifecycle-governance.md)) reference this Section rather than restating the field requirements. Where a conflict exists between metadata field definitions stated here and those stated elsewhere, this Section governs.

**Clause 2.** Required metadata fields for every document:

| Field | Type | Description |
|-------|------|-------------|
| `document_type` | string | Canonical type from this taxonomy |
| `title` | string | Human-readable title |
| `tier` | integer (1–4) | Taxonomy tier per Section 1 |
| `audience` | enum | `human`, `agent`, or `both` |
| `status` | enum | `draft`, `active`, `deprecated`, `archived` |
| `owner` | string | Named individual or team |
| `last_verified` | date | ISO 8601 date of last review |

**Clause 3.** Recommended additional metadata fields:

| Field | Type | Description |
|-------|------|-------------|
| `requires_review_by` | date | Staleness threshold — triggers review per [Article III](article-III-lifecycle-governance.md) |
| `related_documents` | list | Explicit cross-references |
| `lifecycle_stage` | enum | `inception`, `active`, `maintenance`, `sunset` |
| `generated_by` | string | For Tier 1–2: the pipeline that produces the document |
| `access_classification` | enum | `public`, `internal`, `restricted`, `confidential` |

**Clause 4.** Metadata shall be encoded in YAML frontmatter at the top of each document, as specified by [Article IV](article-IV-structure-and-format-standards.md). Documents missing required fields are non-compliant and shall be flagged during review cycles per [Article III](article-III-lifecycle-governance.md).

---

## Section 5. Small Team Provisions

**Clause 1.** Teams of fewer than five members may adapt this taxonomy through the following provisions. Documentation overhead must remain proportional to team capacity.

**Clause 2. Minimum Viable Documentation Set.** Small teams shall maintain at minimum:

1. **README** — may consolidate quickstart, architecture overview, and key terms
2. **ADR Log** — a single `decisions.md` file may substitute for a directory
3. **API Specification** — required if the project exposes any programmatic interface

**Clause 3. Consolidation Allowance.** Small teams may combine document types into fewer files, provided each logical type retains its own metadata header or clearly demarcated section, and the consolidation is recorded as an ADR.

**Clause 4. Deferred Adoption.** Recommended types may be adopted progressively. Triggers for adoption review:

- Team grows beyond five members → full Required Core (Section 2)
- First production deployment → Runbook and monitoring documentation
- First external API consumer → API Changelog, Versioning Policy, Error Catalog
- First compliance audit → Security and compliance document types
- First major incident → Incident Post-Mortem template and Incident Response Playbook

**Clause 5.** No small team provision exempts a project from the metadata requirements of Section 4. Even consolidated documents must declare their type, owner, audience, and review date. Structure is the frame that scales; it costs little to establish and much to retrofit.

---

*Respectfully submitted by the Article II Drafting Committee: Madison, Jenifer, CCPinckney, Brearly, RMorris, Pierce, Randolph, and Wythe.*

*"Classify once, navigate forever." — CCPinckney*
