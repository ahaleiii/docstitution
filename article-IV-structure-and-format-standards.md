<!--
---
document_type: governing-document
title: "Article IV: Structure & Format Standards"
status: draft
owner: convention-committee
audience: [humans, agents]
last_verified: 2025-07-25
review_cadence: annual
tags: [structure, format, metadata, accessibility, cross-references, diagrams-as-code, platform-parity]
cross_references:
  - article-I-foundational-principles.md
  - article-II-document-types-and-taxonomy.md
  - convention/committees/madison-synthesis.md
---
-->

# Article IV: Structure & Format Standards

**Drafted by:** The Article IV Committee — Jenifer, CCPinckney, Lansing, Bedford, Bassett, WSJohnson, Mason, Broom

**Authority:** Derived from the [Madison Synthesis](convention/committees/madison-synthesis.md), Section 5 (Article IV scope), with tension resolutions from Sections 7.1 and 7.8.

**Scope:** How documents are organized, formatted, and made navigable for both human and agent audiences.

**Governing principle:** Structure is the frame; narrative fills it. A well-structured document is readable in a terminal, parseable by an agent, and navigable on any screen.

---

## Section 1. Document Metadata Requirements

### Section 1.1. Mandatory Frontmatter

Every governed document SHALL include a YAML metadata block as its first content element, enclosed in an HTML comment (`<!-- -->`) or a YAML frontmatter fence (`---`).

The following fields are REQUIRED:

| Field | Type | Description |
|---|---|---|
| `document_type` | string | Classification per [Article II](article-II-document-types-and-taxonomy.md) |
| `title` | string | Human-readable document title |
| `status` | enum | One of: `draft`, `active`, `review`, `deprecated`, `archived` |
| `owner` | string | Named individual or team accountable for accuracy |
| `audience` | list | Intended consumers — e.g., `[human-authors, agent-consumers]` |
| `last_verified` | date | ISO 8601 date of the most recent accuracy review |
| `tags` | list | Searchable classification terms |

### Section 1.2. Recommended Metadata

