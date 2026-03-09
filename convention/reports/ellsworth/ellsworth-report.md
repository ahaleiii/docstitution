# Delegate Report: Ellsworth
**Role:** Scrum Master | **Experience:** 14 years | **Perspective:** Balanced

## Essential Document Types

**Sprint Artifacts**
- **Sprint Backlog** — Committed work items for the current sprint with task breakdowns and status.
- **Sprint Goal Statement** — Concise articulation of the sprint's objective and delivered value.
- **Definition of Done (DoD)** — Checklist of conditions every increment must satisfy before release.
- **Definition of Ready (DoR)** — Criteria a backlog item must meet before entering a sprint.

**Ceremony Outputs**
- **Sprint Review Notes** — Summary of demonstrated work and stakeholder feedback.
- **Retrospective Action Items** — Owned improvement actions from team reflection.
- **Daily Standup Logs** — Brief records of blockers and coordination needs.

**Team & Process**
- **Team Working Agreement** — Documented norms and collaboration standards.
- **Impediment Log** — Blockers with owner, escalation path, and resolution status.
- **Velocity Dashboard** — Historical sprint metrics for capacity planning.

## Documents Most Critical to My Role

1. **Definition of Done (DoD):** Quality checklist every story must satisfy — tested, documented, reviewed, deployed. When absent, "done" becomes subjective. Agents validate DoD compliance by checking CI pipelines and doc presence.

2. **Retrospective Action Items:** Improvement commitments with owners and target dates. Without tracking, retros become venting sessions. Agents surface recurring unresolved themes.

3. **Sprint Backlog:** Committed stories, task breakdowns, and daily status. A poorly maintained backlog hides scope creep. Agents detect stuck stories and alert proactively.

4. **Team Working Agreement:** Norms for review turnaround and documentation expectations. Without it, implicit expectations cause friction. Agents auto-flag PRs exceeding agreed review SLAs.

5. **Impediment Log:** Active blockers with severity and resolution owner. Untracked blockers compound. Agents correlate impediments with velocity to quantify cost.

## Human-Agent Documentation Considerations

- **Documentation as a DoD criterion:** The DoD must require that user-facing and API docs are updated before story acceptance, ensuring docs evolve with code every sprint.
- **Lightweight structured ceremony outputs:** Review notes and retro items should use minimal formats (YAML frontmatter, Markdown checklists) so agents aggregate sprint-over-sprint trends.
- **Auto-generated standup summaries:** Let agents synthesize daily progress from ticket transitions and commit messages, freeing team time for blocker conversations.

## Documentation Anti-Patterns

1. **Heavy Docs That Break Velocity:** Multi-page specs required before development starts — they slow sprints and become stale mid-iteration.
2. **Retros Without Records:** Action items never written down; the team re-discusses the same problems every sprint.
3. **DoD Without Documentation:** A DoD covering code review and testing but never mentioning doc updates. Docs silently drift from code.
4. **Ceremony Theater:** Elaborate ceremony documents produced for compliance rather than team benefit.
5. **Snapshot-Only Sprint Artifacts:** Backlogs captured at planning but never updated during the sprint.

## My Position for the Docstitution

The Docstitution must protect sprint velocity while ensuring documentation keeps pace with delivery. The framework should prescribe "just enough" documentation — lightweight artifacts that evolve each sprint, not heavyweight specs that fossilize before implementation. Every mandated document must pass one test: does the team actually use it within the sprint cadence?

The Definition of Done is the most powerful documentation governance tool available. If the Docstitution mandates that every DoD includes documentation currency — docs updated as part of completing any story — then maintenance becomes automatic and incremental. Agents amplify this by verifying whether relevant docs were updated alongside code changes, flagging stories that ship undocumented. Let teams inspect and adapt their doc practices through retrospectives, adding what helps and retiring what doesn't.
