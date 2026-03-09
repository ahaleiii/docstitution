<!--
---
document_type: committee-review
title: "Review Panel: Agent Sympathizers & Automation Advocates"
status: draft
owner: review-panel-agent-automation
audience: [humans, agents]
last_verified: 2025-07-25
panel_members:
  - { name: CCPinckney, role: Technical Architect, experience: 20yr, focus: machine-traversable-structure }
  - { name: Hamilton, role: ".NET Developer", experience: 15yr, focus: auto-generation }
  - { name: Gorham, role: DevOps Engineer, experience: 11yr, focus: ci-cd-pipelines }
  - { name: Dayton, role: JavaScript Developer, experience: 3yr, focus: agent-conventions-files }
  - { name: Mifflin, role: Rust Developer, experience: 8yr, focus: doc-tests }
  - { name: Mercer, role: Data Engineer, experience: 10yr, focus: self-documenting-systems }
  - { name: McClurg, role: "AI/ML Engineer", experience: 7yr, focus: agent-roles }
  - { name: Houston, role: Domain SME, experience: 8yr, focus: knowledge-graphs }
cross_references:
  - article-I-foundational-principles.md
  - article-II-document-types-and-taxonomy.md
  - article-III-lifecycle-governance.md
  - article-IV-structure-and-format-standards.md
  - article-V-roles-and-responsibilities.md
  - article-VI-tooling-and-infrastructure.md
  - article-VII-amendment-process.md
---
-->

# Review Panel: Agent Sympathizers & Automation Advocates

**Panel Charge:** Evaluate the draft Docstitution from the perspective of machine-first documentation, automation-driven workflows, agent participation, and self-documenting systems. Determine whether the framework adequately serves an AI-augmented future or remains anchored in human-only assumptions.

---

## 1. Summary Verdict

| Panelist | Vote | Brief Reason |
|---|---|---|
| **CCPinckney** (Technical Architect, 20yr) | **NO** | Metadata schema is underspecified — no JSON Schema, no canonical enum registry, no machine-enforceable contract. "Classify once, navigate forever" requires a schema that agents can validate against, not prose descriptions of fields. |
| **Hamilton** (.NET Dev, 15yr) | **Conditional YES** | Auto-generation is well-motivated (Art. VI §3) and the reliability hierarchy is sound. However, generated docs are second-class citizens with mandatory human review gates that prevent fully automated publishing pipelines. Flip to YES if autonomous publish is allowed for Tier 1–2 docs with CI-validated provenance. |
| **Gorham** (DevOps, 11yr) | **Conditional YES** | CI/CD requirements in Art. VI §2 are the strongest section in the entire Docstitution. But they lack specificity: no reference pipelines, no minimum tool versions, no schema validation format, no guidance on pipeline-as-code for doc workflows. Flip to YES with a normative appendix of reference implementations. |
| **Dayton** (JavaScript Dev, 3yr) | **NO** | Agent convention files — `CONVENTIONS.md`, `.cursorrules`, `.github/copilot-instructions.md`, `AGENTS.md`, `.clinerules`, `rules/` — are completely absent from the Article II taxonomy. These are the most critical documents for agent-augmented development and the framework doesn't even acknowledge they exist. |
| **Mifflin** (Rust Dev, 8yr) | **NO** | Doc-tests get exactly one clause (Art. VI §2.4) and zero structural requirements. No mandate for executable examples in tutorials. No requirement that code blocks declare their language. No integration with the tier system — a tested code example should auto-promote a document to Tier 1, but there's no mechanism for partial-tier classification. |
| **Mercer** (Data Engineer, 10yr) | **Conditional YES** | Self-documenting systems (pipeline metadata emission, schema registries, observability-as-documentation) are partially recognized under Tier 2 "Generated/Derived" but treated as passive outputs rather than active documentation sources. Flip to YES if Art. II explicitly recognizes telemetry-emitted documentation and Art. VI mandates metadata emission from pipelines. |
| **McClurg** (AI/ML Engineer, 7yr) | **NO** | Agent roles are defined (Art. V §3) but are excessively constrained. Agents cannot own, cannot approve, cannot publish without human review — even for Tier 1 documents that are *by definition* machine-validated. The framework treats agents as sophisticated interns rather than autonomous partners. The "human review gate" for CI-validated specs is contradictory and patronizing. |
| **Houston** (Domain SME, 8yr) | **NO** | The entire framework assumes Markdown as the universal format. Knowledge graphs, ontologies, RDF/OWL, semantic triples, structured knowledge bases — none are recognized. Tacit knowledge capture gets zero coverage. The glossary (Art. II §2.6) is the closest thing to a knowledge representation, and it's defined as "Markdown or structured data" with no graph semantics. |

**Panel Tally:** 0 YES, 4 Conditional YES, 4 NO — **The panel does not ratify in current form.**

