# Delegate Report: Paterson
**Role:** Project Manager | **Experience:** 20 years | **Perspective:** Balanced

## Essential Document Types

**Planning & Scheduling**
- **Project Charter** — Authorizes the project, defines scope, and names accountable parties.
- **Project Plan / Schedule** — Breakdown of tasks, milestones, dependencies, and timelines.
- **Resource Allocation Matrix** — Maps people and capacity to workstreams.

**Tracking & Reporting**
- **Status Reports** — Cadence snapshots of progress, blockers, risks, and milestones.
- **Risk Register** — Living log of risks with probability, impact, mitigations, and owners.
- **Decision Log** — Records decisions, rationale, and stakeholders involved.
- **Issue Log** — Active impediments with severity, owner, and resolution timeline.

**Communication & Governance**
- **Meeting Minutes** — Structured records of discussions, decisions, and action items.
- **RACI Matrix** — Clarifies accountability for each deliverable.
- **Change Request Log** — Scope changes with impact assessment and approval status.

## Documents Most Critical to My Role

1. **Status Reports:** Progress against milestones, burn-down metrics, blockers, and next-period plan. When missing, executives assume and problems fester. Agents can auto-generate drafts by aggregating ticket movement and CI/CD data.

2. **Risk Register:** Risk descriptions, likelihood/impact scores, mitigations, and trigger conditions. Without it, risks become surprises. Agents can monitor velocity drops and dependency failures to auto-flag emerging risks.

3. **Project Plan / Schedule:** Work breakdown, dependencies, assignments, and dates. A stale plan creates false confidence. Agents detect schedule drift by comparing planned versus actual completion rates.

4. **Meeting Minutes:** Attendees, decisions, and action items with owners and deadlines. Without them, decisions are re-litigated endlessly. Agents parse structured minutes to auto-create tickets and send reminders.

5. **Decision Log:** Decision statements with context, options evaluated, and rationale. Missing logs force teams to re-argue settled matters. Agents cross-reference decisions against current state to flag changed assumptions.

## Human-Agent Documentation Considerations

- **Templated status reports:** Consistent templates with machine-readable sections (metrics, risks, actions) let agents aggregate cross-project dashboards while humans scan quickly.
- **Quantified risk triggers:** Define risks with measurable conditions (e.g., "velocity below 20 for two sprints") so agents autonomously monitor and escalate.
- **Action items as tracked entities:** Tag action items in minutes with structured metadata — owner, deadline, status — so agents extract and track them without manual follow-up.

## Documentation Anti-Patterns

1. **Status Reports That Lie Green:** Reports showing "on track" by default because no one updates honestly — negative value masking real health.
2. **Orphaned Meeting Minutes:** Minutes taken but action items never tracked. The ceremony happens; accountability never closes.
3. **Risk Registers Created Once:** Populated at kickoff and never revisited. Becomes a checkbox artifact.
4. **Documentation as Overhead:** Treating project docs as bureaucratic waste produces tribal knowledge that collapses when people leave.

## My Position for the Docstitution

If a document doesn't help ship faster or safer, eliminate it. Twenty years has taught me documentation rot is more dangerous than documentation gaps. A maintained template-based status report outweighs a beautifully crafted narrative no one updates. The governing framework must prescribe maintenance cadences — not just creation — and define consequences for staleness.

I advocate standardized templates across project management documents. Templates reduce author overhead, ensure consumer consistency, and make docs parseable by agents. When status reports follow a known schema, agents aggregate portfolio dashboards in real time. The Docstitution should mandate templates with both human-readable narrative and machine-parseable metadata. Every governed document needs an owner, a freshness SLA, and a defined consequence for decay.
