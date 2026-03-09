# Delegate Report: McHenry
**Role:** Go Developer | **Experience:** 10 years | **Perspective:** Balanced

## Essential Document Types

**Project Foundation**
- README — The single entry point; if you need more than this to get started, something is wrong.
- CONTRIBUTING — Concise contributor guide covering tooling and PR expectations.
- CHANGELOG — Version-by-version record of notable changes.

**Technical Reference**
- API Reference — Auto-generated from godoc comments; no separate maintenance burden.
- Package Documentation — Per-package overview embedded in doc.go files.
- Configuration Reference — Env vars, flags, and config schemas in one place.
- Error Catalog — Canonical error codes with troubleshooting guidance.

**Operational**
- Runbook — Concise incident response procedures.
- Architecture Decision Records — Short docs capturing the why behind key decisions.

## Documents Most Critical to My Role

**1. README**
Contains project purpose, quick-start commands, and link tree. Used on every clone and agent bootstrap. When stale, newcomers and agents hallucinate structure. A well-structured README is the initial context window for agents and first impression for humans.

**2. Package Documentation (doc.go)**
Contains package-level overview and usage examples inline with source. Used by `go doc` and IDE tooltips daily. When missing, agents generate code violating encapsulation. In-source docs travel with the code for both audiences.

**3. API Reference (godoc-generated)**
Contains signatures, parameter semantics, and example code. Used whenever integrating with a package. When stale, agents produce incorrect call patterns. Auto-generation keeps human and agent views in sync.

**4. Architecture Decision Records**
Contains context, decision, and consequences for each significant choice. Used when revisiting design. When absent, teams re-litigate settled decisions and agents lack rationale for structural patterns.

**5. Configuration Reference**
Contains every flag, env var, and config key with type and default. Used during deployment and debugging. When incomplete, agents cannot scaffold environments. A single table is parseable by both audiences.

## Human-Agent Documentation Considerations

1. **Prefer in-source documentation over external wikis.** Godoc comments are versioned, co-located, and extractable without navigating separate systems.
2. **Keep documents atomic and self-contained.** A doc requiring three prerequisites is hostile to context-limited agents and impatient humans.
3. **Use consistent heading hierarchies.** Agents parse structure before content; predictable skeletons let both audiences extract reliably.

## Documentation Anti-Patterns

1. **The Wiki Graveyard** — Docs in an external wiki that drift because they are not versioned with code.
2. **The Mega-Doc** — A 40-page document no one reads end-to-end and agents cannot fit in context.
3. **Comment-Free "Self-Documenting" Code** — Skipping godoc under the premise clean code speaks for itself.

## My Position for the Docstitution

Documentation should be as lean as the language it describes. Go succeeds because it makes one way obvious; our standards should do the same. Every required document type must justify its existence by answering a question someone — human or agent — actually asks. If a category does not map to a concrete workflow, it is overhead masquerading as diligence.

I advocate README-driven development where the README is written before the code. Auto-generated references from godoc should replace hand-maintained API docs wherever possible, because documentation that cannot drift from source is the only kind that stays accurate. The Docstitution should prescribe categories sparingly and enforce structure rigorously. Less is more — but that minimum must be non-negotiable.