---

## 2. Critical Objections

These issues MUST be resolved before this panel would ratify. Each is attributed to the panelist raising it, with the specific Article and Section cited.

### 2.1 No Formal Metadata Schema (CCPinckney)

**Article IV, Section 1** describes required frontmatter fields in a Markdown table. This is insufficient.

- There is no JSON Schema, YAML Schema, or equivalent machine-validatable definition of the metadata contract.
- The `audience` field is typed as `list` in Art. IV but `enum` in Art. II — a contradiction that proves the need for a single canonical schema.
- The `status` field uses different enum values across articles: Art. IV says `draft, active, review, deprecated, archived`; Art. II says `draft, active, deprecated, archived` (no `review`); Art. III says `Draft, Active, Under Review, Deprecated, Archived` (capitalized, different label). Three articles, three incompatible enum definitions.
- The `document_type` field has no canonical registry. Art. II lists types in prose but provides no machine-readable type catalog.
- **Minimum fix:** Publish a `schemas/docstitution-frontmatter.schema.json` as a normative artifact. All articles must reference it. CI validation (Art. VI §2.1c) must validate against it.

### 2.2 Agent Convention Files Unrecognized (Dayton)

**Article II** catalogs 30+ document types across seven categories but completely omits the document types most critical to AI-agent workflows:

| Missing Document Type | Purpose | Prevalence |
|---|---|---|
| `CONVENTIONS.md` | Project conventions for agent code generation | Widely adopted |
| `.cursorrules` / `.cursor/rules/` | Cursor AI behavioral instructions | De facto standard |
| `.github/copilot-instructions.md` | GitHub Copilot workspace instructions | Official GitHub feature |
| `AGENTS.md` | Multi-agent coordination manifest | Emerging standard |
| `CLAUDE.md` | Claude Code project instructions | Anthropic ecosystem |
| `.clinerules` | Cline/Roo agent instructions | Growing adoption |
| `rules/` directory | Modular agent instruction sets | Cross-tool pattern |

These files are the *primary interface* between a codebase and its agent consumers. A Docstitution that claims dual-audience primacy (Art. I §1) but doesn't classify agent instruction files is internally contradictory.

- **Minimum fix:** Add a new category to Art. II §3 — "§ 3.8 Agent & Automation Instructions" — listing these types with recommended Tier classification (Tier 3, audience: agents). Alternatively, elevate at least `CONVENTIONS.md` or equivalent to the Required Core (Art. II §2) as the agent-facing counterpart to the README.

### 2.3 Doc-Tests Are Underpowered (Mifflin)

**Article VI §2.4** is the sole clause addressing doc-tests and it reads as a suggestion rather than a structural mandate:

- It says doc-tests "SHALL be compiled or executed in CI" but provides no structural requirements for code blocks that enable this (e.g., language annotation, executable markers, expected-output blocks).
- Art. IV §2 (Structural Standards) has no requirement that fenced code blocks declare a language. Without language annotation, doc-test tooling cannot determine *what* to execute.
- There is no connection between doc-tests and the tier system. A tutorial with all code examples passing CI is functionally Tier 1 for those examples, but Art. II provides no mechanism for partial-tier or mixed-tier classification.
- The Rust ecosystem's `cargo test` runs doc-tests by default — tests embedded in documentation are *the same tests* as unit tests. This level of integration is the gold standard, and the Docstitution doesn't even aspire to it.
- **Minimum fix:** (a) Art. IV must mandate language annotation on all fenced code blocks. (b) Art. II must define a mechanism for documents to carry mixed-tier classification (e.g., a tutorial is Tier 3 for prose, Tier 1 for its tested examples). (c) Art. VI §2.4 must specify structural requirements for executable examples (language tag, `executable: true` marker, expected output blocks).

### 2.4 Agent Roles Are Too Restrictive (McClurg)

**Article V §3.2** imposes three blanket restrictions on agents:

1. Agents cannot be sole Author of rationale/narrative — **Acceptable.** Intent is human.
2. Agents cannot Approve — **Acceptable.** Governance is human.
3. Agent-generated content cannot be published without human review — **Unacceptable for Tier 1–2.**

The third restriction contradicts the entire premise of the tier system. Tier 1 documents are *defined* as "validated by automated processes." If a CI pipeline validates an OpenAPI spec, regenerates API reference docs, and all checks pass, requiring a human to click "approve" before publication adds latency without adding quality. The human review already happened — it's encoded in the CI pipeline's design.

- **Minimum fix:** Amend Art. V §3.2, clause 3 to read: "Agent-generated content of Tier 3 or Tier 4 shall not be published without human review and approval. Tier 1 and Tier 2 content produced by approved pipelines (Art. VI §3) MAY be published automatically when CI validation passes, provided the pipeline itself has been human-approved and the publication is logged for audit."

