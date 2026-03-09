<!--
---
title: "Article VII: Amendment Process"
article: VII
document_type: governing-document
status: ratified
owner: convention-committee
audience: [humans, agents]
last_verified: 2026-03-09
version: 0.1.0
review_cadence: annual
tags: [amendment, versioning, governance, change-management]
drafted_by:
  - Washington (President/Chief Architect)
  - Madison (Documentation Architect)
  - Ellsworth (Scrum Master)
  - Paterson (Project Manager)
  - Sherman (Senior SWE)
date: 2026-03-09
applies_to: articles I–VII
principle: "Semper Reformanda — always reforming"
---
-->

# Article VII: Amendment Process

> *The Docstitution must evolve as practices mature, tools change, and teams learn — but it shall not change carelessly. Every amendment must be deliberate, evidence-based, and inclusive of those it affects.*

---

## Section 1. Amendment Proposals

**§ 1.1.** Any stakeholder — human or agent acting on behalf of a human owner — may propose an amendment to any provision of this Docstitution (Articles I–VII).

**§ 1.2.** A proposal SHALL be submitted as a pull request containing:

1. **Scope** — Which Article(s) and Section(s) are affected.
2. **Motivation** — The problem, grounded in evidence (§ 1.3).
3. **Proposed Change** — Specific text to add, modify, or remove.
4. **Impact Assessment** — Affected roles ([Article V](article-V-roles-and-responsibilities.md)), document types ([Article II](article-II-document-types-and-taxonomy.md)), and lifecycle stages ([Article III](article-III-lifecycle-governance.md)).
5. **Rollback Plan** — How to reverse the change if harmful.

**§ 1.3. Evidence Requirement.** Proposals MUST cite at least one:

- A retrospective finding identifying a documentation pain point.
- An incident review where documentation gaps contributed to harm.
- Staleness or non-compliance data from tooling ([Article VI](article-VI-tooling-and-infrastructure.md)).
- Practitioner feedback from established channels.

Theoretical improvements without demonstrated need SHALL NOT be sufficient grounds for amendment.

---

## Section 2. Review & Deliberation

**§ 2.1. Affected-Role Review.** The author MUST identify all affected roles per [Article V](article-V-roles-and-responsibilities.md) (Author, Reviewer, Owner, Human Consumer, Agent Consumer) and request review from a representative of each.

**§ 2.2. Deliberation Period.** Proposals SHALL remain open for a minimum of five (5) business days. Stakeholders may comment, object, or counter-propose; the author must address all substantive feedback. If scope changes materially, the period resets.

**§ 2.3.** Proposed amendments MUST conform to the format standards of [Article IV](article-IV-structure-and-format-standards.md).

---

## Section 3. Ratification

**§ 3.1. Approval Threshold.** An amendment is ratified when:

1. All affected-role reviewers (§ 2.1) have approved, OR the deliberation period elapsed without objection.
2. At least one document owner ([Article V](article-V-roles-and-responsibilities.md)) of the affected Article has approved.
3. No unresolved blocking objections remain.

**§ 3.2.** Upon ratification, the amendment is merged and takes effect immediately unless the proposal specifies a deferred date.

**§ 3.3. Change Record.** Every ratified amendment MUST include a changelog entry with version increment, date, summary, and PR link, per [Article III](article-III-lifecycle-governance.md).

---

## Section 4. Versioning & History

**§ 4.1. Semantic Versioning.** The Docstitution uses `MAJOR.MINOR.PATCH`:

- **MAJOR** — Changes to foundational principles ([Article I](article-I-foundational-principles.md)), removal of an Article, or breaking changes to existing practices.
- **MINOR** — New provisions, document types ([Article II](article-II-document-types-and-taxonomy.md)), roles ([Article V](article-V-roles-and-responsibilities.md)), or tooling requirements ([Article VI](article-VI-tooling-and-infrastructure.md)) that do not alter existing obligations.
- **PATCH** — Corrections, clarifications, and formatting fixes that preserve meaning.

**§ 4.2.** The repository MUST maintain a `CHANGELOG.md` per [Article VI](article-VI-tooling-and-infrastructure.md). Each entry records version, date, affected Articles, summary, and PR link.

**§ 4.3.** Git history is the authoritative audit trail. Amendments SHALL NOT be applied via force-push or history rewrite on main.

---

## Section 5. Sunset & Reaffirmation

**§ 5.1.** Any provision may declare an explicit sunset date in its metadata. Provisions not reaffirmed before their sunset date are flagged `stale` and subject to mandatory review.

**§ 5.2.** All Articles SHALL be reviewed for relevance at least once per calendar year, coinciding with a retrospective or audit (per [Article III](article-III-lifecycle-governance.md) freshness SLOs).

**§ 5.3.** Tooling under [Article VI](article-VI-tooling-and-infrastructure.md) SHOULD automate sunset detection. A stale provision is not automatically repealed; it is flagged for expedited review under Section 2.

**§ 5.4.** Reaffirmation follows Sections 1–3, but the evidence requirement (§ 1.3) may be satisfied by a statement that the provision remains relevant.

---

## Section 6. Emergency Amendments

**§ 6.1. Scope.** The emergency process applies ONLY to:

- Security vulnerabilities in documentation practices or tooling ([Article VI](article-VI-tooling-and-infrastructure.md)).
- Critical errors causing active harm (e.g., incorrect runbook steps).
- Compliance violations requiring immediate action.

**§ 6.2. Fast-Track Procedure.** An emergency amendment MAY bypass the deliberation period (§ 2.2) but MUST:

1. Be submitted as a pull request labeled `emergency`.
2. Be approved by at least one owner of the affected Article.
3. Include evidence of urgency (incident link, vulnerability report, or compliance notice).

**§ 6.3. Retroactive Review.** Every emergency amendment MUST undergo full review per Sections 1–3 within ten (10) business days. If rejected, the amendment is reverted.

**§ 6.4.** Emergency amendments are recorded in the changelog with an `[EMERGENCY]` tag and discussed at the next retrospective.

---

*Drafted by the Article VII Committee: Washington, Madison, Ellsworth, Paterson, Sherman.*

*This Article governs amendment of the Docstitution — including itself. To change these rules, follow the process herein.*
