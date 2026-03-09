<!--
---
document_type: governing-document
title: "Article I: Foundational Principles"
status: ratified
owner: convention-committee
audience: [humans, agents]
last_verified: 2026-03-09
review_cadence: annual
tags: [principles, dual-audience, freshness, ownership, accessibility]
sections:
  - dual-audience-primacy
  - proximity
  - freshness-as-quality
  - verifiability
  - readability
  - ownership
  - accessibility
related_articles:
  - article-II-document-types-and-taxonomy
  - article-III-lifecycle-governance
  - article-IV-structure-and-format-standards
  - article-V-roles-and-responsibilities
  - article-VI-tooling-and-infrastructure
  - article-VII-amendment-process
---
-->

# Article I: Foundational Principles

These seven principles are the non-negotiable values of the Docstitution. Every Article, standard, and practice defined elsewhere must be consistent with them. When principles conflict in practice, the resolution guidance in each section applies.

---

## Section 1. Dual-Audience Primacy

**Declaration.** Every document shall be consumable by both humans and software agents. No document may serve one audience at the exclusion of the other.

**Rationale.** Documentation now has two classes of reader: people who need to understand systems, and agents that need to traverse, query, and act on that knowledge. A document locked in unstructured prose fails agents; one reduced to raw schema fails humans. The Convention affirmed this with near-unanimity.

**Guidance.**

- Adopt a *dual-layer* structure: structured metadata (YAML frontmatter, semantic headings, typed cross-references) forms the frame; narrative prose fills it. See [Article IV](article-IV-structure-and-format-standards.md) for format requirements.
- Metadata headers are mandatory on every document. At minimum: `document_type`, `title`, `owner`, `audience`, and `last_verified`.
- When a document is primarily for one audience, it must still be *traversable* by the other. An agent-facing schema must include a human-readable summary. A narrative tutorial must include structured metadata for agent discovery.

---

## Section 2. Proximity

**Declaration.** Documentation shall live with the artifact it describes. Code-adjacent documents reside in the repository alongside the code. Infrastructure documents reside with the infrastructure definitions.

**Rationale.** Documentation separated from its subject decays faster, is discovered less often, and drifts silently. Colocation keeps documents in the same review cycle, version history, and ownership structure as the artifact.

**Guidance.**

- READMEs, ADRs, API specs, inline comments, and runbooks belong in the repository they describe.
- Cross-cutting documents (style guides, glossaries, governance policies) belong in a governed central location with explicit cross-references to the repositories they affect. See [Article II](article-II-document-types-and-taxonomy.md) for the classification of which types colocate and which centralize.
- A document that cannot be found by someone working on the related artifact is a document that does not exist.

---

## Section 3. Freshness as Quality

**Declaration.** A stale document is worse than a missing document. Every document shall carry a freshness indicator, and staleness shall be actively detected and remediated.

**Rationale.** Stale documentation teaches falsehoods with the authority of the written word. Missing documentation at least signals a gap. Freshness is not a maintenance task—it is a quality dimension.

**Guidance.**

- Every document must include a `last_verified` date in its metadata, representing when a human or automated process last confirmed the document reflects reality.
- Teams shall define freshness SLOs per document type. [Article III](article-III-lifecycle-governance.md) establishes review cadences and staleness thresholds.
- Automated staleness detection should run in CI where possible. Documents exceeding their freshness SLO must be flagged, not silently ignored. See [Article VI](article-VI-tooling-and-infrastructure.md) for tooling requirements.
- When a stale document cannot be updated promptly, it must be visibly marked as potentially inaccurate.

---

## Section 4. Verifiability

**Declaration.** Documentation shall be testable and verifiable where possible. When executable specifications and prose disagree, a defined reliability hierarchy determines which is authoritative.

**Rationale.** Prose can describe intent that no longer matches behavior. Tests prove current behavior but cannot explain purpose. Both are necessary. The Convention resolved this by establishing a reliability hierarchy: executable specifications are highest-fidelity, generated documents are next, and authored prose provides irreplaceable context.

**Guidance.**

- A documentation reliability hierarchy governs authoritativeness: executable specifications (highest fidelity for current behavior), generated documentation (accurate but lacking intent), and authored prose (irreplaceable for intent and context). See [Article II](article-II-document-types-and-taxonomy.md) for the full tier definitions and classification.
- When prose contradicts an executable spec, the spec describes what the system does; the prose describes what it should do. Both are signals. The discrepancy must be resolved, not ignored.
- Doc-tests, example validation, and link checking should be integrated into CI pipelines. See [Article VI](article-VI-tooling-and-infrastructure.md).

---

## Section 5. Readability

**Declaration.** A document that cannot be understood by its intended audience has failed its purpose, regardless of its technical accuracy.

**Rationale.** Documentation exists to transfer understanding. Accuracy without comprehension is trivia. Every document has a declared audience, and it must meet that audience where they are—in vocabulary, assumed context, and cognitive load.

**Guidance.**

- Declare the intended audience in document metadata. Write for that audience's vocabulary and expertise level.
- Prefer plain language. Define jargon on first use or link to a shared glossary.
- Use semantic heading hierarchy, lists, and short paragraphs. Undifferentiated text fails both human scanning and agent parsing.
- Mandate diagram-as-code (Mermaid, PlantUML, or equivalent) for architectural visuals. Require alt text and text descriptions for all visual content so that diagrams are accessible in plain-text environments. See [Article IV](article-IV-structure-and-format-standards.md) for structural standards.

---

## Section 6. Ownership

**Declaration.** Every document shall have a named, current steward accountable for its accuracy and freshness. A document with no owner is a document with no future.

**Rationale.** Unowned documentation is the root cause of most documentation decay. Without a steward, no one is accountable when a document drifts from reality. Ownership creates accountability.

**Guidance.**

- Every document must declare an `owner` in its metadata. The owner is a team or named role, not an individual who may leave.
- Ownership means accountability for freshness, accuracy, and responsiveness to feedback—not sole authorship.
- When an owner changes teams or roles, ownership must transfer explicitly. Orphaned documents must be flagged and reassigned. See [Article V](article-V-roles-and-responsibilities.md) for ownership transfer procedures.
- Ownership of a document does not require expertise in its tooling. It requires commitment to its truth.

---

## Section 7. Accessibility

**Declaration.** Documentation shall be accessible to people with disabilities, to constrained environments, and to all platforms where work is performed. No reader shall be excluded by the format of a document.

**Rationale.** Accessibility is not an enhancement—it is a baseline. Engineers work in terminals, on mobile devices, through screen readers, and across operating systems. Documentation that requires a specific browser or assumes visual rendering excludes part of its audience by design.

**Guidance.**

- Plain text is the baseline format. Every document must be fully usable when rendered as plain text. Rich rendering (HTML, PDF, interactive) is an enhancement, not a requirement.
- All images and diagrams must include alt text. Diagram-as-code source serves as a machine-readable and screen-reader-friendly alternative to raster images.
- Do not assume a single operating system or shell environment. Where platform-specific instructions are necessary, provide variants or clearly label platform scope.
- Comply with WCAG 2.2 AA for any documentation delivered through web interfaces. See [Article IV](article-IV-structure-and-format-standards.md) for detailed accessibility standards.

---

## Supremacy Clause

These principles govern the interpretation of all subsequent Articles. Where an Article's specific provisions could be read in a manner inconsistent with a foundational principle, the principle prevails. [Article VII](article-VII-amendment-process.md) defines the process for amending these principles, which requires a higher threshold of consensus than amendments to other Articles.
