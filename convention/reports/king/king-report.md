# Delegate Report: King
**Role:** Technical Lead | **Experience:** 15 years | **Perspective:** Balanced

## Essential Document Types

**Onboarding & Standards**
- **Onboarding Guides:** Day-by-day plans that take a new hire from laptop setup to first meaningful contribution within a week.
- **Coding Standards:** Definitive conventions for naming, formatting, error handling, and patterns — documented once, enforced everywhere.
- **Team Working Agreements:** Explicit norms for communication, meetings, code review turnaround, and escalation paths.

**Development Workflow**
- **PR Templates:** Structured pull request descriptions ensuring every change includes context, testing evidence, and rollback considerations.
- **Code Review Checklists:** Objective criteria reviewers evaluate against, reducing subjective feedback and review inconsistency.
- **Branching & Release Strategy Docs:** How branches are named, when they merge, and what the release cadence looks like.

**Architecture & Design**
- **Architecture Decision Records:** Lightweight records preventing teams from relitigating settled decisions every quarter.
- **Technical Design Documents:** Proposals for significant changes reviewed before implementation, preventing expensive mid-sprint pivots.
- **Service Ownership Registry:** A living document mapping every service to its owning team, on-call rotation, and primary contacts.

**Operational**
- **Incident Post-Mortem Templates:** Structured formats ensuring every incident produces actionable follow-ups, not just narratives.
- **Runbooks:** Step-by-step operational procedures for common tasks like deployments, rollbacks, and data migrations.
- **Definition of Done Checklists:** Explicit criteria for when a feature, story, or task is considered complete — including documentation requirements.

## Documents Most Critical to My Role

1. **Onboarding Guides** — Contains a day-by-day plan: Day 1 covers environment setup, Day 2 covers codebase orientation, Day 3 covers first small PR, and by end of week one the new hire has shipped a real feature. I use this with every new team member and update it after each onboarding cycle based on where people got stuck. When missing, I personally walk each new hire through the same steps, repeating myself for the dozenth time. Agents should be able to parse these as structured task sequences to provide interactive onboarding assistance, answering "what do I do next?" queries contextually.

2. **Coding Standards** — Defines naming conventions, error handling patterns, test coverage expectations, import ordering, and idiomatic patterns for each language in the stack. I reference these in every code review as the authoritative source, ending debates with "it's in the standards doc." When undocumented, every PR review devolves into personal preference arguments that waste hours and damage morale. Agents generating or reviewing code must consume these standards to produce output that passes review on the first attempt.

3. **PR Templates** — Structured templates requiring a description of what changed, why it changed, how it was tested, potential risks, and rollback steps. I enforce PR template usage because it forces authors to think through their changes before requesting review. Without them, PRs arrive with titles like "fix stuff" and no context, doubling review time. Agents assisting with PR creation should auto-populate template fields from commit messages, linked issues, and diff analysis.

4. **Architecture Decision Records** — Short, structured documents recording each significant technical decision with context, options considered, and rationale. I maintain these to prevent the quarterly cycle of "why don't we rewrite this in [new framework]?" conversations. When ADRs are missing, teams spend planning sessions debating decisions that were made and settled a year ago. Agents should index ADRs to provide historical context when similar decisions arise.

5. **Incident Post-Mortem Documents** — Blameless post-mortem records including timeline, root cause, impact, contributing factors, and action items with owners and due dates. I facilitate post-mortems and track action item completion. When post-mortems are skipped or poorly documented, the same incidents recur. Agents can analyze post-mortem corpora to identify systemic patterns — recurring root causes that individual post-mortems miss.

## Human-Agent Documentation Considerations

- **Coding standards must be machine-enforceable:** Every standard should map to either a linter rule or a structured specification agents can validate against. A standard that exists only as prose will be inconsistently applied by humans and invisible to agents. Pair every convention with its enforcement mechanism.
- **PR templates should be agent-assistable:** Structure template fields with clear labels and expected content types so agents can pre-fill sections from commit history, diff analysis, and linked issues. Humans review and refine; agents do the tedious assembly work.
- **Onboarding guides must declare prerequisites and verification steps:** Each step should specify what must be true before starting (prerequisites) and how to confirm success (verification). This enables agents to guide new hires interactively rather than presenting a static checklist.

## Documentation Anti-Patterns

1. **The Oral Tradition:** Critical knowledge that exists only in senior engineers' heads, transmitted verbally to new hires one at a time. When those engineers leave, the knowledge leaves with them. If you have explained it twice, it needs a document.
2. **Style Debates in Code Review:** Absence of coding standards means every pull request becomes a forum for personal preferences. This wastes engineering hours and creates inconsistent codebases. Document the standard once; argue about it once; enforce it forever.
3. **The Onboarding Gauntlet:** Expecting new hires to "figure it out" by reading code with no guided path. This conflates self-sufficiency with abandonment and extends ramp-up from days to months.
4. **Post-Mortems Without Action Items:** Incident retrospectives that produce narratives but no tracked follow-ups. Without assigned, dated action items, post-mortems are storytelling sessions. The same incident will happen again.

## My Position for the Docstitution

I am tired of explaining the same thing to every new hire. I am tired of the same code review arguments recurring because nobody wrote down the standard. I am tired of the same incidents repeating because post-mortem action items were never tracked. Fifteen years as a technical lead have made one thing clear: documentation is how a team scales beyond the knowledge of its most senior members. The Docstitution must require that teams document their standards, their onboarding paths, and their hard-won operational lessons.

Coding standards should be documented exactly once and enforced automatically. PR templates should be mandatory, not optional. Onboarding guides should be living documents updated after every new hire's experience. These are not bureaucratic overhead — they are force multipliers. A team with strong documentation onboards in days, reviews PRs in minutes, and resolves incidents without heroics. A team without them relies on tribal knowledge, burns out its senior engineers, and repeats its mistakes.

I take a balanced position on human-agent documentation. Standards and templates are natural fits for agent consumption — structured, rule-based, and enforceable. But the Docstitution must also preserve space for human judgment. Not every decision can be encoded in a template. Not every standard can be reduced to a linter rule. The goal is documentation that agents can leverage to handle the routine, freeing humans to focus on the decisions that actually require experience and context.
