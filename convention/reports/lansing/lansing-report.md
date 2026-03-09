# Delegate Report: Lansing
**Role:** Accessibility Engineer | **Experience:** 13 years | **Perspective:** Human Sympathizer

## Essential Document Types

**Strategy & Vision** — Product vision document with accessibility as core value; accessibility policy statement with WCAG conformance commitments.
**Design & Experience** — Accessibility standards guide; alt text and media description standards; inclusive language guide; keyboard navigation specs.
**Development** — API references with semantic markup; code sample accessibility standards; troubleshooting guides with descriptive headings.
**Governance** — Style guide with mandatory a11y rules; accessibility audit templates; contribution guide requiring a11y checks.

## Documents Most Critical to My Role

**1. Accessibility Standards Guide** — WCAG 2.2 Level AA mapped to docs: heading hierarchy, contrast, link text, tables, media alternatives. Every author references this. When missing, docs exclude users with disabilities and agents generate inaccessible content. Agents need enforceable criteria as numbers and ordered constraints.

**2. Alt Text and Media Description Standards** — Rules for contextual alt text, captions, diagram equivalents. Without this, images are invisible to screen readers and text-based agents alike. Agents need explicit rules about what information alt text must convey.

**3. Documentation Style Guide (Accessibility Sections)** — Mandatory heading hierarchy, link text rules, table headers. Enforced by CI linters. Without this, screen reader navigation is chaotic. Agents need structural constraints as deterministic rules.

**4. Accessibility Audit Templates** — Checklists for perceivability, operability, understandability — pass/fail per criterion. Without audits, a11y debt accumulates silently. Agents run automated checks; humans test with assistive tech.

**5. Keyboard Navigation Specifications** — Tab order, focus indicators, skip-nav links. Without them, keyboard-only users are excluded. Agents validate DOM structure for tab order compliance.

## Human-Agent Documentation Considerations

1. **Agents must generate accessible content by default.** Constrain doc-generating agents with heading hierarchy, alt text, semantic HTML, and contrast requirements as non-negotiable rules.

2. **Alt text is critical for agent comprehension.** Text-based agents can't see images — alt text is the only way visual content exists for them.

3. **Semantic structure serves both assistive tech and agents.** Screen readers and agents parse by the same structural elements. No conflict between accessibility and agent-readability.

4. **Automated a11y linting must be in doc CI.** Enforce heading order, alt text presence, contrast, and table headers on every change.

## Documentation Anti-Patterns

1. **Missing Alt Text** — Images with empty or meaningless alt ("image1.png", "screenshot"). Screen readers and agents get nothing.
2. **Color as Only Channel** — Red/green for pass/fail with no text alternative. Colorblind users and text-based agents can't distinguish states.
3. **Heading Hierarchy Violations** — H1 to H4 because H4 "looks right." Broken outline for screen reader navigation.
4. **"Click Here" Links** — Link text without destination context. Screen reader users navigating by links hear meaningless phrases.
5. **Inaccessible Tables** — Data tables without headers, scope, or captions. Screen readers can't associate data with columns.

## My Position for the Docstitution

Accessibility is not a feature — it is a prerequisite. For thirteen years I have audited software, and documentation is consistently the worst offender. Teams that would never ship without WCAG testing publish docs with missing alt text, broken headings, and color-dependent information. The Docstitution must establish accessibility as a constitutional right.

The convergence of accessibility and agentic AI is structural. The same semantic markup enabling screen readers enables agents. The same alt text making images accessible to blind users makes them comprehensible to text-based agents. Accessible docs are agent-ready docs — there is no trade-off.

I will fight for mandatory standards: WCAG 2.2 Level AA for all documentation, alt text on every image, heading hierarchy enforced by CI, and periodic audits with assistive technology.
