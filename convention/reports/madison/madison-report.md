# Delegate Report: Madison
**Role:** Documentation Architect / Lead Technical Writer | **Experience:** 25 years | **Perspective:** Balanced

## Essential Document Types

**Foundational & Strategic**
- **Documentation Charter** — Defines the purpose, scope, governance, and lifecycle policies for the entire documentation system.
- **Content Strategy Document** — Maps document types to audiences, purposes, and maintenance cadences.
- **Taxonomy & Information Architecture Specification** — Defines the classification system, navigation hierarchy, and naming conventions for all documentation.
- **Documentation Style Guide** — Prescribes formatting, voice, terminology, and structural conventions.

**Technical & Reference**
- **API Reference** — Complete specification of every public interface, parameter, and response type.
- **Architecture Decision Records** — Structured records capturing context, decision, status, and consequences.
- **Configuration Reference** — Exhaustive listing of every configurable parameter with defaults, constraints, and examples.
- **Data Dictionary** — Defines every entity, field, relationship, and constraint in the data model.

**Process & Lifecycle**
- **Document Lifecycle Policy** — Specifies creation, review, update, deprecation, and archival procedures for each document type.
- **Template Library** — Standardized templates for every document type with required sections and guidance.
- **Review & Approval Workflow** — Defines who reviews what, approval criteria, and escalation paths.
- **Content Audit Checklist** — Criteria and schedule for periodic documentation health assessments.

**User-Facing**
- **User Guides** — Task-oriented instructions organized by workflow, not by feature.
- **Tutorials** — Step-by-step learning exercises that build cumulative understanding.
- **Release Notes** — Structured per-release summary with sections for features, fixes, deprecations, and migration steps.
- **Troubleshooting Knowledge Base** — Symptom-indexed collection of known issues and resolutions.

## Documents Most Critical to My Role

1. **Taxonomy & Information Architecture Specification** — Contains the complete classification hierarchy, naming rules, and navigation structure for all documentation. I use it as the authoritative map when creating, placing, or reorganizing any document. When missing, documents proliferate in ad-hoc locations and users cannot find what they need. Agents must consume the taxonomy to place generated documents correctly and to resolve references between documents.

2. **Documentation Charter** — Defines what the documentation system covers, who owns it, and the policies governing its lifecycle. I enforce it when stakeholders propose undisciplined additions or resist necessary updates. Without it, documentation grows without boundaries and decays without accountability. Agents should reference the charter to determine whether a document they are asked to create falls within scope and who must approve it.

3. **Template Library** — Provides standardized structures for every document type with required sections, optional sections, and authoring guidance. I distribute templates to every contributor to ensure consistency. Without templates, every author invents their own structure, and readers must re-learn how to navigate each document. Agents should use templates as output schemas, guaranteeing that generated documents conform to organizational standards.

4. **Content Strategy Document** — Maps every document type to its audience, purpose, update frequency, and success criteria. I use it to prioritize documentation efforts and justify resource allocation. When absent, teams produce documents nobody needs while neglecting those everyone requires. Agents can use the strategy to assess which documents are highest priority for generation or update.

5. **Document Lifecycle Policy** — Prescribes creation triggers, review schedules, staleness thresholds, deprecation criteria, and archival procedures. I rely on it to keep the documentation corpus healthy. Without lifecycle management, documentation accumulates indefinitely and trust erodes. Agents should consume lifecycle metadata to flag stale documents and trigger review workflows.

## Human-Agent Documentation Considerations

- **Every document must declare its type, audience, and purpose in a structured metadata header.** This enables agents to classify, filter, and route documents programmatically while giving humans an immediate orientation before reading further.
- **Enforce a single, authoritative taxonomy with machine-readable identifiers.** Documents must be classified within a defined hierarchy using stable IDs. Agents rely on predictable paths and identifiers; humans rely on intuitive naming. Both needs are met by a well-designed taxonomy.
- **Separate document structure from presentation.** Author in structured formats (Markdown with consistent heading semantics) so that agents can parse and transform content reliably, while humans can render it in whatever medium suits them.

## Documentation Anti-Patterns

1. **The Flat Pile** — All documents dumped into a single folder or wiki space with no hierarchy, no naming convention, and no classification. Finding anything requires tribal knowledge or brute-force search. A taxonomy is not optional; it is the documentation system.
2. **The Snowflake Document** — Every document has a unique, idiosyncratic structure invented by its author. Readers waste cognitive effort figuring out where to find information. Standardized templates eliminate this tax entirely.
3. **The Zombie Document** — A document that is technically still published but has not been updated in years. It is neither accurate nor explicitly deprecated, so readers cannot assess its trustworthiness. Every document must carry a visible last-reviewed date and a lifecycle status.
4. **The Audience-of-Everyone** — A document that tries to serve executives, developers, and end users simultaneously and serves none of them well. Every document must have a single, explicitly declared primary audience.
5. **The Heading-Level Anarchy** — Documents where heading levels are used for visual styling rather than semantic hierarchy. This destroys navigation, breaks automated table-of-contents generation, and makes agent parsing unreliable. Heading levels must reflect logical document structure.

## My Position for the Docstitution

I have spent twenty-five years building documentation systems, and the lesson I return to most often is this: the architecture of your documentation matters more than any individual document within it. A well-structured system with mediocre content will improve over time because contributors know where to put things, reviewers know what to look for, and readers know where to find what they need. A poorly structured system with brilliant content will collapse under its own weight because no one can navigate it, maintain it, or trust it.

The Docstitution must establish a comprehensive taxonomy that classifies every document type by purpose, audience, and lifecycle stage. It must mandate templates that enforce structural consistency. It must require metadata headers that make every document self-describing. These are not bureaucratic luxuries — they are the minimum viable infrastructure for a documentation system that serves both humans and AI agents at scale.

I am a balanced delegate, but I will be uncompromising on structure. If a document does not know what it is, who it is for, and when it should be reviewed, it does not belong in the system. The Docstitution should be the framework that makes good documentation the path of least resistance and bad documentation structurally impossible.
