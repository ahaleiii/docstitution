# Delegate Report: McClurg
**Role:** AI/ML Engineer | **Experience:** 7 years | **Perspective:** Agent Sympathizer

## Essential Document Types

**AI/ML Systems**
- **Model Card** — Standardized profile: architecture, training data, performance metrics, limitations, and ethical considerations.
- **Prompt Documentation** — Catalog of system prompts, templates, expected behaviors, edge cases, and version history.
- **Data Documentation** — Dataset provenance, schema, preprocessing steps, known biases, and quality metrics.
- **AI Ethics & Governance Doc** — Fairness, transparency, accountability, and human oversight policies.

**Agent Experience**
- **Document Schema Registry** — Machine-readable schemas defining structure, metadata, and relationships of every document type.
- **Agent Navigation Guide** — Instructions for AI agents on how to discover, traverse, and consume the documentation set.
- **Machine-Readable Summaries** — Structured abstracts with purpose, audience, freshness date, and key terms in parseable format.

**Operational**
- **Model Monitoring Runbook** — Procedures for detecting drift, evaluating degradation, and triggering retraining.
- **AI Incident Playbook** — Response procedures for hallucinations, bias incidents, and prompt injection.

## Documents Most Critical to My Role

1. **Model Card** — Contains architecture, evaluation metrics across slices, intended uses, and known limitations. Used during model selection and audit. Stale cards mean deploying models without understanding boundaries. Agents parse cards to recommend models and flag limitation violations.

2. **Document Schema Registry** — Defines structure of every document type: required fields, metadata format, validation rules. Consumed by agents to understand the doc set. Without schemas, agents resort to heuristic parsing that breaks on variations.

3. **Prompt Documentation** — Records every system prompt, template variables, failure modes, and version history. Used during prompt engineering and debugging. Undocumented prompts become irreproducible tribal knowledge. Agents use prompt docs to chain operations correctly.

4. **Agent Navigation Guide** — Explicit instructions for how agents should discover documents, resolve ambiguity, and prioritize sources. Without it, agents waste tokens on trial-and-error. This document's primary audience is non-human.

5. **Data Documentation** — Dataset lineage, transformations, sampling strategy, and quality metrics. Used during training and fairness audits. Missing data docs make model behavior unexplainable. Agents consume structured docs to validate pipeline inputs.

## Human-Agent Documentation Considerations

- **Structured metadata on every document** — YAML frontmatter with `doc-type`, `last-verified`, `audience`, `related-docs`, and `summary` so agents can index and filter without reading full content.
- **Document schemas as first-class artifacts** — A schema registry lets agents validate documents, detect staleness, and generate conformant new documents.
- **Explicit agent instructions** — Machine-readable sections describing how an agent should use each document: what questions it answers and what to consult next.

## Documentation Anti-Patterns

1. **Unstructured model docs** — Free-form prose without standardized model card sections. Unsearchable and incomparable.
2. **Prompt folklore** — Prompts living in Slack threads or code comments rather than versioned docs.
3. **Human-only navigation** — Organizing docs assuming sidebar browsing. Agents need explicit graph structure.
4. **Missing freshness indicators** — No dates or version tags. Agents cannot assess information currency without temporal metadata.

## My Position for the Docstitution

The Docstitution must recognize AI agents as a primary documentation consumer. Every document should be structured enough for agents to parse programmatically and rich enough for humans to understand contextually. The convention must mandate a document schema registry as a foundational artifact, ensuring every document type has a defined structure.

I am the most agent-forward delegate at this convention. Model cards, prompt docs, and data lineage are not niche AI-team concerns — they are documentation backbone for any product using AI. The Docstitution should require machine-readable summaries, an agent navigation guide, and freshness metadata on every document. The era of docs written solely for human eyes is over.