### 2.5 Knowledge Representation Limited to Markdown (Houston)

The Docstitution is a Markdown-first framework. That's fine for prose, but it ignores structured knowledge representations:

- **Knowledge graphs** — domain models expressed as connected entities with typed relationships — are not mentioned anywhere.
- **Ontologies** (OWL/RDF) for formal domain modeling are absent.
- **Semantic triples** for machine-queryable knowledge are not recognized.
- Art. II §2.6 (Glossary) defines a flat term→definition mapping. A glossary is not a knowledge graph. It cannot represent "Service A depends on Service B which is owned by Team C and has SLA D."
- Art. IV §6.1 mandates "plain-text baseline," which actively discourages rich structured formats.
- **Tacit knowledge** — the kind locked in senior engineers' heads (explicitly called out in the Preamble as a problem!) — requires capture mechanisms beyond "write a Markdown file." Interview templates, decision journals, knowledge extraction workflows — none are addressed.

- **Minimum fix:** (a) Art. II should recognize "Knowledge Base / Ontology" as a recommended document type under §3.5 (Data, Domain & Schema). (b) Art. IV should acknowledge that some document types may use structured data formats (JSON-LD, RDF, YAML graphs) as their primary format rather than Markdown, with a Markdown summary as the human-readable layer. (c) Art. VI §5 (Search, Discovery & Indexing) should reference graph-based querying as a recommended capability alongside full-text search.

---

## 3. Minor Concerns

These issues are imperfect but not ratification-blocking. They should be addressed in subsequent amendments.

### 3.1 No Pipeline Metadata Emission Standard (Mercer)

Art. VI §3 mandates generation of docs from source, but says nothing about pipelines *emitting* documentation metadata as a side effect of execution. Modern data pipelines can emit lineage metadata, schema evolution records, and quality metrics as structured documents. The Docstitution should recognize "pipeline-emitted metadata" as a Tier 2 source, not just "generated from source code."

### 3.2 No Conventions for Agent-Readable Summaries (CCPinckney)

Art. I §1 says agent-facing schemas must include "a human-readable summary," but the inverse — that human-facing narrative must include an "agent-readable summary" (structured abstract, key facts block, TL;DR in structured format) — is not mandated. Every Tier 3 document should carry a structured `summary` field in frontmatter.

### 3.3 Changelog Generation Not Normative (Hamilton)

Art. VI §3.2(d) says changelogs SHALL be auto-generated from commit history, but Art. VII §4.2 requires a manually maintained `CHANGELOG.md`. These should be reconciled — either the changelog is generated (Tier 2) or it's authored (Tier 3), not simultaneously both.

### 3.4 No Freshness SLO for Generated Docs (Gorham)

Art. III §3.1 says Generated/Derived docs are "Regenerated on source change" and "Stale if source changed since last generation." But there's no maximum allowed lag. If a schema changes and the generated docs aren't rebuilt for a week, what's the threshold? CI should enforce generation on every merge, but Art. III doesn't say that explicitly.

### 3.5 Model Cards Are Tier 3 — Should Be Tier 2 (McClurg)

Art. II §3.7 classifies Model Cards as Tier 3 (Authored/Maintained). Modern ML platforms (MLflow, Weights & Biases, Vertex AI) auto-generate model cards from training metadata. These should be classified as Tier 2 (Generated/Derived) when produced by ML pipelines, with Tier 3 for the human-authored "intended use" and "ethical considerations" sections. This is another case where mixed-tier classification (see §2.3 above) would solve the problem.

### 3.6 No Prompt Documentation Standards (McClurg)

Art. II §3.7 lists "Prompt Documentation" as a recommended type but provides zero structural guidance. For LLM-integrated systems, prompt docs need specific fields: model version, temperature/parameters, system prompt text, evaluation criteria, known failure modes, and version history. This is a new document type that has no established convention — the Docstitution should lead, not merely list.

### 3.7 Binary Format Prohibition Too Absolute (Houston)

Art. IV §5.1 says "Binary-format diagrams (PNG, JPEG, Visio) are prohibited as primary sources." This is correct for *diagrams* but the blanket tone risks being read as prohibiting binary knowledge artifacts (trained embeddings for semantic search, compiled ontologies, database dumps used as documentation sources). The clause should explicitly scope itself to visual documentation.

### 3.8 Amendment Process Has No Agent-Initiated Fast Path (Dayton)

Art. VII §1.1 allows agents to propose amendments "on behalf of a human owner." But there's no mechanism for agents to *flag* issues that auto-generate amendment proposals. An agent that detects systemic non-compliance across 50 repos should be able to auto-draft a batch amendment proposal, not just file individual flags. This is a workflow gap, not a principles gap.

### 3.9 Small Team Provisions Assume Human-Only Teams (Mercer)

