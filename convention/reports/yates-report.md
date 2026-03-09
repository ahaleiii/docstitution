# Delegate Report: Yates
**Role:** QA Tester | **Experience:** 12 years | **Perspective:** Human Sympathizer

## Essential Document Types

**Manual & Exploratory Testing Docs**
- **Exploratory Testing Charters** — Mission statements guiding time-boxed sessions with scope, risks, and note templates.
- **Bug Report Templates** — Structured formats capturing environment, steps, expected/actual behavior, and discovery narrative.
- **Session-Based Test Notes** — Raw observations from exploratory sessions documenting findings and uninvestigated hunches.

**User-Facing Docs**
- **UAT Scripts** — Step-by-step acceptance procedures in plain language business users can follow independently.
- **Accessibility Testing Guides** — Procedures for WCAG compliance covering screen readers, keyboard navigation, and contrast.
- **User Journey Documentation** — Actual paths users take, including unhappy paths and edge cases formal docs omit.

**Process & Standards Docs**
- **Triage and Severity Guidelines** — Definitions and examples for consistent bug classification.
- **Test Completion Criteria** — Clear "done testing" definitions preventing premature sign-off.
- **Regression Checklists** — Scenarios to verify after changes, based on historical defect patterns.

## Documents Most Critical to My Role

1. **Bug Report Templates** — Environment, steps, expected/actual results, severity, and discovery narrative. Without structure, reports become clarification ping-pong. Agents pre-populate environment data; humans tell the story that makes reports actionable.

2. **UAT Scripts** — Plain-language steps for non-technical users to verify features. Without them, UAT is unstructured and sign-off premature. Agents track completion; humans judge whether software *feels* right.

3. **Accessibility Testing Guides** — Procedures for screen readers, keyboard navigation, and contrast. Must be used every cycle, not pre-audit only. Automated tools catch ~30% of issues; the rest need human testers.

4. **Exploratory Testing Charters** — Mission, scope, time box, and risks for unscripted sessions. Agents cannot do genuine exploratory testing—they lack intuition. Charters organize human judgment effectively.

5. **User Journey Documentation** — Actual user paths including errors and workarounds. Without them, testing covers only happy paths. Agents analyze telemetry; humans walk journeys finding where experience breaks.

## Human-Agent Documentation Considerations
- **Bug reports need human narrative**: Agents auto-capture logs and screenshots, but the tester's account of what they were trying to accomplish is irreplaceable. The Docstitution must protect space for narrative.
- **Accessibility docs must center human experience**: Automated scans catch a fraction of issues. Manual evaluation with assistive technology must be prescribed.
- **The best doc test is a confused new hire**: Give docs to someone unfamiliar and watch them struggle. This validation cannot be replaced by agent review.

## Documentation Anti-Patterns
1. **Accessibility as Afterthought** — Guides created before audits only, covering automated scans, never part of regular development.
2. **Bug Reports Without Stories** — Steps listed mechanically without explaining what the tester was doing or why behavior is wrong.
3. **UAT Scripts Written by Developers** — Acceptance tests in jargon users cannot follow.
4. **"Works for Me" Documentation** — Docs tested only by their authors who know the system.
5. **Automated-Only Testing Docs** — Covering only automated suites, ignoring exploratory and accessibility work.

## My Position for the Docstitution

The ultimate test of any document is whether a human can use it without help. Hand your UAT script to a business user and watch. If they struggle, the document failed. The Docstitution must establish usability testing for documentation as mandatory.

The agentic era risks marginalizing the humans docs serve. Agents check existence, links, and formatting—they cannot assess whether a document makes sense to a confused user. The Docstitution must enshrine human testers as permanent participants in the doc lifecycle. Bug reports should tell stories, UAT scripts should speak plainly, accessibility guides should mandate human evaluation. Documentation serving humans first is a principle to protect.
