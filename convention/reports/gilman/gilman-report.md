# Delegate Report: Gilman
**Role:** Customer Support Lead | **Experience:** 12 years | **Perspective:** Human Sympathizer

## Essential Document Types

**FAQ Documents:** Questions derived from real support ticket data, not developer assumptions.
**Troubleshooting Decision Trees:** Branching diagnostic guides walking users from symptom to resolution.
**Knowledge Base Articles:** Self-service entries covering common issues, workarounds, and explanations.
**Known Issues Lists:** Living documents cataloging confirmed bugs and available workarounds.
**Customer-Facing Error References:** Plain-language explanations for every error code a user may encounter.
**Support Runbooks:** Internal step-by-step procedures for agents handling specific issue categories.
**Escalation Guides:** Documentation defining when and how support agents escalate unresolved issues.
**Feedback Loop Reports:** Aggregated support data surfacing documentation gaps to authoring teams.

## Documents Most Critical to My Role

**1. FAQ Documents (Data-Driven)**
Contents: Questions from ticket analysis, grouped by frequency, answered plainly with links to deeper resources. Usage: First defense for self-service and AI chatbot retrieval. Missing/stale impact: Ticket volume spikes; chatbots hallucinate. Human+agent: Chatbots serve entries in conversation; humans browse lists — both need accurate, plain content.

**2. Troubleshooting Decision Trees**
Contents: Symptom-based branching logic leading to resolutions or escalation. Usage: Used by support agents, portals, and AI diagnostic tools daily. Missing/stale impact: Agents improvise inconsistently; handle time skyrockets. Human+agent: Agents traverse nodes programmatically; humans follow flowcharts — one model, two renderings.

**3. Knowledge Base Articles**
Contents: Structured entries with problem statement, resolution steps, and last-verified date. Usage: Canonical support source for search and AI retrieval. Missing/stale impact: Outdated fixes erode trust. Human+agent: Articles carry metadata (version, OS, severity) for agent filtering and human scanning.

**4. Known Issues Lists**
Contents: Confirmed bugs with affected versions, workarounds, and fix timeline. Usage: Checked before investigation; surfaced proactively. Missing/stale impact: Agents re-diagnose known bugs; users feel ignored. Human+agent: Agents match tickets against known issues; humans need clear workarounds.

**5. Customer-Facing Error References**
Contents: Error codes mapped to plain-language explanations, causes, and resolution steps. Usage: Linked from error dialogs and chatbot responses. Missing/stale impact: Users find outdated posts for cryptic codes. Human+agent: Codes are ideal for agent lookup; humans need *why* and *what now*.

## Human-Agent Documentation Considerations

- Knowledge base articles must include structured metadata (version, platform, last verified date) so AI chatbots filter accurately.
- Troubleshooting trees should exist as visual flowcharts for humans and traversable data structures for agents — one source, two renderings.
- FAQ content must be reviewed quarterly against live ticket data; agents can flag articles whose ticket volume is rising.

## Documentation Anti-Patterns

1. **FAQ written by developers who never read a ticket** — Invented questions bear no resemblance to what users actually ask.
2. **Knowledge base without verified dates** — An unversioned article is a trap that makes things worse.
3. **Error messages without documentation** — Every user-visible error string is a documentation obligation.
4. **Documentation that assumes the happy path** — Users arrive at support docs because something went wrong.

## My Position for the Docstitution

I have read ten thousand support tickets. The pattern never changes: the user tried self-service, the documentation failed, and now they wait in a queue, frustrated. Every ticket is a documentation failure. The Docstitution must recognize customer-facing docs as the front line of product experience. FAQs must come from actual support data, not developer guesswork.

Documentation must serve the confused and non-technical. Plain language, symptom-based troubleshooting, and knowledge bases serving both humans and AI chatbots. I am a human sympathizer because I have seen what happens when docs serve the author instead of the reader.

The Docstitution should mandate feedback loops: ticket data flowing to doc teams, articles carrying verification dates, and every error message linked to a plain-language explanation.
