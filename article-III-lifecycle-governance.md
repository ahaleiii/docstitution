<!--
---
title: "Article III: Lifecycle Governance"
document_type: governance
status: Draft
owner: Article III Drafting Committee
reviewers:
  - Madison (Documentation Architect)
  - Ellsworth (Scrum Master)
  - Few (SRE)
  - Wythe (Compliance Architect)
  - Paterson (Project Manager)
  - Livingston (SysAdmin)
review_cadence: quarterly
freshness_threshold_days: 90
last_reviewed: null
created: 2025-07-17
version: 0.1.0
cross_references:
  - article-I-foundational-principles.md
  - article-II-document-types-taxonomy.md
  - article-V-roles-responsibilities.md
---
-->

# Article III: Lifecycle Governance

_When and how documents are created, reviewed, updated, deprecated, and archived across the product and software development lifecycle._

---

## Section 1. Document Lifecycle Stages

**§1.1** Every document governed by this Docstitution SHALL exist in exactly one lifecycle stage:

| Stage | Description |
|---|---|
| **Draft** | Under initial composition. Not yet authoritative. |
| **Active** | Reviewed, approved, and the current source of truth. |
| **Under Review** | Flagged for reassessment — by staleness threshold, incident, or dependency change. |
| **Deprecated** | No longer current. A successor or removal notice MUST be linked. |
| **Archived** | Removed from active discovery but preserved in version control for audit. |

**§1.2** Stage transitions SHALL be recorded in version history with the actor's identity (human or agent) and a rationale, per Article V.

**§1.3** A **Draft** document SHALL NOT be cited as authoritative.

---

## Section 2. Creation Triggers & Obligations

**§2.1** The following events SHALL trigger creation of corresponding documentation. These obligations apply regardless of team size; Section 6 provides accommodations for scope, not exemption.

| Trigger Event | Required Document(s) | Tier (Article II) |
|---|---|---|
| New service deployed to production | Runbook, service catalog entry | Authored/Maintained |
| New public or internal API | API specification (OpenAPI or equivalent) | Executable/Verified |
| Significant architectural decision | Architecture Decision Record (ADR) | Authored/Maintained |
| New user-facing feature | User documentation or release note | Authored/Maintained |
| Production incident (Sev-1 or Sev-2) | Post-mortem / incident review | Authored/Maintained |
| New build or deployment pipeline | Pipeline documentation | Generated/Derived |
| Schema or data model change | Updated schema documentation | Generated/Derived |

**§2.2** Generated/Derived documents SHALL be produced by automated pipelines where feasible. Agents generate factual and structural content; humans author intent and rationale. All agent-generated content requires human review before publication.

**§2.3** Documentation MAY be authored concurrently with development but SHALL reach **Active** status before the work item is considered complete (see Section 5).

---

## Section 3. Review & Maintenance Cadences

**§3.1 Review Frequency by Tier.** Documents SHALL be reviewed per their Article II classification:

| Document Tier (Article II) | Review Cadence | Freshness Threshold |
|---|---|---|
| **Executable / Verified** | Continuous (CI-validated) | Validated on every build |
| **Generated / Derived** | Regenerated on source change | Stale if source changed since last generation |
| **Authored / Maintained** | Quarterly | 90 days without review |
| **Ephemeral / Ceremonial** | Per sprint or cadence | End of sprint/cycle |

**§3.2 Freshness Enforcement.** A document exceeding its freshness threshold SHALL be automatically transitioned to **Under Review**. Tooling SHOULD surface staleness warnings to the owner. A document remaining **Under Review** for more than 30 days beyond its threshold SHALL be escalated per Article V.

**§3.3 Staleness Is a Defect.** Per Article I's principle that a stale document is worse than a missing one, a document exceeding twice its freshness threshold SHALL be flagged for deprecation review.

**§3.4 Triggered Reviews.** Beyond scheduled cadence, a document SHALL enter **Under Review** when:

- A production incident implicates the documented system or process.
- A dependency documented within it undergoes a major version change.
- The document's owner transfers ownership (per Article V).
- An agent or human consumer reports a factual inaccuracy.

---

## Section 4. Deprecation & Archival

**§4.1 Deprecation Criteria.** A document SHALL be deprecated when:

- Its subject matter has been superseded by a new system, process, or document.
- The system or service it describes has been decommissioned.
- It has failed two consecutive review cycles without an owner willing to maintain it.

**§4.2 Deprecation Procedure.**

1. The document owner (or successor per Article V) SHALL propose deprecation with written rationale.
2. A deprecation notice SHALL be added, including: date, reason, and link to any successor document.
3. The document SHALL remain **Deprecated** for a minimum of 30 days before archival.

**§4.3 Archival Procedure.**

1. After the deprecation waiting period, the document MAY transition to **Archived**.
2. Archived documents SHALL remain in version control, retrievable for audit and institutional memory.
3. Archived documents SHALL be excluded from active search indexes but available via explicit archive queries.
4. Regulated documents SHALL observe mandated retention periods before any deletion.

**§4.4 No Silent Deletion.** No document that has reached **Active** status SHALL be deleted without passing through Deprecation and Archival. Version history SHALL NOT be rewritten or purged except as required by legal obligation.

---

## Section 5. Definition of Done Integration

**§5.1** Documentation is a mandatory component of "done." No work item SHALL be considered complete unless its documentation obligations under Section 2 have been satisfied.

**§5.2 Tiered Process Weight.** Documentation effort SHALL be proportional to the document's tier:

| Document Tier | Definition of Done Requirement |
|---|---|
| **Executable / Verified** | Spec passes CI validation; no manual step required beyond authoring |
| **Generated / Derived** | Pipeline regenerates successfully; human spot-check on material changes |
| **Authored / Maintained** | Document reviewed by at least one peer; merged via standard review process |
| **Ephemeral / Ceremonial** | Document exists and is accessible; no formal review gate |

**§5.3** Scrum teams SHALL include documentation status in sprint review. Work items shipping code without satisfying documentation obligations SHALL be tracked as documentation debt in the backlog.

**§5.4 Version History Requirements.** Every update to an **Active** document SHALL include a change rationale — a brief statement explaining _why_ the change was made, not merely _what_ changed. For Authored/Maintained documents, this rationale SHALL be recorded in the commit message or an associated changelog entry.

---

## Section 6. Small Team Provisions

**§6.1** Teams of five or fewer members MAY adopt the following accommodations without formal waiver:

- **Combined roles.** A single person MAY serve as both author and reviewer, provided they document this dual role and seek external review quarterly.
- **Simplified cadence.** Authored/Maintained documents MAY use a semi-annual review cadence (180-day freshness threshold) instead of quarterly, provided no compliance or regulatory requirement demands otherwise.
- **Lightweight creation.** Creation triggers in Section 2 MAY be satisfied with abbreviated documents (e.g., a README section rather than a standalone runbook) provided the required information is present and discoverable.

**§6.2** Small team accommodations do NOT exempt teams from creation triggers (Section 2), deprecation procedures (Section 4), or Definition of Done obligations (Section 5). The obligations remain; only the ceremony is reduced.

**§6.3** When a small team grows beyond five members, it SHALL adopt standard cadences within one review cycle of crossing the threshold.

---

## Self-Governance Declaration

This Article practices what it preaches.

- **Owner:** Article III Drafting Committee (Madison, Ellsworth, Few, Wythe, Paterson, Livingston)
- **Review Cadence:** Quarterly
- **Freshness Threshold:** 90 days
- **Current Status:** Draft
- **Tier:** Authored/Maintained

Upon ratification, ownership SHALL transfer to the Docstitution Governance Body defined in Article V.
