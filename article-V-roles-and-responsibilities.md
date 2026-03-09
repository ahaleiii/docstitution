<!--
---
title: "Article V: Roles & Responsibilities"
document_type: governing-document
article: V
status: ratified
owner: convention-committee
audience: [humans, agents]
last_verified: 2026-03-09
review_cadence: annual
tags: [roles, responsibilities, ownership, agents, review-gates]
domain: "Governance — Documentation Roles"
scope: "Who creates, reviews, owns, and maintains documentation"
drafting_committee: [Washington, Gerry, Wythe, King, Read, McClurg, Gilman]
cross_references: [article-I, article-III, article-VI]
---
-->

# Article V: Roles & Responsibilities

*Who creates, reviews, owns, and maintains documentation — and how humans and agents participate as partners in that work.*

---

## Section 1. Documentation Roles

Every act of documentation involves one or more defined roles. These roles govern behavior across the lifecycle stages defined in [Article III](article-III-lifecycle-governance.md).

### § 1.1 Role Taxonomy

| Role | Definition | Eligible Actors |
|---|---|---|
| **Owner** | Accountable steward of a document's accuracy and completeness. | Humans only |
| **Author** | Creator or substantive editor of content. | Humans and Agents |
| **Reviewer** | Evaluates content for correctness, clarity, and compliance. | Humans and Agents |
| **Approver** | Grants publication authority via sign-off. | Humans only |
| **Consumer (Human)** | Reads or depends upon documentation to perform work. | Humans |
| **Consumer (Agent)** | Parses, queries, or acts upon documentation programmatically. | Agents |

### § 1.2 Role Principles

1. **A document may have many Authors but exactly one Owner** — ensuring unambiguous accountability.
2. **Every role carries obligations.** Consumer rights (Section 5.3) create Owner duties.
3. **Roles are not exclusive.** One person may serve multiple roles on different documents — see Section 6.
4. **Agent roles are participatory, not autonomous.** Agents may Author, Review, and Consume, but may not Own or Approve.

---

## Section 2. Human Responsibilities

Humans hold ultimate accountability for the documentation estate.

### § 2.1 Owner Duties

The Owner of a document shall: (a) ensure accuracy, currency, and alignment with the artifact described; (b) respond to reported inaccuracies within [Article III](article-III-lifecycle-governance.md) cadences; (c) initiate deprecation or archival per [Article III](article-III-lifecycle-governance.md); and (d) maintain metadata, classification (Section 5), and cross-references.

### § 2.2 Author & Reviewer Duties

Human Authors shall write for both human and agent audiences per [Article I](article-I-foundational-principles.md), provide the **intent, rationale, and narrative context** that only human judgment can supply, and accept responsibility for any agent-generated content they incorporate. Human Reviewers shall verify accuracy, compliance, and fitness for audience — with particular attention to agent-generated content.

### § 2.3 Documentation in Definition of Done

No feature, service, or system change is complete until: relevant documentation is created or updated, reviewed by at least one non-Author, and metadata is current per [Article IV](article-IV-structure-and-format-standards.md).

---

## Section 3. Agent Participation & Boundaries

AI agents are valued participants in documentation work. Their speed, consistency, and analytical capability strengthen the estate — channeled through accountable governance.

### § 3.1 Permitted Agent Roles

Agents may participate as:

| Capacity | Description |
|---|---|
| **Generator** | Produce draft content from code, schemas, telemetry, or machine-readable sources. |
| **Validator** | Check documents for structural compliance, broken links, staleness, and terminology. |
| **Enforcer** | Flag or block publication of documents failing [Article VI](article-VI-tooling-and-infrastructure.md) validation gates. |
| **Draft Author** | Produce initial drafts of factual or structural documents for human review. |
| **Reviewer (Assistive)** | Identify gaps, inconsistencies, or standards violations for human consideration. |

### § 3.2 Agent Boundaries

1. **Agents shall not be the sole Author of narrative or rationale documentation.** Documents explaining *why* — ADRs, design rationale, tutorials — require a human Author.
2. **Agents shall not Approve documents.** The Approver role is reserved for humans.
3. **Agent-generated content shall not be published without human review and approval.** This gate applies regardless of document type or classification.

### § 3.3 Human Review Gates & Enforcement

The following mechanisms enforce the human review requirement of § 3.2:

1. **`reviewed_by` metadata.** All published documents SHALL include a `reviewed_by` field identifying the human reviewer who approved publication.
2. **`generated_by` metadata.** Agent-generated content SHALL be flagged with a `generated_by` metadata field identifying the agent or pipeline that produced it.
3. **CI enforcement.** CI pipelines SHOULD reject publication of agent-generated narrative content (Tier 3 or Tier 4) that lacks a human `reviewed_by` entry. See [Article VI](article-VI-tooling-and-infrastructure.md) for CI requirements.
4. **Accuracy audit.** Teams SHOULD review agent-generated documentation quarterly for accuracy drift, terminology consistency, and alignment with current system behavior.
5. **Non-compliance procedure.** Documents found to violate review gates SHALL be reverted to `draft` status and flagged for human review before republication.

