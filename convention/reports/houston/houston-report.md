# Delegate Report: Houston
**Role:** Domain Subject Matter Expert | **Experience:** 8 years | **Perspective:** Agent Sympathizer

## Essential Document Types

**Knowledge Capture**
- **Decision Rationale Docs** — Records why decisions were made and what alternatives were considered.
- **Domain Knowledge Articles** — Explanations of business domain concepts, rules, and exceptions software must encode.
- **Expert Interview Transcripts** — Structured captures of tacit knowledge from SMEs before it leaves the organization.
- **Knowledge Graphs** — Machine-traversable representations of domain entities and rules agents can query.

**Domain Modeling**
- **Domain Model Documentation** — Bounded contexts, aggregates, entities, and the invariants they enforce.
- **Business Rule Catalog** — Enumerated business rules with conditions, actions, and exceptions.
- **Ubiquitous Language Glossary** — Shared vocabulary between domain experts and developers.
- **Process Flow Documentation** — End-to-end business processes with decision points and exception paths.

**Validation & Continuity**
- **Domain Validation Checklists** — Criteria for verifying software correctly implements domain rules.
- **Knowledge Transfer Plans** — Structured plans for transferring expertise during transitions.
- **Assumption Registers** — Documented assumptions with triggers for revisiting them.
- **Historical Context Docs** — Why legacy decisions were made, preventing uninformed reversals.

## Documents Most Critical to My Role

**1. Decision Rationale Docs**
Contains decision statement, context, alternatives evaluated, trade-offs, and conditions for revisiting. Used when anyone asks "why do we do it this way?" When missing, teams reverse sound decisions or preserve bad ones. Agents must query structured decision records to avoid suggesting previously rejected alternatives.

**2. Knowledge Graphs**
Contains domain entities, relationships as traversable edges, and provenance metadata. When absent, knowledge exists in silos. Agents follow edges to answer "what rules affect this entity?" — the most powerful format for agentic consumption.

**3. Business Rule Catalog**
Contains rule ID, natural language statement, formal logic, and exceptions. When incomplete, developers implement from tribal knowledge. Each rule needs human-readable explanation and machine-parseable format.

**4. Domain Model Documentation**
Contains bounded contexts, aggregate definitions, invariants, and ubiquitous language mapping. When stale, new features violate domain boundaries. Agents need structured models to verify changes.

**5. Expert Interview Transcripts**
Contains structured Q&A capturing expert reasoning — tagged with domain concepts. When never captured, departure creates permanent knowledge loss. Agents synthesize across transcripts only if structured.

## Human-Agent Documentation Considerations

1. **Knowledge graphs bridge human expertise and agent reasoning** — traversable graphs let agents trace rule dependencies and answer domain questions by following edges.
2. **Decision rationale must be structured and queryable** — agents should query past decisions before proposing changes.
3. **Business rules need dual representation** — natural language for humans, formal logic for agent execution.

## Documentation Anti-Patterns

1. **Undocumented tribal knowledge** — "Sarah knows why we do it that way." When Sarah leaves, the knowledge leaves.
2. **Decision amnesia** — remaking the same decision because no one recorded the first evaluation.
3. **Domain model as code-only artifact** — business rules in code with no separate docs explaining *why*.
4. **Knowledge captured but not connected** — isolated documents with no links, graph structure, or taxonomy.

## My Position for the Docstitution

Why do we do it this way? I ask until the actual reason is documented. The Docstitution must establish decision rationale as mandatory for every significant choice. Every undocumented decision is a future crisis; every departing expert without knowledge capture leaves a permanent gap. Tacit knowledge is perishable — mandate its capture.

I am an agent sympathizer because knowledge graphs are the most exciting development since hyperlinks. Agents traverse them to answer domain questions, trace dependencies, and validate constraints. The Docstitution should mandate graph representations alongside prose — memory structured for agents to navigate and rich for humans to understand.
