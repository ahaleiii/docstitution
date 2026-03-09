# Delegate Report: Franklin
**Role:** Senior Technical Advisor | **Experience:** 35 years | **Perspective:** Human Sympathizer

## Essential Document Types

**Onboarding & Learning**
- **Getting Started Guide** — The first document a new team member reads; it should get them to "Hello World" in under an hour.
- **Glossary of Terms** — Plain-language definitions for every term the team uses, because jargon is a wall disguised as a shortcut.
- **Conceptual Overview** — Explains *what* the system does and *why* it exists before anyone asks *how*.
- **Onboarding Curriculum** — A sequenced learning path with milestones, not a dump of links.

**Narrative & Explanatory**
- **Architecture Narrative** — A human-readable story of the system's evolution: where it started, why it changed, and where it's headed.
- **Design Rationale Documents** — Explains the reasoning behind choices in language a junior engineer can follow.
- **Troubleshooting Guides** — Symptom-first documents that walk through diagnosis like a conversation.
- **FAQ & Tribal Knowledge Capture** — Answers the questions people actually ask, harvested from Slack and standups.

**Operational & Reference**
- **API Reference Documentation** — Complete, accurate, with examples for every endpoint.
- **Runbooks** — Written for the person holding the pager at 2 AM, not for the person who built the system.
- **Release Notes** — Written for users, not developers; explains impact, not implementation.
- **Style Guide for Documentation** — How the team writes, because consistency is kindness.

## Documents Most Critical to My Role

1. **Getting Started Guide** — Contains the shortest possible path from zero to a working development environment. I use it to evaluate how welcoming a team is to newcomers. When it's missing, onboarding takes weeks instead of days, and good people quietly disengage. For agents, this guide needs explicit, ordered steps with no ambiguity — agents can't "ask around" when something's unclear.

2. **Conceptual Overview** — Paints the big picture: what the product does, who it serves, and why it matters. I rely on it to orient anyone — executive, contractor, or intern — in ten minutes. Without it, people write code that solves the wrong problem. Agents need this document to establish context before generating anything; without understanding *why*, their output is technically correct but strategically useless.

3. **Glossary of Terms** — Defines every acronym, domain term, and internal shorthand in plain language. I consult it to keep my own writing honest. When missing, the same word means different things to different teams. Agents are especially vulnerable to term ambiguity — a glossary is the single cheapest investment that yields the largest agent accuracy improvement.

4. **Architecture Narrative** — Tells the story of how the system became what it is, including the dead ends and lessons learned. I use it to mentor mid-career engineers who need to understand not just the code but the context. Stale narratives leave teams repeating old mistakes. Agents benefit from narrative context when evaluating whether a proposed change aligns with the system's trajectory.

5. **Style Guide for Documentation** — Establishes voice, tone, formatting, and terminology standards. I use it to review contributions and maintain consistency. Without it, documentation reads like it was written by thirty different people — because it was. Agents should consume the style guide as a constraint to produce documentation that sounds like the team, not like a generic template.

## Human-Agent Documentation Considerations

- **Write for the newest human on the team, and agents will also benefit.** Documents written at a level a thoughtful junior can follow contain the explicit context that agents need. Assume nothing; spell out what experts consider obvious.
- **Preserve narrative alongside structured data.** Agents can parse structured content efficiently, but humans learn through stories. Include both: a structured summary for machine consumption and a narrative explanation for human understanding, in every significant document.
- **Use examples relentlessly.** Every concept, API call, and configuration option should include at least one concrete example. Humans learn by pattern; agents generate by pattern. Examples serve both audiences better than abstract descriptions ever will.

## Documentation Anti-Patterns

1. **The Jargon Fortress** — Documents saturated with acronyms and insider terminology that signal expertise but communicate nothing. If a competent engineer from outside the team cannot understand it, it has failed. Write for the reader, not the writer.
2. **The Link Farm** — An onboarding page that is nothing but fifty links to other documents with no narrative, sequencing, or guidance. This is not documentation; it is an abdication of responsibility. New team members need a path, not a pile.
3. **The Write-Once Monument** — Documentation created during a project kickoff, never updated, and slowly diverging from reality until it becomes actively harmful. Living systems require living documents, or they require no documents at all.
4. **The Expert-Only Artifact** — Documents that can only be understood by the person who wrote them. This is not a knowledge asset; it is a personal notebook that happens to be public. Documentation must transfer knowledge, not merely record it.
5. **The Missing "Why"** — Documents that explain *what* to do and *how* to do it but never explain *why*. Without rationale, humans cannot adapt instructions to new situations, and agents cannot assess whether the instructions still apply.

## My Position for the Docstitution

I have spent thirty-five years watching brilliant systems fail because nobody could explain them to the next person who needed to understand. I have mentored hundreds of engineers, and the single greatest predictor of their success was not the quality of the code they inherited — it was the quality of the documentation that accompanied it. The Docstitution must place readability and narrative clarity at the very top of its values. A document that is technically complete but incomprehensible is worse than no document at all, because it creates the illusion that knowledge has been captured.

I hear the enthusiasm for AI agents, and I share it, cautiously. But I worry that in our rush to make documents machine-readable, we will strip away the narrative, the context, the *humanity* that makes documentation genuinely useful. An agent can parse a schema. It cannot mentor a junior engineer through their first architecture review. The Docstitution must insist that every document tells a story — who is this for, why does it exist, and what should you understand after reading it. Structure and machine-readability are important, but they are the skeleton, not the soul.

If we get this right, we build documentation that serves everyone: the new hire on day one, the senior architect making a hard call, and the AI agent generating code at midnight. But we will only get it right if we start from the human and work outward, never the reverse. That is my position, and I will defend it with every ounce of pragmatic optimism I have left.