RECOMMENDED fields (include when applicable): `cross_references` (list of related document paths — see [Section 4](#section-4-cross-referencing--discoverability)), `version`, `platform` (e.g., `[windows, macos, linux]`), `created` (ISO 8601), and `supersedes` (path to replaced document).

### Section 1.3. Metadata as Contract

Frontmatter is the structural contract between the document and every system that consumes it — search indexes, linters, agents, and dashboards. Documents missing required fields SHALL fail CI validation, as governed by [Article VI](article-VI-tooling-and-infrastructure.md).

---

## Section 2. Structural Standards

### Section 2.1. Semantic Heading Hierarchy

Headings SHALL convey document structure, not visual styling:

1. Every document begins with exactly one H1 (`#`) matching the `title` metadata field.
2. Heading levels SHALL NOT be skipped — an H3 must be preceded by an H2.
3. Headings SHALL be descriptive and unique within their document.
4. Heading text SHALL describe *content*, not *format* — prefer "Authentication Flow" over "Section 3."

### Section 2.2. Document Length and Decomposition

- **Reference documents** may be long but must be navigable via headings and anchors.
- **Narrative documents** (tutorials, guides, ADRs) SHOULD remain under 1,500 words; decompose into linked sub-documents when exceeded.
- **No monoliths.** A single document covering an entire system has failed before it begins (see [Madison Synthesis, Anti-Pattern 6.3: "The Monolith Document"](convention/committees/madison-synthesis.md#63-structural-failures)).

### Section 2.3. The Dual-Format Principle

Documents SHALL serve both audiences from a single source, per [Article I](article-I-foundational-principles.md) (Principle 1: Dual-Audience Primacy):

- **Structured data** (tables, frontmatter, code blocks, typed lists) enables agent parsing.
- **Narrative prose** provides context, rationale, and mental models for human readers.
- Neither layer is optional.

### Section 2.4. Progressive Disclosure

1. Lead with a summary or purpose statement.
2. Present essential information before supplementary detail.
3. Use collapsible sections or linked sub-pages for advanced content.
4. Organize by task, not by team — documents are navigated by what the reader needs to *do* (see [Madison Synthesis, Anti-Pattern 6.3: "Org-Chart Navigation"](convention/committees/madison-synthesis.md#63-structural-failures)).

### Section 2.5. Fenced Code Block Language Declaration

All fenced code blocks SHALL declare their language identifier (e.g., `` ```python ``, `` ```yaml ``, `` ```json ``). Unlabeled code blocks fail CI validation, impede syntax highlighting, degrade screen reader announcements, and reduce agent parseability. When the content is plain text with no specific language, use `` ```text ``.

---

## Section 3. Accessibility Standards

### Section 3.1. Baseline Compliance

All documentation SHALL meet WCAG 2.2 Level AA as a minimum baseline.

### Section 3.2. Specific Requirements

1. **Images and diagrams** SHALL include `alt` text conveying information content, not visual appearance. ("Three microservices connected via message queue" — not "diagram.png.")
2. **Links** SHALL use descriptive text. Bare URLs and "click here" are prohibited.
3. **Tables** SHALL include header rows.
4. **Color** SHALL NOT be the sole means of conveying information.
5. **Semantic markup** SHALL replace visual formatting — use emphasis for stress, lists for enumeration.
6. **Heading hierarchy** SHALL be semantic and sequential for screen reader navigation — headings convey document structure, not visual weight (see [Section 2.1](#section-21-semantic-heading-hierarchy)).
7. **Fenced code blocks** SHALL declare their language for screen reader announcement and syntax highlighting (e.g., `` ```python ``, `` ```yaml ``). Unlabeled code blocks are an accessibility and CI failure.
8. **CI pipelines** SHOULD include automated accessibility checks (e.g., alt-text validation, heading-level enforcement, link-text linting). See [Article VI](article-VI-tooling-and-infrastructure.md) for CI requirements.

### Section 3.3. Accessibility and Agent Readability Converge

Semantic headings, descriptive links, alt text, and table headers serve both screen readers and agents. Accessibility is the structural foundation on which agent parseability is built.

---

## Section 4. Cross-Referencing & Discoverability

### Section 4.1. No Orphaned Documents

Every document SHALL be reachable via at least one inbound link from another governed document. A document with no inbound links is undiscoverable (see [Madison Synthesis, Anti-Pattern 6.3: "Orphaned Documents"](convention/committees/madison-synthesis.md#63-structural-failures)).

### Section 4.2. Explicit, Typed Links

Cross-references between documents SHALL be:

1. **Explicit** — rendered as Markdown links, not implicit name-drops.
2. **Typed** — declared in the `cross_references` metadata field for agent traversal.
3. **Bidirectional where practical** — if Document A references Document B, Document B SHOULD reference Document A.

### Section 4.3. Link Integrity

All internal links SHALL be validated by automated tooling in CI. Broken links are structural defects equivalent to failing tests.

---

## Section 5. Visual Documentation Standards

### Section 5.1. Diagram-as-Code Mandate

Architectural and system diagrams SHALL be authored as code using Mermaid, PlantUML, Structurizr DSL, or equivalent text-based diagramming languages. Binary-format diagrams (PNG, JPEG, Visio) are prohibited as primary sources.

**Rationale:** Diagram-as-code is version-controlled, diff-able, and agent-readable — immune to the "Stale Diagram" anti-pattern (see [Madison Synthesis, Anti-Pattern 6.1](convention/committees/madison-synthesis.md#61-staleness--drift)).

### Section 5.2. Diagram Accessibility

Every diagram SHALL include:

1. Descriptive `alt` text when rendered as an image.
2. A plain-text summary adjacent to the diagram source, describing key relationships. This ensures usefulness in plain-text environments where rendering is unavailable.

### Section 5.3. Diagram Scope

Each diagram SHALL illustrate a single concept or relationship. Use layered diagrams (e.g., C4 model levels) for progressive detail.

---

## Section 6. Platform & Environment Considerations

### Section 6.1. Plain-Text Baseline

Every document SHALL be fully useful when rendered as plain text. Markdown is the primary authoring format; rich rendering (HTML, PDF) is an enhancement, never a prerequisite.

- Documents SHALL be readable with `cat`, `less`, or `Get-Content`.
- No document SHALL require a browser or proprietary viewer for its core content.
- The plain-text representation IS the agent interface.

### Section 6.2. Platform Parity

Documentation SHALL NOT assume a single operating system, shell, or toolchain:

1. **Commands** SHALL include equivalents for all supported platforms, or use platform-agnostic alternatives (see [Madison Synthesis, Anti-Pattern 6.4: "Platform Afterthought"](convention/committees/madison-synthesis.md#64-audience--usability-failures)).
2. **File paths** SHALL use forward-slash notation or provide platform-specific variants.
3. **Platform metadata** — documents specific to a platform SHALL declare so in the `platform` metadata field.

### Section 6.3. Responsive Considerations

Documentation rendered in web formats SHALL be readable on mobile viewports without horizontal scrolling. Wide tables SHOULD include responsive alternatives.

### Section 6.4. Conditional Content Blocks

When a single document must address multiple platforms, use clearly marked conditional sections with platform-specific headings:

```markdown
#### On macOS / Linux

\`\`\`bash
export API_KEY="your-key"
\`\`\`

#### On Windows

\`\`\`powershell
$env:API_KEY = "your-key"
\`\`\`
```

Platform-specific content SHALL be demarcated by headings — never buried in parenthetical asides.

---

## Ratification Notes

This Article resolves tensions identified in the [Madison Synthesis](convention/committees/madison-synthesis.md):

- **Tension 1 (Human vs. Machine):** The Dual-Format Principle ([Section 2.3](#section-23-the-dual-format-principle)) — lightweight structure enables agents; narrative preserves human readability.
- **Tension 8 (Visual vs. Plain):** Diagram-as-Code ([Section 5.1](#section-51-diagram-as-code-mandate)) and Plain-Text Baseline ([Section 6.1](#section-61-plain-text-baseline)) — text source is authoritative; rendered output is enhancement.

This Article implements [Article I](article-I-foundational-principles.md) principles of Dual-Audience Primacy, Readability, and Accessibility, and provides the structural vocabulary referenced by [Article II](article-II-document-types-and-taxonomy.md) document type definitions.

---

*Submitted for ratification by the Article IV Drafting Committee*