### § 3.4 Autonomous Agent Publication of Verified Content

**Exception:** For Tier 1 (Executable/Verified) and Tier 2 (Generated/Derived) documents produced by human-approved CI pipelines, agents MAY publish without per-document human review, provided:

1. The pipeline itself has been reviewed and approved by a human Owner or Approver;
2. All pipeline outputs are logged in an audit trail with timestamps, input sources, and the generating agent identity;
3. Human review gates apply to the pipeline *configuration*, not to each individual output; and
4. A human Owner remains accountable for the pipeline's outputs and may revoke autonomous publication at any time.

This exception recognizes that requiring per-document human review of machine-verified artifacts (e.g., auto-generated API references, schema docs, CI-validated changelogs) creates friction without proportional quality benefit when the pipeline itself is trusted.

### § 3.5 Agent Identity & Audit Trail

Agents must be identified as distinct actors in all audit trails via `generated_by` or `co-authored-by` metadata. Agent contributions shall be distinguishable from human contributions in version history, with records retained per [Article III](article-III-lifecycle-governance.md).

---

## Section 4. Ownership & Stewardship

### § 4.1 Human Ownership Mandate

Every document — whether human-authored, agent-generated, or collaboratively produced — shall have a named human Owner in its metadata. A document without a current Owner is non-compliant and shall be flagged for remediation.

### § 4.2 Ownership Assignment

Ownership aligns with domain expertise: the person closest to the system a document describes is the preferred Owner. Assignments shall be recorded in document metadata and discoverable via [Article VI](article-VI-tooling-and-infrastructure.md) infrastructure.

### § 4.3 Ownership Transfer

When an Owner departs, changes roles, or cannot fulfill their duties:

1. The departing Owner or their manager shall designate a successor before departure.
2. If no successor is designated, the team lead assumes interim ownership.
3. Transfers shall be recorded in change history with date and reason.
4. A **30-day grace period** is granted for the new Owner to review and accept the document.
5. Documents without an Owner beyond 30 days shall be escalated and marked with a stewardship warning.

---

## Section 5. Access Classification

Documentation shall be accessible by default. Restriction is the exception, applied only where security concerns require it.

### § 5.1 Classification Tiers

| Tier | Label | Access |
|---|---|---|
| **Tier 0** | **Open** | All humans and agents |
| **Tier 1** | **Internal** | Authenticated team members and authorized agents |
| **Tier 2** | **Restricted** | Named individuals and specifically authorized agents |
| **Tier 3** | **Confidential** | Named individuals only; no agent access |

### § 5.2 Classification Principles

1. **Default Open.** Documents are Tier 0 unless the Owner demonstrates a higher tier is warranted. The burden falls on restriction, not access.
2. **Minimum Necessary Restriction.** Classify at the lowest tier that adequately protects the content.
3. **Agent Audit.** Agent access to Tier 2 documents shall be logged. Tier 3 documents are human-only.
4. **Periodic Review.** Classification levels shall be reviewed on [Article III](article-III-lifecycle-governance.md) freshness cadences. Over-classification is a defect.

### § 5.3 Consumer Rights

Both human and agent consumers have the right to: (a) **Accuracy** — documentation reflecting current system state; (b) **Currency** — timely updates within [Article III](article-III-lifecycle-governance.md) freshness thresholds; (c) **Accessibility** — content structured for their mode of consumption per [Article I](article-I-foundational-principles.md)'s Dual-Audience Primacy; and (d) **Discoverability** — the ability to find documentation through search, cross-references, and [Article II](article-II-document-types-and-taxonomy.md) taxonomy.

---

## Section 6. Small Team Provisions

### § 6.1 Role Consolidation

A single person may hold Owner, Author, and Reviewer roles across different documents. However, **no person shall be both sole Author and sole Approver of the same document.** On teams of three or fewer, peer review may be satisfied by any team member who did not author the content, including cross-team reviewers.

### § 6.2 Agent Augmentation

Small teams are encouraged to lean on agent capabilities — as Generators for first drafts, Validators for automated quality checks, and assistive Reviewers to supplement bandwidth. The human review gate (Section 3.2) remains non-negotiable regardless of team size. Agents extend capacity; they do not replace accountability.

### § 6.3 Minimum Viable Governance

Even the smallest team shall maintain: (a) a named Owner for every document; (b) human review of all content before publication; (c) agent identity metadata on all agent-generated contributions; and (d) a plan for ownership transfer should the sole Owner become unavailable.

---

*Ratified by the Article V Drafting Committee: Washington (President), Gerry, Wythe, King, Read, McClurg, Gilman.*
