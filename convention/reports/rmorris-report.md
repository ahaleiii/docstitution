# Delegate Report: RMorris
**Role:** Operations Lead | **Experience:** 25 years | **Perspective:** Balanced

## Essential Document Types

**Operational Runbooks:** Step-by-step procedures for routine and emergency operations both humans and agents can execute.
**Incident Post-Mortems:** Structured after-action documents capturing timeline, root cause, and corrective actions.
**Change Management Records:** What changed, who approved it, and how to roll it back.
**Escalation Procedures:** Chains of responsibility defining who gets paged, when, and with what authority.
**On-Call Handoff Docs:** Living documents transferring operational context between shifts.
**Service Dependency Maps:** Visual and machine-readable maps of service interdependencies.

## Documents Most Critical to My Role

**1. Executable Runbooks**
Numbered steps with preconditions, decision branches, and rollback procedures. Executed during incidents by on-call engineers and agents. A stale runbook at 3 AM is worse than none — false confidence wastes minutes. Must be agent-parseable into discrete steps while readable by a sleep-deprived human.

**2. Incident Post-Mortem Documents**
Timeline, root cause, impact metrics, action items with owners. Without them, organizations repeat failures and agents cannot learn from undocumented incidents. Structured fields enable agent pattern-matching; blameless language keeps humans honest.

**3. Change Management Documentation**
Change description, risk assessment, rollback plan, approval chain. Undocumented changes are the top incident cause in my 25 years. Agents auto-populate from CI/CD; human risk judgment must remain auditable.

**4. Escalation Procedure Docs**
Tiered paths with contacts and response expectations. Wrong targets mean lost minutes during outages. Agents need machine-readable contact trees; humans need scannable formats under stress.

**5. Service Dependency Maps**
Directed graphs with health endpoints, SLAs, and failure modes. Incorrect maps cause misdiagnosed incidents. Must exist in visual format for humans and structured data for agent traversal.

## Human-Agent Documentation Considerations

- Runbooks need dual-layer format: machine-parseable steps agents execute, plus human annotations explaining the "why" for judgment calls.
- Post-mortems must be queryable for agent pattern-matching while preserving narrative sections for human context.
- Change docs should support agent pre-flight validation — confirming rollback plans exist before changes proceed.

## Documentation Anti-Patterns

1. **The Prose Runbook:** Flowing paragraphs instead of numbered conditional steps — guaranteed to fail at 3 AM.
2. **The Optimistic Runbook:** Only the happy path, no failure branches or alternatives.
3. **The Postmortem Graveyard:** Filed and never referenced — every incident a surprise again.
4. **The Tribal Knowledge Excuse:** "Just ask Dave" as documentation strategy.

## My Position for the Docstitution

Documentation is an operational control, not a writing exercise. Every runbook and change record exists to prevent or mitigate failure. The Docstitution must enshrine this: operational docs are tested infrastructure. If a runbook has not been executed in a drill, it is fiction.

Agentic AI makes this more urgent. Agents do exactly what the document says — no intuition, no "I know what they meant." I welcome agents as the ultimate doc quality test. If an agent cannot execute your runbook, neither can a junior engineer at 3 AM.

The Docstitution should mandate structured executable formats, require testing through drills and agent execution, and establish freshness requirements. Documentation debt is operational risk.
