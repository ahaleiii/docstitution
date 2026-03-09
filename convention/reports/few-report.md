# Delegate Report: Few
**Role:** Site Reliability Engineer | **Experience:** 12 years | **Perspective:** Balanced

## Essential Document Types

**SLO Definition Documents:** Formal specifications of service level objectives with indicators, targets, and error budget policies.
**Monitoring Runbooks:** Alert-specific response procedures linking each alert to diagnostic steps and remediation.
**Toil Documentation:** Inventories of repetitive manual work with automation priority and elimination timelines.
**Error Budget Policy Docs:** Governance defining consequences when error budgets are exhausted.
**Observability Architecture Docs:** What is instrumented, where telemetry flows, and what dashboards exist.
**Incident Response Playbooks:** Severity-tiered procedures defining roles and resolution workflows.

## Documents Most Critical to My Role

**1. SLO Definition Documents**
SLIs, targets, measurement methodology, and error budget calculations. Referenced continuously for reliability-vs-feature tradeoffs. Without current SLOs, teams fly blind. Must be machine-readable for agents to calculate burn rates while clear enough for product managers.

**2. Monitoring Runbooks**
Alert name, severity, root causes, diagnostic commands, remediation steps. The first thing read when an alert fires. Stale runbooks pointing to renamed services waste critical minutes. Need structured headers agents parse for triage with human-readable sections for judgment.

**3. Toil Tracking Documentation**
Manual tasks with frequency, time cost, and automation feasibility. Without it, teams normalize toil until it consumes all engineering time. Agents detect patterns from ticketing systems; humans prioritize what to automate.

**4. Error Budget Policy Documents**
Consequences for exhaustion: freezes, reliability sprints, exceptions. Without enforcement, SLOs become aspirational suggestions. Agents auto-invoke when thresholds are crossed; humans handle exceptions.

**5. Observability Architecture Documentation**
Instrumentation coverage, telemetry pipelines, dashboard inventory, alert routing. Undocumented observability means blind spots and silent failures. Agents need service-to-monitoring maps; humans need holistic views.

## Human-Agent Documentation Considerations

- Docs should have SLOs: freshness targets, accuracy audits, staleness measured as an SLI. We monitor service uptime; we should monitor doc freshness.
- Monitoring runbooks should include machine-executable diagnostics so agents triage before a human opens their laptop.
- Toil docs should be auto-populated by agents analyzing ticket patterns, then reviewed by humans too busy doing toil to document it.

## Documentation Anti-Patterns

1. **The Unmonitored Monitor:** Monitoring runbooks never reviewed for accuracy.
2. **The Aspirational SLO:** Objectives without error budget policies — theoretical numbers with zero consequences.
3. **The Dashboard Graveyard:** Dashboards nobody can explain, linked to no services or decisions.
4. **The Immortal Document:** No freshness metadata, no owner. Looks authoritative; describes a system that no longer exists.

## My Position for the Docstitution

Documentation is a service, and like all services, it needs SLOs. We would never run production without monitoring availability, yet we run doc systems with zero observability into freshness or accuracy. The Docstitution must require every document class to carry freshness targets and audit schedules, measured like any SLI.

Monitoring docs are the most neglected category. Teams have dashboards and alerts but almost none document why alerts exist or how to respond. The Docstitution must elevate monitoring runbooks to first-class status, requiring every production alert to have a documented response.

Staleness is the silent reliability killer. I have seen outages extended by hours from runbooks written for architectures migrated long ago. The Docstitution should mandate freshness tracking with automated decay warnings. If we page engineers for failing health checks, we can page doc owners for stale runbooks.
