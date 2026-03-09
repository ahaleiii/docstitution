<!--
---
document_type: committee-review
title: "Review Panel: Human Sympathizers & Minimalists"
status: draft
owner: review-panel-human-minimalist
audience: [convention-delegates, ratification-committee]
last_verified: 2025-07-25
tags: [review, ratification, human-sympathizer, minimalist, objections]
cross_references:
  - README.md
  - article-I-foundational-principles.md
  - article-II-document-types-and-taxonomy.md
  - article-III-lifecycle-governance.md
  - article-IV-structure-and-format-standards.md
  - article-V-roles-and-responsibilities.md
  - article-VI-tooling-and-infrastructure.md
  - article-VII-amendment-process.md
---
-->

# Review Panel: Human Sympathizers & Minimalists

*A critical review of the draft Docstitution, Articles I–VII and Preamble.*

**Panel composition:** Franklin, Gerry, Mason, Lansing, Gilman, AMartin, Yates (Human Sympathizers); Sherman, McHenry, Ellsworth (Minimalists)

**Review date:** 2025-07-25

---

## 1. Summary Verdict

| Panelist | Role | Vote | Rationale |
|---|---|---|---|
| **Franklin** | Senior Advisor (35yr) | **YES, with reservations** | The Preamble is beautifully written and the "why" is strong throughout. However, Articles IV and VI become specification-dense and lose the human reader. The framework *talks about* readability more than it *demonstrates* it. |
| **Gerry** | QA Lead (18yr) | **NO** | Human review gates exist but are not enforceable. Article V §3.2 says agents "shall not be the sole Author of narrative," but there is no mechanism to *detect or prevent* this. No audit procedure, no compliance checks, no penalties. The gates are aspirational, not operational. |
| **Mason** | UX Lead (22yr) | **YES, with reservations** | The information architecture is solid — clear hierarchy, good cross-referencing mandate (Article IV §4). But there is no entry point for someone who just wants to *use* this framework. No quickstart. No "which article do I read first?" The Table of Contents in the README is a list, not a navigation aid. |
| **Lansing** | Accessibility Engineer (13yr) | **NO** | Article IV §3.1 says "WCAG 2.2 Level AA as a minimum baseline" but provides only five specific requirements (§3.2). WCAG 2.2 AA has 50+ success criteria. The Article mandates compliance but gives authors almost no actionable guidance on how to achieve it. The Docstitution's own documents use HTML comments for metadata — screen readers will skip these entirely, making the "structural contract" invisible to assistive technology users. |
| **Gilman** | Support Lead (12yr) | **YES, with reservations** | Customer-facing documentation is mentioned only obliquely. Article II §2.1 (README) and §3.3 (Tutorials) acknowledge external audiences, but there is no dedicated treatment of end-user docs, knowledge base articles, or support-facing content. The framework is engineer-facing; it needs at least a hook for customer documentation. |
| **AMartin** | User Doc Specialist (14yr) | **NO** | Tutorials are a "Recommended" type (Article II §3.3), not a "Required Core" type. The Getting Started Guide is optional. There is no concept of learning paths, progressive skill-building, or user journeys. The framework treats documentation as reference infrastructure and neglects its pedagogical function entirely. |
| **Yates** | QA Tester (12yr) | **YES, with reservations** | The documents are internally consistent and well-structured. However, they have never been usability-tested. Several sections (Article VI §2, Article III §3) use dense table-after-table layouts that are hard to scan. The "SHALL/SHOULD/MAY" RFC-style language is precise but adds cognitive load for non-governance readers. |
| **Sherman** | Senior SWE (30yr) | **NO** | Article II §4 (metadata requirements) duplicates Article IV §1 (metadata requirements). Article I §4 (Verifiability) restates the tier hierarchy that Article II §1 defines in full. The reliability hierarchy appears three times across Articles I, II, and VI. This framework preaches against redundancy (Anti-Pattern 6.3) while practicing it. Cut the duplicates or canonicalize with single-source references. |
| **McHenry** | Go Dev (10yr) | **NO** | This framework requires, at minimum: YAML frontmatter on every file, a prose linter in CI, link checking in CI, schema validation in CI, quarterly review cadences, ownership metadata, cross-reference indexes, and a terminology registry. For a three-person team shipping a Go CLI tool, this is a documentation bureaucracy that dwarfs the product. The small team provisions (Articles II §5, III §6, V §6, VI §6) reduce scope but the *floor* is still too high. |
| **Ellsworth** | Scrum Master (14yr) | **YES, conditional** | The Definition of Done integration (Article III §5) is exactly right — documentation as part of "done" is the only way it survives sprint cadence. But the quarterly review cycle for Authored/Maintained docs (Article III §3.1) doesn't align with sprint rhythms. Make the review cadence configurable per team (with a quarterly default, not mandate) and I'll vote yes. |

