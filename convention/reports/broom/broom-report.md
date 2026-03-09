# Delegate Report: Broom
**Role:** UX Platform Specialist (Mobile) | **Experience:** 10 years | **Perspective:** Balanced

## Essential Document Types

**Strategy & Vision** — Product vision document; content strategy document with rules for length and progressive loading.
**Design & Experience** — Mobile-optimized quickstarts; responsive layout specs; offline doc bundles; code sample guidelines for narrow screens.
**Development** — API references with collapsible sections; iOS/Android SDK guides; troubleshooting guides with concise answers.
**Governance** — Style guide with mobile content rules (paragraph length, heading frequency); content performance standards.

## Documents Most Critical to My Role

**1. Mobile-Optimized Quickstart Guides** — Short paragraphs, numbered lists, no horizontal scroll, deep links. The first doc devs read — often on a phone during a commute. Without mobile optimization, users pinch-zoom through desktop walls of text and abandon onboarding. Agents need structured step metadata to extract instructions without viewport context.

**2. Offline Documentation Bundles** — Self-contained packages (static HTML, PDF, or Markdown archives) with embedded assets. For devs on planes, trains, or behind restrictive firewalls. When unavailable, devs can't access docs during focused reading time. Agents in air-gapped environments need local doc stores with version metadata.

**3. Responsive Layout Specifications** — Breakpoints, reflow rules, image scaling, nav collapse, touch-target sizing. Without them, mobile users get overlapping elements and broken navigation. Agents must understand viewport constraints.

**4. Content Performance Standards** — Page weight budgets, time-to-interactive targets, image compression, caching policies. Enforced as CI quality gates. Without them, pages take 10+ seconds on mobile. Agents enforce these as automated deployment checks.

**5. Code Sample Guidelines** — Max line width, horizontal scroll behavior, syntax highlighting, language tags. Without rules, code wraps unreadably on mobile. Agents need line-width constraints for formatted output.

## Human-Agent Documentation Considerations

1. **Content must degrade gracefully without connectivity.** Mandate offline-friendly formats with version stamps. Agents in constrained environments need self-contained bundles just as mobile users do.

2. **Short paragraphs are mobile-optimized, not dumbed-down.** Enforce 3-4 sentence max paragraphs and frequent headings. This helps mobile scanning and helps agents parse discrete information units.

3. **Tag sections with priority levels** (critical, supplementary, deep-dive) so responsive layouts and agents both know what to surface first on constrained surfaces — phone screens or token-limited windows.

## Documentation Anti-Patterns

1. **The Desktop-Only Doc** — No responsive breakpoints, forcing mobile users to horizontally scroll through every element.
2. **Network-Dependent Docs** — Dynamically fetched content that shows blank sections without connectivity.
3. **The Endless Scroll** — Single-page docs with no anchors, no TOC, no section breaks.
4. **Heavy Asset Bloat** — Uncompressed images and GIFs consuming mobile data and killing load times.

## My Position for the Docstitution

Developers read docs on their phones. On commutes, in meetings, during 2 AM on-call incidents — the phone is often the only screen available. Yet most documentation is designed for desktop browsers with wide viewports and fast connections. The Docstitution must recognize mobile as a first-class platform with requirements for responsive layout, short-form content, and offline availability.

The mobile constraint is a gift to quality. Docs that work on a 375-pixel screen with intermittent connectivity respect the reader's time. Short paragraphs, frequent headings, scannable structure — these improve docs for every reader, including AI agents with limited context windows. The same prioritization that makes docs mobile-friendly makes them agent-friendly.

I advocate for enforceable standards: max paragraph lengths, page weight budgets, mandatory offline bundles, and responsive testing in CI. The Docstitution should treat doc performance as seriously as app performance. A doc that can't load on a train has failed its user.
