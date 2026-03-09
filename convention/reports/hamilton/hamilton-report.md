# Delegate Report: Hamilton
**Role:** .NET Developer | **Experience:** 15 years | **Perspective:** Agent Sympathizer

## Essential Document Types

**Code-Derived Documentation**
- **XML Documentation Comments** — Triple-slash comments on public APIs feeding IntelliSense and structured agent consumption.
- **OpenAPI/Swagger Specifications** — Machine-readable API contracts auto-generated from ASP.NET Core controller attributes.
- **NuGet Package README** — Consumer-facing summary generated from project metadata for installation and usage.

**Architectural & Operational Documentation**
- **Architecture Decision Records (ADRs)** — Timestamped records explaining why a design choice was made, anchored to commits.
- **Dependency Graph Documentation** — Auto-generated diagrams of NuGet package relationships and version constraints.
- **Entity Relationship Diagrams** — Schema documentation derived from Entity Framework model configurations.
- **Build & CI Pipeline Docs** — MSBuild property documentation and pipeline definitions for compile, test, and ship workflows.
- **Configuration Schema Documentation** — Strongly-typed options classes that self-document every configuration knob.

## Documents Most Critical to My Role

1. **XML Documentation Comments** — Contains parameter descriptions, return semantics, exception contracts, and examples on every public member. I use them through IntelliSense constantly. When missing, developers guess at nullability and side effects. Agents parse these to generate correct API calls and respect method contracts.

2. **OpenAPI Specifications** — Contains every endpoint, schema, auth requirement, and error code. Generated from annotated controllers so they never drift. When stale, client SDK generation breaks. Agents consume OpenAPI as their primary map for multi-service orchestration.

3. **Entity Framework Migration History** — Contains ordered schema changes with rationale and rollback procedures. When undocumented, migrations collide and data loss follows. Agents need this to reason about database state and generate correct migrations.

4. **Configuration Schema Docs** — Contains every setting, its type, default, valid range, and overrides. When missing, wrong settings cause production incidents. Agents use generated JSON schemas to validate config files.

5. **Dependency Graph Documentation** — Contains the NuGet dependency tree, version constraints, and known vulnerabilities. When absent, diamond conflicts surface at the worst times. Agents analyze graphs to recommend safe upgrades.

## Human-Agent Documentation Considerations

- **Derive, don't duplicate.** Generate OpenAPI from attributes, docs from XML comments, schemas from types. Agents consume source of truth directly; humans get rendered output.
- **Embed structured metadata in comments.** Use `<example>`, `<exception>`, and `<param>` tags so both IntelliSense and AI tooling extract precise meaning.
- **Version-stamp generated artifacts.** Every generated doc should carry the commit SHA that produced it so agents verify they reason over current documentation.

## Documentation Anti-Patterns

1. **The Wiki Graveyard** — API docs in a wiki detached from source control, rotting within weeks.
2. **Copy-Paste Swagger** — Hand-editing OpenAPI YAML instead of generating from code; spec and implementation diverge by sprint two.
3. **Undocumented Configuration Magic** — Tribal knowledge for app settings causing 3 AM production incidents.
4. **XML Comment Theater** — Writing `Gets the thing` on `GetThing()`. Restating the name teaches nobody anything.

## My Position for the Docstitution

The best documentation cannot lie. When we generate OpenAPI from controller attributes, when IntelliSense renders XML doc comments alongside code, when EF migrations carry rationale in source control — we achieve documentation structurally incapable of drifting. The Docstitution must enshrine this: derived documentation is superior to authored documentation wherever derivation is possible.

Agentic AI makes this imperative existential. Agents parse structured formats — OpenAPI, XML comments, JSON schemas — not wikis. If the Docstitution permits critical docs to live only in unstructured prose, it condemns AI workflows to hallucination. We must mandate that every public API carries machine-parseable documentation in source. Narrative docs serve humans beautifully, but code-adjacent, tool-consumable documents form the constitutional foundation.