**Tally: 4 YES (with reservations), 1 conditional YES, 5 NO**

**Current ratification: FAILS (50% yes, needs 80%)**

---

## 2. Critical Objections

These issues MUST be resolved before ratification. Each is tagged with the blocking panelist(s) whose vote it would flip.

### Objection 2.1 — Human Review Gates Are Unenforceable

**Raised by:** Gerry
**Severity:** Blocking
**File:** `article-V-roles-and-responsibilities.md`, Section 3 (Agent Participation & Boundaries)
**Also affects:** `article-VI-tooling-and-infrastructure.md`, Section 2

**Problem:** Article V §3.2 states that "Agent-generated content shall not be published without human review and approval." Article VI §2.3 requires documentation CI checks as "required status checks on pull requests." But nowhere does the framework specify *how* to distinguish agent-authored content from human-authored content in the review process. The `generated-by` metadata (Article V §3.3) is self-reported by the agent — there is no verification mechanism.

A determined or misconfigured agent can submit content, self-label as human-authored, and pass through every gate this framework defines. The human review requirement is a policy, not a control.

**Proposed fix:** Add to Article VI §2 a new clause requiring:
1. CI validation that any commit with agent identity markers (co-authored-by trailers, bot accounts) has at least one human-approved review.
2. A recommended practice of branch protection rules requiring human approval for documentation PRs from agent-associated accounts.
3. Periodic audit sampling (quarterly) of published documents to verify human review actually occurred — not just that the metadata *claims* it did.

**Vote flip:** Gerry → YES

---

### Objection 2.2 — Accessibility Requirements Are Hollow

**Raised by:** Lansing
**Severity:** Blocking
**File:** `article-IV-structure-and-format-standards.md`, Section 3 (Accessibility Standards)

**Problem:** Section 3.1 mandates "WCAG 2.2 Level AA as a minimum baseline." Section 3.2 then lists exactly five requirements — alt text, descriptive links, table headers, no color-only information, and semantic markup. This covers roughly 10% of the WCAG 2.2 AA success criteria. Notable omissions:

- **1.3.1 Info and Relationships** — No guidance on ensuring programmatic structure matches visual structure beyond headings.
- **1.4.3 Contrast (Minimum)** — No mention of contrast ratios for rendered documentation.
- **1.4.4 Resize Text** — No requirement that rendered docs support text resizing.
- **2.4.1 Bypass Blocks** — No requirement for skip navigation in rendered web documentation.
- **2.4.6 Headings and Labels** — Partially covered, but no enforcement mechanism.
- **3.1.1 Language of Page** — No requirement for `lang` attributes in rendered HTML.
- **3.1.2 Language of Parts** — No guidance for multilingual content or code-switching.

Additionally, the Docstitution's own frontmatter is enclosed in HTML comments (`<!-- -->`), which are invisible to screen readers and most assistive technologies. The metadata that Article IV §1.3 calls "the structural contract between the document and every system that consumes it" is structurally invisible to users who most need structural aids.

