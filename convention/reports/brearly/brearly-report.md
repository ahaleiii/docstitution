# Delegate Report: Brearly
**Role:** API Specialist | **Experience:** 12 years | **Perspective:** Balanced

## Essential Document Types

**API Design & Specification**
- **OpenAPI Specification** — Single source of truth for every API: endpoints, schemas, authentication, and error responses in machine-readable format.
- **API Style Guide** — Naming conventions, versioning strategy, pagination patterns, and error format standards.
- **API Versioning Policy** — Rules for when and how versions are introduced, deprecated, and sunset.

**Developer Experience**
- **Developer Portal Content** — Getting-started guides, auth walkthroughs, and tutorials enabling self-service integration.
- **SDK Documentation** — Language-specific references with installation, configuration, and idiomatic examples.
- **API Changelog** — Chronological record of breaking and non-breaking changes with migration guidance.

**Governance**
- **API Lifecycle Doc** — Stages from proposal through design review, beta, GA, deprecation, and retirement.
- **Rate Limiting & Quota Docs** — Limits per tier, response headers, and retry-after behavior.
- **API Error Catalog** — Every error code with cause and recommended resolution.

## Documents Most Critical to My Role

1. **OpenAPI Specification** — Contains every endpoint, schema, and auth requirement. Generates SDKs, tests, and docs. If stale, generated code diverges from reality. Agents consume specs directly to understand APIs and validate requests.

2. **Developer Portal Content** — Quickstarts, auth setup, and use-case walkthroughs as the first integrator touchpoint. Stale content means failed first calls and abandoned integrations. Agents use portal structure to guide developers through workflows.

3. **API Changelog** — Every addition, deprecation, and removal with migration steps. Missing changelogs force manual spec diffing. Agents parse structured changelogs to auto-generate migration guides.

4. **SDK Documentation** — Language-specific method references and usage examples. Outdated SDK docs cause version mismatches. Agents use typed signatures to generate correct integration code.

5. **API Error Catalog** — Every error code with status, cause, and resolution. Incomplete catalogs lead to generic error handling. Agents use structured catalogs to recommend specific fixes.

## Human-Agent Documentation Considerations

- **OpenAPI as canonical source** — All docs, SDKs, and tests generated from the spec. Agents consume one artifact instead of reconciling multiple sources.
- **Time-to-first-call metadata** — Portal docs with structured step counts so agents can recommend the fastest integration path.
- **Semantic versioning in frontmatter** — Changelogs with structured headers (version, date, breaking flag) enabling agents to assess upgrade risk automatically.

## Documentation Anti-Patterns

1. **Spec-last documentation** — Writing docs after implementation instead of designing the OpenAPI spec first. The spec drifts immediately.
2. **Example-free endpoints** — Schemas without concrete request/response examples. Developers and agents need copy-pasteable calls.
3. **Undocumented error states** — Returning codes that appear nowhere in documentation.
4. **Portal rot** — A portal accurate at launch but stale through three API versions.

## My Position for the Docstitution

I judge API documentation by one metric: how quickly can a developer make a successful API call? The Docstitution must enshrine OpenAPI-first design as a principle. The spec must exist before implementation, serve as the single source of truth, and generate all downstream artifacts. When the spec is the source, drift becomes structurally impossible.

The Docstitution should mandate interactive docs, a complete error catalog, and a versioning policy with deprecation timelines. For agents, OpenAPI specs are natively consumable — the human-optimal and agent-optimal formats converge in one artifact. Build on that convergence: structured specs for machines, rich examples for humans, all from one source.
