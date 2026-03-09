# Delegate Report: Williamson
**Role:** Platform Architect | **Experience:** 18 years | **Perspective:** Balanced

## Essential Document Types

**Developer Onboarding**
- **Getting-Started Guides:** Zero-to-first-feature walkthroughs that a new developer can complete in under an hour.
- **README Files:** The single most important file in any repository — purpose, setup, usage, and contribution instructions.
- **Environment Setup Documentation:** Reproducible local development environment instructions including dependencies, secrets management, and common troubleshooting.

**API & SDK**
- **API Reference Documentation:** Auto-generated, always-current endpoint descriptions with request/response schemas and authentication details.
- **SDK Quick-Start Guides:** Language-specific guides that get a developer from install to first successful API call in minutes.
- **Code Samples & Cookbooks:** Copy-paste-ready examples covering the twenty most common integration patterns.

**Platform & Tooling**
- **Platform Architecture Overview:** High-level diagram and narrative explaining how internal services connect and where teams integrate.
- **Internal Tooling Documentation:** Guides for CI/CD pipelines, deployment tools, feature flags, and observability dashboards.
- **Migration Guides:** Step-by-step instructions for moving between platform versions, API versions, or deprecated tools.

**Standards & Process**
- **Coding Standards:** Language-specific conventions adopted by the organization to eliminate style debates.
- **Contribution Guidelines:** How to submit changes, what review looks like, and what the release process entails.

## Documents Most Critical to My Role

1. **README Files** — Contains project purpose, quick-start instructions, prerequisites, and links to deeper documentation. I use the README as the litmus test for developer experience — if a new engineer cannot understand the project from the README alone, the platform has failed. When missing or stale, developers waste hours asking colleagues basic questions. For agents, READMEs must include structured metadata (project type, language, dependencies) so tooling can auto-discover capabilities.

2. **Getting-Started Guides** — Step-by-step instructions from clone to first shipped feature, including environment setup, first build, first test, and first deployment. I measure platform success by time-to-first-feature. When outdated, new hires spend their first week fighting tooling instead of writing code. Agents should be able to parse these as ordered task lists with verifiable completion criteria.

3. **API Reference Documentation** — Complete, auto-generated endpoint catalog with authentication flows, rate limits, error codes, and example payloads. I rely on this to evaluate whether our platform APIs are self-service or require hand-holding. Stale API docs generate support tickets and erode trust in the platform. Agents consume these as OpenAPI or similar specs — the structured format must be the source, not a derivative.

4. **SDK Documentation** — Installation instructions, initialization patterns, method signatures, and idiomatic usage per supported language. I use these to evaluate whether our SDKs reduce or increase integration friction. Missing SDK docs mean every consumer reinvents the integration from scratch. Agents benefit from type-annotated examples they can adapt for code generation.

5. **Platform Architecture Overview** — A living document showing service boundaries, data flows, and integration points across the internal platform. I reference this when evaluating new feature requests and dependency impacts. When absent, teams build redundant services or create brittle cross-service couplings. Agents need this as a structured graph to reason about system-wide impacts of changes.

## Human-Agent Documentation Considerations

- **READMEs should contain machine-readable project metadata:** Add a structured block (YAML frontmatter or a standard section) declaring language, build system, entry points, and test commands. Humans skim the prose; agents parse the metadata to bootstrap automated workflows.
- **API docs must be generated from specs, not written by hand:** OpenAPI, AsyncAPI, or GraphQL schemas should be the source of truth. Humans get rendered docs; agents get the raw spec. Hand-written API docs are stale the moment they're published.
- **Getting-started guides need deterministic steps:** Every instruction must produce a predictable, verifiable result. Phrases like "you should see something like" must be replaced with exact expected outputs so agents can validate each step programmatically.

## Documentation Anti-Patterns

1. **The Empty README:** A repository with no README or a README containing only the project name. This is the single greatest friction point for developer onboarding and signals that the team does not value developer experience.
2. **The Outdated Getting-Started Guide:** Setup instructions referencing deprecated tools, deleted environment variables, or restructured directories. New developers follow them, fail, and lose trust in all project documentation.
3. **API Docs Written After the Fact:** Endpoint documentation written manually weeks after implementation, missing edge cases, error states, and recent changes. Generate from the spec or accept permanent drift.
4. **Platform Docs Behind a Login Wall:** Internal documentation requiring three SSO hops and a VPN to reach. If developers cannot find docs in thirty seconds, those docs do not exist.
5. **The 200-Page Architecture Document:** A comprehensive document nobody reads because it covers everything and prioritizes nothing. Break it into focused, linked pages with a clear entry point.

## My Position for the Docstitution

I judge every documentation system by a single metric: how fast can a new developer ship their first feature? In eighteen years of building platforms, I have watched brilliant architectures fail because nobody documented the on-ramp. The README is the most important file in any repository. It is the front door, the handshake, the first impression. The Docstitution must enshrine the README as a required, structured artifact with minimum content standards.

Platform documentation must be self-service by design. If a developer has to ask a colleague how to use an API, the documentation has failed. API references must be auto-generated from machine-readable specs, getting-started guides must produce deterministic results, and SDK docs must include copy-paste examples in every supported language. Documentation is not a separate deliverable — it is part of the platform itself.

I advocate for a balanced stance between human readability and agent consumption. The best documentation serves both audiences from a single source: structured specs generate human-friendly references while remaining directly consumable by AI agents and tooling. The Docstitution should mandate that platform teams publish machine-readable metadata alongside every human-readable guide, ensuring that documentation scales with automation rather than against it.
