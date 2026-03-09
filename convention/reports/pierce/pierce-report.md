# Delegate Report: Pierce
**Role:** Business Analyst / Domain SME | **Experience:** 10 years | **Perspective:** Balanced

## Essential Document Types

**Domain Modeling**
- **Domain Model Documentation** — Core domain entities, relationships, and behaviors in domain language.
- **Bounded Context Map** — Boundaries where specific models apply and how contexts interact.
- **Ubiquitous Language Glossary** — Authoritative vocabulary shared between developers and domain experts per context.
- **Aggregate Documentation** — Aggregate roots, invariants, and consistency boundaries.

**Business Process**
- **Business Process Narratives** — Step-by-step domain workflows written in domain language.
- **Domain Event Catalog** — Significant events with triggers, payloads, and downstream effects.
- **Business Capability Map** — What the organization does, independent of implementation.

**Validation & Communication**
- **Context Integration Contracts** — How bounded contexts communicate, including translation layers.
- **Scenario Walkthroughs** — Concrete examples illustrating domain concepts through realistic scenarios.
- **Domain Knowledge Base** — Accumulated insights, edge cases, and historical decisions.

## Documents Most Critical to My Role

1. **Ubiquitous Language Glossary:** Every domain term with precise definition and bounded context. When missing, developers invent terms and code diverges from reality. Agents must consume this to generate code with correct domain language.

2. **Bounded Context Map:** Context boundaries, owning teams, and term translations. Without it, a monolithic model emerges. Agents need context maps to avoid violating boundaries.

3. **Domain Model Documentation:** Entities, aggregates, and invariants in domain language. When stale, code and business models diverge. Agents validate generated code against documented invariants.

4. **Domain Event Catalog:** Named events with triggers, payloads, and subscribers. Without it, event-driven systems become opaque. Agents trace event chains and detect missing handlers.

5. **Scenario Walkthroughs:** Concrete examples exercising domain rules through realistic narratives. Without them, models are unvalidatable by experts. Agents transform walkthroughs into acceptance tests.

## Human-Agent Documentation Considerations

- **Glossary-driven code generation:** Agents must reference the ubiquitous language glossary when generating code, ensuring class and method names align with domain terms rather than developer shorthand.
- **Bounded context awareness:** Agents operating across services must understand that the same concept may have different names in different contexts and translate accordingly.
- **Domain events as agent contracts:** Publish events in a structured versioned catalog that agents treat as binding contracts for generating schemas and integration tests.

## Documentation Anti-Patterns

1. **Developer-Invented Domain Language:** Engineers naming classes without consulting the glossary — the codebase becomes a dialect no domain expert recognizes.
2. **Context Boundary Violations:** Using a term from one bounded context in another without translation, causing semantic bugs invisible in review but catastrophic in production.
3. **Abstract Models Without Examples:** Only ER diagrams with no scenario walkthroughs — unvalidatable by the domain experts who matter most.
4. **Monolithic Glossaries:** One organization-wide glossary ignoring that the same word means different things in different contexts.
5. **Stale Domain Models:** Documentation from initial design never updated as the model evolves — a historical artifact, not a living reference.

## My Position for the Docstitution

Language is the most critical layer of documentation. Before governing formats or tooling, we must govern vocabulary. Every bounded context should maintain an ubiquitous language glossary co-owned by domain experts and developers. When agents generate code using wrong domain terms, they create functional software that is semantically broken.

The Docstitution must mandate bounded context documentation as a prerequisite for system design — model boundaries, integration patterns, and term translations. Without context maps, agents silently violate boundaries in ways that compile but corrupt business logic. Domain models must be validated through scenario walkthroughs, not just diagrams — domain experts validate stories, not schemas.