**Proposed fix:**
1. Expand Article IV §3.2 to include at least the most actionable WCAG 2.2 AA criteria relevant to documentation (contrast, text resizing, language declaration, bypass blocks).
2. Add a reference to the full WCAG 2.2 AA checklist rather than attempting to enumerate all criteria inline — "The five requirements below are the most common; teams SHALL also comply with the full WCAG 2.2 AA standard, linked here."
3. Address the HTML-comment frontmatter gap: either require tooling to expose metadata to assistive technology in rendered output, or acknowledge this limitation and specify a remediation path.
4. Add a requirement for accessibility testing tooling (axe-core, pa11y, or equivalent) in Article VI §2 as a CI check for rendered documentation.

**Vote flip:** Lansing → YES

---

### Objection 2.3 — Tutorials and Learning Paths Are Second-Class Citizens

**Raised by:** AMartin
**Severity:** Blocking
**File:** `article-II-document-types-and-taxonomy.md`, Section 3.3 (Onboarding & Learning)

**Problem:** The six Required Core document types (Article II §2) are: README, ADR Log, API Specification, Runbook, Style Guide, and Glossary. These are reference and governance documents. Not a single pedagogical document type is in the Required Core.

Tutorials, Getting Started Guides, and Troubleshooting Guides are all "Recommended" (§3.3), meaning teams can omit them without justification. The framework says "no justification is required for omission" of recommended types (§3.1). This means a fully compliant project can have zero onboarding documentation.

Article I §5 (Readability) says documents must "meet that audience where they are," but if the audience is a new team member, there may be *no document designed for them*. The README is required, but it is described as "the front door" — not a tutorial. A front door is not an onboarding experience.

**Proposed fix (minimum to flip vote):**
1. Add "Getting Started Guide" to the Required Core (Article II §2) as a seventh required type, with a small-team consolidation allowance permitting it to be a section of the README.
2. Add a single sentence to Article II §2 preamble: "The Required Core must include at least one document designed for a reader encountering the project for the first time."
3. In Article II §3.3, upgrade "Tutorials" from purely optional to "Strongly Recommended" with a trigger: "Required when the project has more than two contributors or any external consumers."

**Vote flip:** AMartin → YES

---

### Objection 2.4 — Redundancy Across Articles I, II, and VI

**Raised by:** Sherman
**Severity:** Blocking
**File:** Multiple — `article-I-foundational-principles.md` §4, `article-II-document-types-and-taxonomy.md` §1, `article-VI-tooling-and-infrastructure.md` §3.4

**Problem:** The documentation reliability hierarchy (Executable > Generated > Authored) is defined in three separate places:

1. **Article I §4** (Verifiability) — defines the three-level hierarchy with descriptions.
2. **Article II §1** (Taxonomy Framework) — defines a four-tier system (adding Ephemeral) with a full table.
3. **Article VI §3.4** — restates the hierarchy again with slightly different wording.

These three versions are *almost* but not *exactly* the same. Article I uses "Executable specifications," "Generated documentation," and "Authored prose." Article II uses "Executable / Verified," "Generated / Derived," "Authored / Maintained," and "Ephemeral / Ceremonial." Article VI restates the hierarchy as "executable, tested specifications," "auto-generated documentation from source," and "human-authored prose." A reader comparing them will wonder which is canonical — exactly the kind of drift-by-duplication this framework condemns.

Similarly, metadata requirements are specified in both Article II §4 and Article IV §1, with slightly different required field lists. Article II requires `tier`; Article IV requires `tags`. Neither references the other as canonical.

**Proposed fix:**
1. Canonicalize the reliability hierarchy in Article II §1 (the most complete version) and have Articles I and VI reference it by cross-link rather than restating it.
2. Canonicalize metadata requirements in Article IV §1 (the format article) and have Article II §4 reference it. One source of truth for required fields.
3. Article I §4 should state the *principle* of verifiability without redefining the tier system. "A reliability hierarchy, defined in Article II, governs trust when sources conflict."

**Vote flip:** Sherman → YES

---

### Objection 2.5 — The Minimum Floor Is Too High for Small Teams

