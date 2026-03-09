<!--
---
document_type: governing-document
title: The Docstitution
status: ratified
owner: convention-committee
audience: [humans, agents]
last_verified: 2025-07-25
version: 1.0.0
review_cadence: annual
tags: [docstitution, preamble, governance, documentation-standards]
description: >
  The governing framework for software documentation — establishing principles,
  taxonomy, lifecycle, structure, roles, tooling, and amendment processes for
  documentation that serves both human team members and AI agents.
articles:
  - id: preamble
    title: Preamble
    path: README.md#preamble
  - id: article-i
    title: "Article I: Foundational Principles"
    path: article-I-foundational-principles.md
  - id: article-ii
    title: "Article II: Document Types & Taxonomy"
    path: article-II-document-types-and-taxonomy.md
  - id: article-iii
    title: "Article III: Lifecycle Governance"
    path: article-III-lifecycle-governance.md
  - id: article-iv
    title: "Article IV: Structure & Format Standards"
    path: article-IV-structure-and-format-standards.md
  - id: article-v
    title: "Article V: Roles & Responsibilities"
    path: article-V-roles-and-responsibilities.md
  - id: article-vi
    title: "Article VI: Tooling & Infrastructure"
    path: article-VI-tooling-and-infrastructure.md
  - id: article-vii
    title: "Article VII: Amendment Process"
    path: article-VII-amendment-process.md
---
-->

# The Docstitution

A governing framework for software product documentation — drafted by convention, ratified by practice. The Docstitution establishes the principles, taxonomy, lifecycle governance, structural standards, roles, tooling requirements, and amendment processes that make documentation serve as reliable infrastructure for both human team members and AI agents.

---

## Preamble

We, the delegates of the Docstitution Convention — fifty-four practitioners spanning every discipline of the software craft, from architecture to operations, from frontend to compliance, from quality assurance to domain expertise — having each submitted our independent assessments of what documentation must be, do hereby establish this Docstitution as the governing framework for documentation within software product teams.

### Purpose

We establish this framework because documentation is infrastructure. It is not overhead to be minimized, nor ceremony to be endured, nor an artifact produced after the work is done. Documentation is the work. It is the primary interface through which team members — human and agent alike — discover intent, understand decisions, operate systems, and build upon what came before. Where documentation fails, knowledge becomes oral tradition, decisions are relitigated, onboarding stalls, incidents escalate, and agents operate blind.

We have witnessed the cost of neglect: the zombie document, published and never updated; the oral tradition, locked in the heads of senior engineers; the wiki graveyard, disconnected from the code it purports to describe. We draft this framework so that these failures become recognizable, preventable, and unacceptable.

### Scope

This Docstitution governs documentation for software products and systems across their full lifecycle — from inception through operation, maintenance, and eventual retirement. Its provisions address every document that a software team produces, consumes, or maintains in the course of delivering and sustaining a product. Industries and disciplines beyond software product development are outside its jurisdiction.

### Dual-Audience Principle

We recognize that documentation now serves two distinct classes of consumer: human team members who read, interpret, and act on documentation through understanding; and AI agents who parse, traverse, and execute against documentation through structure. Neither audience is secondary. A document unreadable by humans has failed its explanatory purpose. A document unparseable by agents has forfeited the leverage that modern tooling provides.

We therefore adopt the dual-layer principle: every document shall carry structured metadata and semantic organization sufficient for machine traversal, while preserving the narrative clarity, context, and rationale that only human authorship provides. Structure is the frame; narrative fills it.

### Core Philosophy

We hold these tenets to be foundational:

1. **Documentation is infrastructure, not overhead.** It is funded, maintained, monitored, and held to quality standards — as any critical system component must be.

2. **Every document declares what it is, who it is for, and when it was last verified.** Structured metadata is not optional adornment; it is the navigation system by which both humans and agents locate, evaluate, and trust a document.

3. **Structure enables, rather than burdens, documentation creators.** Templates, taxonomies, and standards exist to reduce the cognitive cost of producing documentation — not to impose bureaucratic weight. When structure becomes burden, the structure must be reformed.

4. **Freshness is a quality attribute.** A stale document is worse than a missing one, for it misleads with the authority of the written word. Every document shall carry a freshness indicator, and decay shall be actively monitored.

