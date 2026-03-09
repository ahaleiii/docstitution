# Delegate Report: WSJohnson
**Role:** Software Architect | **Experience:** 25 years | **Perspective:** Balanced

## Essential Document Types

**Architecture & Design**
- **Architecture Decision Records (ADRs)** — Immutable records of significant design decisions with context, options considered, decision, and consequences.
- **C4 Model Diagrams** — System context, container, component, and code-level diagrams that describe the system at four levels of abstraction.
- **System Architecture Document** — Living description of the system's structure, component responsibilities, and integration patterns.
- **Technical Design Documents** — Detailed designs for specific features or subsystems, authored before implementation begins.
- **Interface & API Specifications** — Formal definitions of every public contract between components or services.

**Code-Adjacent Documentation**
- **README per Repository/Module** — Entry point document colocated with code: what it is, how to build it, how to run it, and where to find more.
- **Inline Architecture Annotations** — Structured comments or doc-blocks that link code to the ADRs and design documents that govern it.
- **Dependency & Integration Map** — Diagram and documentation of all upstream and downstream dependencies with versioning and ownership.
- **Build & Deployment Documentation** — Describes how to build, test, package, and deploy the artifact, colocated with the pipeline definition.

**Operational & Process**
- **Runbooks** — Operational procedures for monitoring, alerting, scaling, and incident response tied to specific architectural components.
- **Technical Debt Register** — Documents known debt with severity, affected components, remediation cost, and priority.
- **Migration & Upgrade Guides** — Step-by-step procedures for version upgrades, data migrations, and breaking-change adoptions.
- **Capacity & Performance Baselines** — Documents current performance characteristics and thresholds that trigger scaling or redesign.

## Documents Most Critical to My Role

1. **Architecture Decision Records (ADRs)** — Each ADR contains the status, context, decision, and consequences of a single architectural choice. I author them before implementation and reference them during reviews. When missing, teams forget *why* they made choices and reverse good decisions or repeat bad ones. Agents should consume ADRs as hard constraints: if an ADR says "we chose PostgreSQL because of X," the agent must not propose MongoDB without acknowledging the existing decision.

2. **C4 Model Diagrams** — Four layers of diagrams from system context down to code structure, authored in diagram-as-code formats like Structurizr DSL or PlantUML. I use them to communicate architecture to audiences at different levels of detail. Without them, every architecture conversation starts from scratch with ad-hoc whiteboard drawings. Agents can parse diagram-as-code sources to understand system structure and validate that proposed changes respect component boundaries.

3. **Technical Design Documents** — Authored before implementation, each contains the problem statement, proposed solution, alternatives considered, and acceptance criteria. I review them to catch design issues before code is written. When skipped, problems are discovered during code review or — worse — in production. Agents should reference active design docs to ensure generated code aligns with the approved design.

4. **README per Repository/Module** — Colocated with the code, each README covers what the module does, how to build and run it, its dependencies, and where to find deeper documentation. I maintain them as the entry point for anyone touching the code. A missing or stale README means every new developer wastes hours figuring out basics. Agents use the README as their first context source when working within a repository.

5. **Dependency & Integration Map** — Documents every external service, library, and internal module dependency with version, owner, and contract reference. I use it to assess blast radius when making changes. Without it, a change in one service breaks another because no one mapped the dependency. Agents must consult the dependency map before proposing changes that cross service boundaries.

## Human-Agent Documentation Considerations

- **Colocate documentation with the code it describes.** ADRs in the repository's `docs/decisions/` folder, READMEs at every module root, architecture diagrams authored as code in version control. Agents operate on repository context; documentation outside the repository is invisible to them. Humans benefit equally from proximity.
- **Use diagram-as-code for all architectural visualizations.** Structurizr DSL, PlantUML, Mermaid — any text-based format that lives in version control. Agents can read, diff, and update text-based diagrams. Binary image files are opaque to agents and difficult to maintain for humans.
- **Link code to decisions explicitly.** Use structured annotations or a machine-readable mapping file to connect code modules to the ADRs, design documents, and interface specs that govern them. This enables agents to load relevant architectural context automatically when modifying code.

## Documentation Anti-Patterns

1. **The Architecture Astronaut Document** — A beautifully drawn diagram that describes a theoretical system architecture that was never built. If the diagram does not match the code, it is fiction. Architecture documentation must be validated against the running system or generated from it.
2. **The Decision Graveyard** — A folder of ADRs that were written once and never referenced again. ADRs must be linked to the code they govern and consulted during reviews. An unlinked ADR is an unenforceable decision.
3. **The Wiki Exile** — Architecture documentation stored in a wiki entirely disconnected from the codebase. Developers work in their IDE and their repository; documentation that lives elsewhere is documentation that is never read. Colocate or accept obsolescence.
4. **The Diagram Without a Legend** — A diagram full of boxes and arrows where the shapes, colors, and line styles have no defined meaning. Every diagram must include a legend, and ideally use a standardized notation like C4 so that meaning is inherent.
5. **The Prose-Only Architecture** — Ten pages of text describing system architecture with no visual representation. Architecture is spatial; prose alone cannot convey component relationships, data flow, and boundaries effectively. Diagrams are not supplementary — they are primary.

## My Position for the Docstitution

I will draw a diagram before I write a paragraph, and I make no apology for it. In twenty-five years of software architecture, I have seen more miscommunication caused by walls of text than by any other single factor. The Docstitution must elevate architectural diagrams — specifically, diagram-as-code artifacts maintained in version control — to first-class document types. C4 model diagrams should be the standard visual language, and Architecture Decision Records should be the standard textual record. Together, they form the minimum viable architecture documentation that every software product requires.

Documentation must live where the code lives. The moment you move architecture documentation to a wiki, a SharePoint site, or a shared drive, you have sentenced it to irrelevance. Developers do not leave their repositories to read documentation, and agents cannot access content outside their working context. The Docstitution should mandate that ADRs, design documents, READMEs, and architecture diagrams are stored in the repository and maintained under the same version control discipline as production code. If the documentation is not in the repo, it does not exist for practical purposes.

I am a balanced delegate, and I respect that compliance, onboarding, and governance perspectives must all be represented. But I will insist on this: architecture documentation that is disconnected from the codebase is documentation that has already begun to die. The Docstitution must make colocation a governing principle, not a recommendation.
