# Delegate Report: Spaight
**Role:** Backend Developer | **Experience:** 14 years | **Perspective:** Balanced

## Essential Document Types

**API & Contract Docs**
- **OpenAPI/Swagger Specifications** — Machine-readable contracts defining every endpoint, parameter, response, and error code.
- **API Versioning Guides** — Rules for introducing, deprecating, and sunsetting API versions.
- **Data Model Documentation** — Schema definitions including relationships, constraints, and migration history.

**Service & Architecture Docs**
- **Service Catalog** — Registry of all backend services with ownership, dependencies, and health endpoints.
- **Architecture Decision Records** — Captured rationale for backend technology and design choices.
- **Integration Guides** — Instructions for consuming a service without asking the owning team.

**Operational Docs**
- **Runbooks** — Incident response procedures tied to specific services.
- **Configuration Reference** — All environment variables and feature flags per service.

## Documents Most Critical to My Role

1. **OpenAPI/Swagger Specifications** — Endpoint paths, methods, schemas, auth, and errors. Every consumer uses these to integrate correctly. Stale specs cause integration failures at deploy time. Agents auto-generate SDKs and validate requests; humans negotiate contracts.

2. **Service Dependency Maps** — Upstream/downstream relationships, SLAs, and fallbacks. Used in design reviews and incidents. Stale maps leave cascading failures undiagnosed. Agents traverse maps for blast radius; humans reason about system impact.

3. **Data Model Documentation** — Schemas, keys, indexes, and domain constraints. Referenced during development and migrations. Missing docs cause broken queries and data issues. Agents generate migrations; humans understand domain semantics.

4. **API Versioning Guides** — Strategy, deprecation timelines, and compatibility rules. Without them, consumers break silently. Agents enforce policies in CI; humans need clear migration paths.

5. **Architecture Decision Records** — Context, decision, and consequences of significant choices. Without ADRs, teams re-litigate settled debates. Agents surface relevant ADRs; humans understand the "why."

## Human-Agent Documentation Considerations
- **Contract-first development enables agent tooling**: OpenAPI specs written before code let agents generate stubs, tests, and clients automatically.
- **Machine-readable formats must stay human-reviewable**: Author specs in YAML with inline descriptions so humans review intent while agents parse structure.
- **Embed validation in CI**: Agents should verify deployed endpoints match their spec on every build, catching drift humans would miss.

## Documentation Anti-Patterns
1. **"Code Is Documentation"** — Code shows what, never why or for whom. A spec-less backend is a black box to every consumer.
2. **Snapshot Specs** — OpenAPI generated once, never updated. Consumers trust them implicitly while they rot.
3. **Tribal Knowledge APIs** — Endpoints working only because one engineer knows the undocumented parameter.

## My Position for the Docstitution

If an API is not documented in a machine-readable specification, that API does not exist. An undocumented endpoint cannot be discovered, validated, or safely consumed. The Docstitution must mandate OpenAPI specifications for every service endpoint, authored contract-first, versioned with code, and validated in CI.

Contract-first development bridges human intent and agent capability. Agents generate client code, run compliance checks, and detect drift. Humans review specs to negotiate contracts and onboard teammates. The Docstitution should require every service to publish a machine-readable spec, a human-readable integration guide, and a versioning policy—the minimum viable documentation for any backend service.