5. **Proximity preserves accuracy.** Documentation lives with the artifact it describes. Code-adjacent documents are versioned with code, reviewed in pull requests, and treated as first-class development artifacts.

6. **Ownership is explicit and current.** Every document has a named human steward responsible for its accuracy, currency, and eventual retirement. Orphaned documents are documentation debt.

7. **Agents participate; humans govern.** AI agents may generate, validate, and enforce documentation. They shall not be sole authors of rationale, intent, or narrative. Human review remains the gate for meaning and accuracy.

### The Convention

This Docstitution was drafted through a structured convention process. Fifty-four delegates — representing roles from junior developer to principal architect, from technical writer to security lead, from DevOps engineer to business analyst — submitted independent position reports on what documentation their discipline requires, how it should be structured, and whom it should serve.

These reports were synthesized, debated, and reconciled. Where consensus existed — and it existed broadly on the primacy of API references, the necessity of architecture decision records, the requirement of structured metadata, and the imperative of freshness — we codified. Where tensions persisted — between minimalism and comprehensiveness, between auto-generation and human authorship, between colocation and central governance — we sought principled compromise. The Articles that follow represent not unanimity, but the best judgment of the Convention as a whole.

### Anti-Hypocrisy Commitment

This Docstitution shall itself follow the principles it prescribes. It carries structured metadata. It declares its audience, its owner, and its status. It is versioned. It will be reviewed. If the framework cannot govern its own documents, it has no authority to govern others.

*Semper Reformanda* — always reforming. This is a living framework, subject to amendment through the process defined in Article VII.

---

## Table of Contents

| Article | Title | Scope |
|---|---|---|
| [Preamble](#preamble) | Preamble | Purpose, scope, philosophy, and founding principles |
| [Article I](article-I-foundational-principles.md) | Foundational Principles | Non-negotiable values underpinning all other Articles |
| [Article II](article-II-document-types-and-taxonomy.md) | Document Types & Taxonomy | Authoritative classification of all document types |
| [Article III](article-III-lifecycle-governance.md) | Lifecycle Governance | Creation, review, update, deprecation, and archival |
| [Article IV](article-IV-structure-and-format-standards.md) | Structure & Format Standards | Organization, formatting, and navigability standards |
| [Article V](article-V-roles-and-responsibilities.md) | Roles & Responsibilities | Authorship, ownership, review, and agent participation |
| [Article VI](article-VI-tooling-and-infrastructure.md) | Tooling & Infrastructure | Technical infrastructure for documentation systems |
| [Article VII](article-VII-amendment-process.md) | Amendment Process | How the Docstitution itself evolves |

---

## Signatories

**Ratified:** July 25, 2025 · **Vote:** 51-3-0 (94.4%) · **Full record:** [convention/votes/ratification-vote.md](convention/votes/ratification-vote.md)

### YEA — 51 Delegates

| Delegation | Signatories |
|---|---|
| **Leadership** | Washington, Franklin, Madison, Wythe, WSJohnson |
| **Product/Process** | Randolph, Paterson, Ellsworth, Wilson |
| **Architecture** | Dickinson, Williamson, CCPinckney |
| **Tech Leads** | Sherman, King |
| **Dev by Technology** | Hamilton, GMorris, FitzSimons, Ingersoll, McHenry, Mifflin, CPinckney, Dayton |
| **Dev by Area** | Blount, Spaight, Carroll, Baldwin |
| **QA** | Gerry, LMartin, Yates |
| **UX & Design** | Mason, Bassett, Bedford, Broom |
| **Ops & Infra** | RMorris, Few, Gorham, Langdon, Livingston, Blair |
| **Data** | Clymer, Butler, Mercer |
| **Security & Accessibility** | Read |
| **Docs/Support/Release** | Rutledge, Gilman, AMartin, Jenifer |
| **SMEs & Specialists** | Pierce, Strong, Brearly, Davie |

### NAY — 3 Delegates (Recorded Dissenters)

| Delegate | Delegation | Grounds |
|---|---|---|
| Lansing | Accessibility | — |
| Houston | Knowledge Representation | — |
| McClurg | Agent Autonomy | — |

---

## Founding Documents

- [Letter of Impetus](./letter-of-impetus.md) — The original vision that initiated the Docstitution Convention, authored by Alan Hale III on 2026-03-08.