**Raised by:** McHenry
**Severity:** Blocking
**File:** `article-VI-tooling-and-infrastructure.md`, Section 6 (Small Team Provisions)

**Problem:** Article VI §6.1 defines the "minimum viable toolchain" as: (a) version control, (b) one prose linter in CI, (c) link checking in CI, and (d) structured metadata on every file. Article VI §6.3 adds that no team is exempt from CI validation, human review of generated output, or machine-readable metadata.

For a two-person team with a Go CLI and a README, this minimum requires:
- Setting up a CI pipeline (if one doesn't exist for docs)
- Choosing, configuring, and maintaining a prose linter (Vale requires a `.vale.ini`, style packages, and vocabulary exceptions)
- Adding link-checking tooling
- Adding YAML frontmatter to every markdown file
- Validating that frontmatter against a schema

This is 2–4 hours of setup and ongoing maintenance overhead for a project whose documentation might be a single README and an ADR file. The godoc model — write good comments, let the tool extract them — achieves 80% of the value at 10% of the ceremony.

**Proposed fix:**
1. Add a "Tier Zero" small team provision to Article VI §6: Teams of three or fewer with five or fewer documentation files MAY satisfy CI requirements through pre-commit hooks or manual checklists rather than full CI pipelines, provided they adopt CI-based validation when documentation exceeds five files or the team exceeds three members.
2. Reduce the metadata floor for small teams: require only `title`, `owner`, and `last_verified` (three fields) instead of the full seven-field set. The remaining fields become required at the five-member threshold.
3. Acknowledge that for some ecosystems (Go, Rust, Elixir), language-native doc tooling (`godoc`, `cargo doc`, `ex_doc`) satisfies the "generated documentation" and "doc-test" requirements without additional infrastructure.

**Vote flip:** McHenry → YES

---

## 3. Minor Concerns

These are imperfect but not blocking. They should be addressed in subsequent revisions.

### 3.1 No Quickstart for the Docstitution Itself (Mason)

**File:** `README.md`

The README is a philosophy document, not an adoption guide. A team encountering this framework for the first time will read 500+ words of philosophy before reaching the Table of Contents. There is no "Start Here" section, no adoption checklist, no "if you only read one article, read this one."

**Recommendation:** Add a "Quick Adoption Guide" section to the README between the Preamble and the Table of Contents: a numbered list of five steps to adopt the framework, linking to the relevant articles. Something like: "1. Add metadata to your README (Article IV). 2. Classify your existing docs (Article II). 3. Set up a linter (Article VI). 4. Assign owners (Article V). 5. Schedule your first review (Article III)."

### 3.2 RFC 2119 Language Without Declaration (Yates)

**File:** All articles

Articles III–VII use SHALL, SHOULD, MAY, and MUST extensively in the RFC 2119 style, but the Docstitution never declares that these terms carry RFC 2119 meaning. Article I and the Preamble use more conversational language ("shall carry," "must be"). This inconsistency makes it unclear whether "SHALL" in Article III carries a different weight than "shall" in Article I.

**Recommendation:** Add a brief "Conventions Used in This Document" note to the README or Article I that declares: "The key words SHALL, MUST, SHOULD, and MAY in Articles I–VII are to be interpreted as described in RFC 2119."

### 3.3 Customer-Facing Documentation Gap (Gilman)

**File:** `article-II-document-types-and-taxonomy.md`

The taxonomy covers developer-facing documentation thoroughly but has no category for:
- End-user documentation (help articles, product guides)
- Knowledge base articles (support team reference)
- FAQ documents
- Release notes for customers (as distinct from changelogs for developers)

Article II §2.1 says the README is "the front door" but for a product with end users, the front door is the help center, not the repo README.

**Recommendation:** Add a §3.8 category titled "Customer & End-User Documentation" with types: End-User Guide, FAQ, Knowledge Base Article, and Customer Release Notes. These can be "Recommended" but their absence from the taxonomy means teams won't think to classify them.

### 3.4 Tables Are Overused for Scanability (Yates)

**Files:** `article-II-document-types-and-taxonomy.md`, `article-III-lifecycle-governance.md`, `article-V-roles-and-responsibilities.md`

Multiple articles present critical information exclusively in tables. Article III §3.1 defines review cadences solely in a table with no narrative explanation. Article V §1.1 defines the entire role taxonomy in a table. Tables are excellent for reference lookup but poor for first-read comprehension. A reader encountering the role taxonomy for the first time gets a grid of cells, not an explanation of *why* these roles exist or how they interact.

**Recommendation:** Precede each critical table with 1–2 sentences of narrative context. "The following roles govern who may perform each documentation action. The key constraint is that Ownership and Approval are human-only roles, ensuring accountability cannot be delegated to agents."

### 3.5 Quarterly Review Cadence Is Calendar-Locked, Not Sprint-Aligned (Ellsworth)

**File:** `article-III-lifecycle-governance.md`, Section 3

The 90-day quarterly cadence (§3.1) doesn't map to any common sprint length. A two-week sprint team would hit the review window mid-sprint 7. A three-week sprint team would hit it at sprint 4.3. Neither is clean.

**Recommendation:** Reframe the cadence as "within N sprints" or allow teams to define their own cadence within a maximum bound. "Authored/Maintained documents SHALL be reviewed at least once every 90 calendar days or every 6 sprints, whichever comes first."

### 3.6 The Preamble's Tone May Alienate Pragmatists (Franklin)

**File:** `README.md`

The Preamble is beautifully written, but the constitutional language ("We, the delegates…," "We hold these tenets…," the Latin motto) may read as self-important to engineers who just want to know what to do. The Anti-Hypocrisy Commitment is excellent, but "Semper Reformanda" immediately after it undercuts the plain-language ethos.

**Recommendation:** Keep the constitutional framing — it's distinctive and memorable — but add a one-sentence plain-language summary at the very top of the README, before the Preamble: "This is a practical framework for writing, maintaining, and governing documentation in software teams. The articles below define what to document, how to structure it, who owns it, and how to keep it current."

### 3.7 No Mention of Internationalization or Localization (Lansing)

**File:** `article-IV-structure-and-format-standards.md`

The framework does not address documentation in languages other than the authoring language. For global teams or products with international users, there is no guidance on: translation workflows, maintaining parity between language versions, or declaring the language of a document in metadata.

**Recommendation:** Add a `language` field to recommended metadata (Article IV §1.2) and a brief note in §6 acknowledging that localization is out of scope for v1.0 but should be addressed in a future amendment.

### 3.8 Ownership Transfer Assumes Managerial Structure (Gilman)

**File:** `article-V-roles-and-responsibilities.md`, §4.3

The ownership transfer procedure (§4.3.2) says "the departing Owner or their manager shall designate a successor." Many small teams, open-source projects, and flat organizations have no "manager." The fallback (§4.3.2: "team lead assumes interim ownership") also assumes a team lead exists.

**Recommendation:** Rephrase as: "the departing Owner, their manager, or any designated team member shall identify a successor."

---

## 4. Commendations

The panel recognizes the following strengths in the draft.

### 4.1 The Dual-Audience Principle Is the Right Foundation (Franklin, Mason, Lansing)

Article I §1 establishes dual-audience primacy as the first foundational principle. This is correct and forward-looking. The framing — "Neither audience is secondary" — prevents the common failure mode of treating agent-readability as a bolt-on. Article IV §3.3 ("Accessibility and Agent Readability Converge") is an insight that deserves wider circulation: making documents accessible to screen readers makes them accessible to agents, and vice versa. This alignment could be a powerful adoption argument.

### 4.2 Small Team Provisions Throughout (McHenry, Ellsworth, Sherman)

Every substantive article (II, III, V, VI) includes a dedicated "Small Team Provisions" section. This is rare in governance frameworks and shows genuine concern for proportionality. The provisions are concrete — specific team-size thresholds, specific accommodations, explicit statements of what is *not* exempted. Article II §5.4 (deferred adoption triggers) is particularly well-designed: it tells a small team exactly *when* to adopt each additional document type. This is the kind of practical guidance that makes a framework adoptable rather than aspirational.

### 4.3 "Staleness Is a Defect" (Gerry, Yates, Gilman)

Article III §3.3 — "a document exceeding twice its freshness threshold SHALL be flagged for deprecation review" — is the strongest single provision in the framework. Treating staleness as a defect rather than a backlog item changes the organizational incentive structure. Combined with the freshness SLO concept (Article I §3), this gives teams a measurable, enforceable quality dimension that most documentation frameworks lack entirely.

### 4.4 Agent Boundaries Are Clear and Principled (Gerry, Franklin)

Article V §3.2 draws the right lines: agents may Generate, Validate, Enforce, Draft, and Review — but may not Own or Approve. The phrasing "Agents extend capacity; they do not replace accountability" (§6.2) is quotable and correct. The concern (Objection 2.1) is not with the *policy* but with its *enforceability*. The intent is exactly right.

### 4.5 Definition of Done Integration (Ellsworth)

Article III §5 mandates documentation as part of "done" and integrates it into sprint review. This is the *only* mechanism that reliably produces documentation in agile teams. The tiered process weight (§5.2) — heavier review for authored content, lighter for generated/ephemeral — shows understanding of sprint economics. §5.3's requirement to track documentation debt in the backlog treats the problem honestly.

### 4.6 The Anti-Hypocrisy Commitment (Sherman, Yates)

The Preamble's "Anti-Hypocrisy Commitment" and Article III's "Self-Governance Declaration" are the most credible parts of the framework. A documentation standard that can't govern its own documents has no authority. The fact that the Docstitution carries its own frontmatter, declares its own owner, and holds itself to its own review cadence is the strongest argument for adoption: *we eat our own cooking*.

### 4.7 No Silent Deletion (Gilman, Gerry)

Article III §4.4 — "No document that has reached Active status SHALL be deleted without passing through Deprecation and Archival" — protects institutional memory. Combined with §4.3.4 ("Regulated documents SHALL observe mandated retention periods"), this gives compliance teams a documentation lifecycle they can audit. This is a real-world need that most frameworks ignore.

### 4.8 The Emergency Amendment Process (Ellsworth, Sherman)

Article VII §6 provides a fast-track for genuine emergencies while requiring retroactive review within ten business days. This is the right balance: you can move fast when production is on fire, but you can't use "emergency" as a permanent bypass. The `[EMERGENCY]` changelog tag and retrospective discussion requirement create accountability without creating bureaucratic delay.

---

## 5. Path to Ratification

**Current vote: 5 YES / 5 NO (50%) — FAILS**

To reach 80% ratification (8 of 10), the following changes are needed:

| Objection | Fixes | Flips |
|---|---|---|
| 2.1 (Unenforceable review gates) | Add CI enforcement clause + audit sampling to Article VI §2 | Gerry → YES |
| 2.2 (Hollow accessibility requirements) | Expand Article IV §3.2, add WCAG reference link, add a11y tooling to Article VI | Lansing → YES |
| 2.3 (No required onboarding doc) | Add Getting Started Guide to Required Core with consolidation allowance | AMartin → YES |
| 2.4 (Reliability hierarchy duplication) | Canonicalize in Article II, cross-reference from I and VI; canonicalize metadata in Article IV | Sherman → YES |
| 2.5 (Floor too high for small teams) | Add Tier Zero provision, reduce metadata floor, acknowledge ecosystem tooling | McHenry → YES |

**Resolving all five critical objections yields: 10 YES / 0 NO (100%)**

Resolving any three of the five yields 80% and ratification. The panel recommends prioritizing Objections 2.2 (accessibility — legal and ethical obligation), 2.4 (redundancy — easiest fix), and 2.3 (onboarding — highest user impact) as the minimum path.

---

*Respectfully submitted by the Review Panel of Human Sympathizers and Minimalists.*

*"A framework this thorough deserves to be this honest." — Sherman*