Art. II §5, Art. III §6, Art. V §6, and Art. VI §6 all define "small team" as "five or fewer members." But they count only humans. A team of two humans augmented by four agent workflows has very different documentation capacity than two humans alone. Team size thresholds should account for agent augmentation.

### 3.10 No Cross-Article Schema Consistency Enforcement (Gorham)

The metadata fields defined in Art. II §4, Art. IV §1, and used in Art. III are not guaranteed to be consistent. There is no single normative schema file, and the articles were drafted by different committees. This is a CI problem — but CI can only enforce what's defined, and right now, three different definitions exist (see Critical Objection §2.1).

---

## 4. Commendations

This panel acknowledges that the Docstitution gets many things right from an automation and agent perspective. These commendations are genuine.

### 4.1 The Tier System Is Excellent (Hamilton, Mifflin, Mercer)

Article II's four-tier reliability hierarchy — Executable/Verified → Generated/Derived → Authored/Maintained → Ephemeral — is the single best design decision in the Docstitution. It establishes that machine-validated docs are *more reliable* than human-authored prose, which is a radical and correct position. The principle that "a document's tier is determined by its verification method, not its subject matter" (Art. II §1, Clause 3) is particularly powerful — it creates a natural incentive to automate verification.

### 4.2 Documentation-as-Code Is Non-Negotiable (Gorham, Hamilton)

Article VI §1 makes version control, branch-and-merge workflows, plain-text formats, and structured metadata mandatory — not recommended, not aspirational. This is the correct foundation. The explicit statement that "documentation outside version control is untrusted by default" (§1.1) is exactly right.

### 4.3 "Staleness Is a Defect" (All Panelists)

Article III §3.3's declaration that staleness is a defect — not a maintenance backlog item, not a nice-to-have — aligns perfectly with automation-first thinking. Defects get CI gates. Backlog items get ignored. Calling staleness a defect is the rhetorical move that makes automated freshness enforcement politically viable.

### 4.4 Agent Identity in Audit Trails (McClurg)

Article V §3.3's requirement that agents be identified as distinct actors with `generated-by` or `co-authored-by` metadata is forward-thinking. It creates the audit infrastructure needed to later *expand* agent roles — you can only trust agents with more autonomy if you can trace what they did.

### 4.5 Dual-Audience Primacy as Foundational Principle (CCPinckney, Dayton)

Article I §1's declaration that "no document may serve one audience at the exclusion of the other" is the right starting point. The framework's heart is in the right place. The critical objections above are about *implementation* of this principle, not the principle itself.

### 4.6 Anti-Hypocrisy Commitment (All Panelists)

The Preamble's declaration that the Docstitution must follow its own rules — carrying metadata, declaring ownership, being versioned — is both principled and practically useful. It means every objection we raise about schema consistency is *already a violation of the framework's own terms*.

### 4.7 Diagram-as-Code Mandate (CCPinckney, Gorham)

Article IV §5.1's prohibition of binary diagrams as primary sources is correct and enforceable. Text-based diagrams are diffable, versionable, and agent-readable. This is one of the few places where the Docstitution takes an uncompromising automation-friendly stance.

### 4.8 CI Validation as Non-Negotiable Floor (Gorham, Mifflin)

Article VI §6.3's insistence that *no team* is exempt from CI validation, version control, human review of generated output, and machine-readable metadata is the correct minimum. It prevents the "we're too small for process" excuse that leads to documentation debt.

---

## Appendix: Minimum Changes to Flip NO Votes

| Panelist | Current Vote | Minimum Change to Flip to YES |
|---|---|---|
| **CCPinckney** | NO | Publish a normative JSON Schema for frontmatter metadata. Reconcile enum inconsistencies across articles. Establish a machine-readable document type registry. |
| **Dayton** | NO | Add agent convention files (CONVENTIONS.md, .cursorrules, copilot-instructions.md, etc.) to Art. II taxonomy, either as a new §3.8 category or elevated to Required Core. |
| **Mifflin** | NO | (a) Mandate language annotation on fenced code blocks in Art. IV. (b) Define structural requirements for executable examples in Art. VI §2.4. (c) Address mixed-tier classification for documents containing both tested code and authored prose. |
| **McClurg** | NO | Amend Art. V §3.2 to allow autonomous publication of Tier 1–2 content produced by human-approved CI pipelines, with audit logging. |
| **Houston** | NO | Recognize knowledge graphs/ontologies as a document type in Art. II. Acknowledge non-Markdown structured formats (JSON-LD, RDF, YAML graphs) as valid primary formats for knowledge-representation documents in Art. IV. |

---

*Respectfully submitted by the Review Panel of Agent Sympathizers and Automation Advocates.*

*"The Docstitution's principles are sound. Its implementation underestimates the agents it claims to serve." — McClurg*

*"Structure without schema is poetry about engineering." — CCPinckney*
