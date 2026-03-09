<!--
---
document_type: compliance-review
title: "Anti-Hypocrite Compliance Review"
status: draft
owner: Convention Review Committee
audience: [humans, agents]
last_verified: 2025-07-25
tags: [compliance, review, anti-hypocrite, ratification]
reviewers:
  - Washington (Convention President, 30yr)
  - Madison (Documentation Architect, 25yr)
  - Wythe (Compliance Architect, 30yr)
---
-->

# Anti-Hypocrite Compliance Review

> *"If the framework cannot govern its own documents, it has no authority to govern others."*
> — Preamble, Anti-Hypocrisy Commitment

**Reviewers:** Washington (Convention President), Madison (Documentation Architect), Wythe (Compliance Architect)

**Date:** 2025-07-25

**Scope:** All eight governing documents of the Docstitution (README + Articles I–VII), evaluated against the standards they themselves prescribe.

**Verdict:** ❌ **DOES NOT PASS.** The Docstitution contains 47 distinct violations of its own rules across metadata, cross-references, consistency, and structural standards. The framework is directionally strong but cannot be ratified until these violations are remediated.

---

## 1. Compliance Matrix

Legend: ✅ = Compliant · ❌ = Non-compliant · ⚠️ = Partial/Inconsistent

| Criterion | README | Art I | Art II | Art III | Art IV | Art V | Art VI | Art VII |
|---|---|---|---|---|---|---|---|---|
| **Has YAML frontmatter** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Frontmatter delimiters (`---`)** | ✅ | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ |
| **`document_type` present** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ |
| **`title` present** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **`status` present** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **`owner` present** | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ |
| **`audience` present** | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ | ❌ | ❌ |
| **`last_verified` present** | ❌ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| **`tags` present (Art IV §1.1)** | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| **No heading-level skips** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Semantic heading hierarchy** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Cross-refs use explicit links** | ⚠️ | ⚠️ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ |
| **Cross-ref paths are valid** | ❌ | ❌ | N/A | N/A | ✅ | N/A | N/A | N/A |
| **Plain-text readable** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Review cadence declared** | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ |
| **H1 matches `title` metadata** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Consistent section numbering** | ✅ | ✅ | ✅ | ✅ | ⚠️ | ✅ | ✅ | ✅ |
| **`document_type` consistent** | — | ⚠️ | ⚠️ | ⚠️ | ⚠️ | ❌ | ❌ | ❌ |
| **`audience` format consistent** | — | ⚠️ | ⚠️ | ❌ | ⚠️ | ❌ | ❌ | ❌ |
| **`owner` format consistent** | — | ⚠️ | ⚠️ | ⚠️ | ⚠️ | ❌ | ❌ | ❌ |

---

## 2. Violations Found

### Category A: Missing Required Metadata Fields

Per Article IV §1.1, every governed document requires: `document_type`, `title`, `status`, `owner`, `audience`, `last_verified`, `tags`.

| # | File | Field | Issue |
|---|---|---|---|
| A1 | `README.md` | `last_verified` | Missing. Has `last_reviewed` instead (wrong field name per Art IV). |
| A2 | `README.md` | `tags` | Missing entirely. |
| A3 | `article-I-foundational-principles.md` | `tags` | Missing entirely. |
| A4 | `article-II-document-types-and-taxonomy.md` | `last_verified` | Missing. Has `last_reviewed` instead. |
| A5 | `article-II-document-types-and-taxonomy.md` | `tags` | Missing entirely. |
| A6 | `article-III-lifecycle-governance.md` | `audience` | Missing entirely. |
| A7 | `article-III-lifecycle-governance.md` | `last_verified` | Missing. Has `last_reviewed: null` — both wrong field name AND null value. |
| A8 | `article-III-lifecycle-governance.md` | `tags` | Missing entirely. |
| A9 | `article-V-roles-and-responsibilities.md` | `document_type` | Missing entirely. |
| A10 | `article-V-roles-and-responsibilities.md` | `owner` | Missing. Has `drafting_committee` list but no `owner` field. |
| A11 | `article-V-roles-and-responsibilities.md` | `audience` | Missing entirely. |
| A12 | `article-V-roles-and-responsibilities.md` | `last_verified` | Missing entirely. |
| A13 | `article-V-roles-and-responsibilities.md` | `tags` | Missing entirely. |
| A14 | `article-VI-tooling-and-infrastructure.md` | `document_type` | Missing entirely. |
| A15 | `article-VI-tooling-and-infrastructure.md` | `owner` | Missing. Has `drafted_by` list but no `owner` field. |
| A16 | `article-VI-tooling-and-infrastructure.md` | `audience` | Missing entirely. |
| A17 | `article-VI-tooling-and-infrastructure.md` | `last_verified` | Missing entirely. |
| A18 | `article-VI-tooling-and-infrastructure.md` | `tags` | Missing entirely. |
| A19 | `article-VII-amendment-process.md` | `document_type` | Missing entirely. |
| A20 | `article-VII-amendment-process.md` | `owner` | Missing. Has `drafted_by` list but no `owner` field. |
| A21 | `article-VII-amendment-process.md` | `audience` | Missing entirely. |
| A22 | `article-VII-amendment-process.md` | `last_verified` | Missing entirely. |
| A23 | `article-VII-amendment-process.md` | `tags` | Missing entirely. |

**Total: 23 missing-field violations.**

### Category B: Broken Cross-References

Per Article IV §4.3, all internal links SHALL be valid.

| # | File | Line(s) | Broken Link | Correct Target |
|---|---|---|---|---|
| B1 | `README.md` | 105 | `articles/article-i.md` | `article-I-foundational-principles.md` |
| B2 | `README.md` | 106 | `articles/article-ii.md` | `article-II-document-types-and-taxonomy.md` |
| B3 | `README.md` | 107 | `articles/article-iii.md` | `article-III-lifecycle-governance.md` |
| B4 | `README.md` | 108 | `articles/article-iv.md` | `article-IV-structure-and-format-standards.md` |
| B5 | `README.md` | 109 | `articles/article-v.md` | `article-V-roles-and-responsibilities.md` |
| B6 | `README.md` | 110 | `articles/article-vi.md` | `article-VI-tooling-and-infrastructure.md` |
| B7 | `README.md` | 111 | `articles/article-vii.md` | `article-VII-amendment-process.md` |
| B8 | `README.md` | 19–38 | YAML `articles[].path` entries | Same — all use `articles/article-*.md` pattern that doesn't exist. |
| B9 | `article-I-foundational-principles.md` | 39 | `article-IV-structure-format-standards.md` | `article-IV-structure-and-format-standards.md` |
| B10 | `article-I-foundational-principles.md` | 54 | `article-II-document-types-taxonomy.md` | `article-II-document-types-and-taxonomy.md` |
| B11 | `article-I-foundational-principles.md` | 87 | `article-VI-tooling-infrastructure.md` | `article-VI-tooling-and-infrastructure.md` |
| B12 | `article-I-foundational-principles.md` | 69 | `article-VI-tooling-infrastructure.md` | `article-VI-tooling-and-infrastructure.md` |
| B13 | `article-I-foundational-principles.md` | 116 | `article-V-roles-responsibilities.md` | `article-V-roles-and-responsibilities.md` |

**Pattern:** Article I systematically drops `-and` from filenames. README references a non-existent `articles/` subdirectory.

**Total: 13 broken link violations (B8 counts as 7 individual broken paths).**

### Category C: Missing Explicit Cross-Reference Links

Per Article IV §4.2, cross-references SHALL be rendered as Markdown links, not implicit name-drops.

| # | File | Section(s) | Issue |
|---|---|---|---|
| C1 | `article-II-document-types-and-taxonomy.md` | §1 Cl.3, §2.1, §2.4, §2.5, §4 | References "Article I", "Article III", "Article IV", "Article VI" as plain text — no Markdown links. |
| C2 | `article-III-lifecycle-governance.md` | §1.2, §2.1, §3.1–3.4, §4, §5 | References Articles I, II, IV, V, VI as plain text — no Markdown links. |
| C3 | `article-V-roles-and-responsibilities.md` | §1–6 (throughout) | References Articles I, III, IV, V, VI as plain text — no Markdown links. |
| C4 | `article-VI-tooling-and-infrastructure.md` | §1–6 (throughout) | References Articles II, III, IV, V as plain text — no Markdown links. |
| C5 | `article-VII-amendment-process.md` | §1–6 (throughout) | References Articles I–VII as plain text — no Markdown links. |

**Total: 5 documents with implicit (non-linked) cross-references.**

### Category D: Frontmatter Format Inconsistency

Article IV §1.1 specifies frontmatter must be enclosed in HTML comment (`<!-- -->`) or YAML fence (`---`). The documents use an HTML-comment-wrapped YAML fence, but inconsistently:

| # | File | Issue |
|---|---|---|
| D1 | `article-I-foundational-principles.md` | Frontmatter in HTML comment WITHOUT `---` YAML delimiters. All other documents that use `---` delimiters include them. |
| D2 | `article-IV-structure-and-format-standards.md` | Same — no `---` delimiters inside HTML comment. |

### Category E: Metadata Value Inconsistencies

| # | Field | Issue | Affected Files |
|---|---|---|---|
| E1 | `document_type` | Five different values used for the same kind of document: `constitution`, `governing-document`, `constitutional_article` (underscore), `governance`, `constitutional-article` (hyphen). | README, Art I, II, III, IV |
| E2 | `audience` | Four different formats: `[humans, agents]`, `both`, `[human-authors, agent-consumers, documentation-maintainers]`, or missing. | README/Art I, Art II, Art IV, Art III/V/VI/VII |
| E3 | `status` | Casing inconsistency: `draft` (lowercase) in 7 documents vs `Draft` (Title Case) in Article III. Article III §1.1 defines stages in Title Case; Article IV §1.1 defines enum in lowercase. | Art III |
| E4 | `owner` | Format varies: natural language (`Docstitution Convention`), kebab-case (`convention-committee`, `article-iv-drafting-committee`), Title Case (`Article II Drafting Committee`), or missing. | All documents |
| E5 | Freshness field | Two competing field names: `last_verified` (Art I, IV use and prescribe) vs `last_reviewed` (Art II, III use). Article IV §1.1 mandates `last_verified`; Article II §4 Cl.2 mandates `last_reviewed`. The Docstitution cannot agree with itself on what to call this field. | Art I prescribes `last_verified`; Art II prescribes `last_reviewed` |

### Category F: Internal Contradictions Between Articles

| # | Contradiction | Articles Involved |
|---|---|---|
| F1 | **Required metadata fields disagree.** Article I §1 requires: `document_type`, `title`, `owner`, `audience`, `last_verified`. Article II §4 Cl.2 requires: `document_type`, `title`, `tier`, `audience`, `status`, `owner`, `last_reviewed`. Article IV §1.1 requires: `document_type`, `title`, `status`, `owner`, `audience`, `last_verified`, `tags`. These three lists conflict on field names (`last_verified` vs `last_reviewed`), and on which fields are mandatory (`tier`, `tags`). | Art I, Art II, Art IV |
| F2 | **Status enum values disagree.** Article IV §1.1 defines status as: `draft`, `active`, `review`, `deprecated`, `archived`. Article III §1.1 defines lifecycle stages as: `Draft`, `Active`, `Under Review`, `Deprecated`, `Archived`. Different terms (`review` vs `Under Review`) and different casing. | Art III, Art IV |
| F3 | **Article VI cross-references have swapped titles.** In its YAML metadata, Article VI maps Article III → "Structure & Formatting" and Article IV → "Lifecycle & Maintenance". These are reversed. Article III is "Lifecycle Governance" and Article IV is "Structure & Format Standards". | Art VI |

### Category G: Review Cadence / Freshness Declarations

Per Article I §3 and Article III §3.1, every Authored/Maintained document must declare its review cadence.

| # | File | Issue |
|---|---|---|
| G1 | `README.md` | No review cadence declared. |
| G2 | `article-I-foundational-principles.md` | No review cadence declared. |
| G3 | `article-II-document-types-and-taxonomy.md` | Has `requires_review_by` (good), but no explicit `review_cadence` field. |
| G4 | `article-IV-structure-and-format-standards.md` | No review cadence declared. |
| G5 | `article-V-roles-and-responsibilities.md` | No review cadence declared. |
| G6 | `article-VI-tooling-and-infrastructure.md` | No review cadence declared. |
| G7 | `article-VII-amendment-process.md` | No review cadence declared. |

Only Article III explicitly declares its review cadence (`quarterly`, 90 days). Article II partially complies via `requires_review_by`.

### Category H: Structural Style Inconsistency

| # | Issue | Details |
|---|---|---|
| H1 | **Section separator style.** Articles I–III, V–VII use `## Section N. Title` (period). Article IV uses `## Section N: Title` (colon). | Art IV deviates from all others. |
| H2 | **Sub-section heading style.** Three different patterns: (a) H3 `### § N.N Title` (Art II, V); (b) H3 `### Section N.N: Title` (Art IV); (c) Bold inline `**§N.N**` with no heading (Art III, VI, VII). Article I has no sub-sections. | No single convention across articles. |
| H3 | **Clause numbering.** Article II uses "Clause N." Article III uses "§N.N" inline bold. Article IV uses sub-section headings. Article VI uses "(a)", "(b)", "(c)" lettering. No uniform clause format. | Four different clause/sub-section formats. |

---

## 3. Cross-Reference Audit

### 3.1 Link Validation Summary

| Source | Target | Valid? | Issue |
|---|---|---|---|
| README → `articles/article-i.md` | `article-I-foundational-principles.md` | ❌ | No `articles/` directory exists. Files are at repo root. |
| README → `articles/article-ii.md` | `article-II-document-types-and-taxonomy.md` | ❌ | Same — wrong path prefix. |
| README → `articles/article-iii.md` | `article-III-lifecycle-governance.md` | ❌ | Same. |
| README → `articles/article-iv.md` | `article-IV-structure-and-format-standards.md` | ❌ | Same. |
| README → `articles/article-v.md` | `article-V-roles-and-responsibilities.md` | ❌ | Same. |
| README → `articles/article-vi.md` | `article-VI-tooling-and-infrastructure.md` | ❌ | Same. |
| README → `articles/article-vii.md` | `article-VII-amendment-process.md` | ❌ | Same. |
| README → `./letter-of-impetus.md` | `letter-of-impetus.md` | ✅ | Valid. |
| Art I → `article-IV-structure-format-standards.md` | `article-IV-structure-and-format-standards.md` | ❌ | Missing `-and` in filename. |
| Art I → `article-II-document-types-taxonomy.md` | `article-II-document-types-and-taxonomy.md` | ❌ | Missing `-and` in filename. |
| Art I → `article-III-lifecycle-governance.md` | — | ✅ | Valid. |
| Art I → `article-VI-tooling-infrastructure.md` | `article-VI-tooling-and-infrastructure.md` | ❌ | Missing `-and` in filename. |
| Art I → `article-V-roles-responsibilities.md` | `article-V-roles-and-responsibilities.md` | ❌ | Missing `-and` in filename. |
| Art I → `article-VII-amendment-process.md` | — | ✅ | Valid. |
| Art IV → `article-I-foundational-principles.md` | — | ✅ | Valid. |
| Art IV → `article-II-document-types-and-taxonomy.md` | — | ✅ | Valid. |
| Art IV → `convention/committees/madison-synthesis.md` | — | ✅ | Valid. |

### 3.2 Orphan Check

Per Article IV §4.1, every document must be reachable via at least one inbound link.

| Document | Inbound Links From | Orphaned? |
|---|---|---|
| `README.md` | Repository root (implicit) | ✅ Reachable |
| `article-I-foundational-principles.md` | README (broken link), Art IV (valid) | ⚠️ Only reachable from Art IV |
| `article-II-document-types-and-taxonomy.md` | README (broken), Art IV (valid) | ⚠️ Only reachable from Art IV |
| `article-III-lifecycle-governance.md` | README (broken), Art I (valid) | ⚠️ Only reachable from Art I |
| `article-IV-structure-and-format-standards.md` | README (broken), Art I (broken) | ❌ **Effectively orphaned** — no valid inbound link |
| `article-V-roles-and-responsibilities.md` | README (broken), Art I (broken) | ❌ **Effectively orphaned** — no valid inbound link |
| `article-VI-tooling-and-infrastructure.md` | README (broken), Art I (broken) | ❌ **Effectively orphaned** — no valid inbound link |
| `article-VII-amendment-process.md` | README (broken), Art I (valid) | ⚠️ Only reachable from Art I |
| `letter-of-impetus.md` | README (valid) | ✅ Reachable |
| `convention/committees/madison-synthesis.md` | Art IV (valid) | ✅ Reachable |

**Articles IV, V, and VI are effectively orphaned** — no valid inbound link exists from any other governed document.

### 3.3 Bidirectionality Check

Per Article IV §4.2, cross-references SHOULD be bidirectional.

- Article IV references Article I and Article II. Neither Article I nor Article II links back to Article IV with a valid link.
- Article I references Articles II–VII. None of Articles II–VII link back to Article I (Articles II, III, V, VI, VII have no inline links at all).

**Bidirectionality is absent across the document set.**

---

## 4. Consistency Audit

### 4.1 Terminology Inconsistencies

| Term | Usage Variants | Where |
|---|---|---|
| Freshness date field | `last_verified` vs `last_reviewed` | Art I/IV prescribe `last_verified`; Art II prescribes `last_reviewed`; documents use both interchangeably |
| Status values | `draft`/`active`/`review`/`deprecated`/`archived` (Art IV) vs `Draft`/`Active`/`Under Review`/`Deprecated`/`Archived` (Art III) | Different casing and `review` ≠ `Under Review` |
| Document type | `constitution`, `governing-document`, `constitutional_article`, `governance`, `constitutional-article` | Five different values across five documents for the same category |
| Audience values | `[humans, agents]`, `both`, `[human-authors, agent-consumers, documentation-maintainers]` | README/Art I, Art II, Art IV |
| Section separator | Period (`.`) vs Colon (`:`) | Art I–III/V–VII use period; Art IV uses colon |

### 4.2 Constitutional Style Inconsistencies

| Aspect | Variants | Documents |
|---|---|---|
| Section headings | `## Section N. Title` vs `## Section N: Title` | Art IV is the outlier (colon) |
| Sub-section format | H3 `### § N.N` vs H3 `### Section N.N:` vs bold inline `**§N.N**` | Three patterns across seven articles |
| Clause notation | "Clause N." vs "§N.N" vs "(a)/(b)/(c)" vs none | Art II, Art III/VI/VII, Art VI, Art I |
| Ratification footer | "Submitted for ratification by..." vs "Ratified by..." vs "Drafted by..." vs "Respectfully submitted by..." | Different closing language in each article |
| Metadata `cross_references` format | List of file paths vs list of article numbers vs list of objects with `article`/`title` vs list of short ids | Art IV, Art II, Art VI, Art V |

### 4.3 Voice and Tone

All documents maintain a consistent formal, constitutional voice. **This is a compliance bright spot.** The deliberative, authoritative tone established in the Preamble carries through all Articles. The "We hold..." and "SHALL/SHOULD/MAY" convention language is consistent throughout.

---

## 5. Overall Verdict

### Does the Docstitution Pass the Anti-Hypocrite Condition?

## ❌ No. Not yet.

The Docstitution contains **47 distinct violations** of its own prescriptions:

| Category | Count | Severity |
|---|---|---|
| **A. Missing required metadata fields** | 23 | 🔴 Critical — violates Art I §1, Art II §4, Art IV §1.1 |
| **B. Broken cross-reference links** | 13 | 🔴 Critical — violates Art IV §4.3 |
| **C. Missing explicit link syntax** | 5 docs | 🟡 Major — violates Art IV §4.2 |
| **D. Frontmatter format inconsistency** | 2 | 🟡 Major — violates Art IV §1.1 consistency |
| **E. Metadata value inconsistency** | 5 | 🟡 Major — violates Art IV §1.1 enum definitions |
| **F. Internal contradictions between articles** | 3 | 🔴 Critical — framework disagrees with itself |
| **G. Missing review cadence declarations** | 7 | 🟡 Major — violates Art I §3, Art III §3.1 |
| **H. Structural style inconsistency** | 3 | 🟠 Moderate — undermines consistency principle |

### What Must Be Fixed Before Ratification

**Critical (must fix):**

1. **Resolve the `last_verified` vs `last_reviewed` conflict.** Articles I and IV prescribe `last_verified`; Article II prescribes `last_reviewed`. Pick one. Apply it everywhere. (Recommendation: `last_verified` — it is more precise and used by the format-authority Article IV.)

2. **Fix all README cross-reference links.** The Table of Contents links to `articles/article-*.md` — a directory that does not exist. All seven links are broken. Update to correct root-level filenames.

3. **Fix all Article I cross-reference links.** Four of six inter-article links drop `-and` from filenames.

4. **Add missing `document_type`, `owner`, and `audience` to Articles V, VI, and VII.** These three documents are each missing three critical metadata fields.

5. **Add `last_verified` dates to all documents.** Six of eight documents lack this field (or use the wrong field name).

6. **Resolve the status enum conflict between Article III and Article IV.** Agree on casing and terminology for lifecycle stages.

7. **Correct Article VI's swapped cross-reference titles.** Article III is "Lifecycle Governance", not "Structure & Formatting".

**Major (should fix):**

8. **Add `tags` to all documents.** Only Article IV has tags; Article IV itself requires them.

9. **Standardize `document_type` values.** Adopt a single canonical type for constitutional articles (recommendation: `constitutional-article` per Article IV's own choice).

10. **Add explicit Markdown links in Articles II, III, V, VI, VII** wherever they reference other Articles by name.

11. **Standardize `audience` field format.** Choose between `[humans, agents]`, `both`, or a more specific list — and use it everywhere.

12. **Add `---` YAML delimiters to Articles I and IV frontmatter** for consistency with the other six documents.

13. **Add review cadence declarations** to all documents (only Article III has one).

**Moderate (recommended):**

14. **Standardize section numbering style.** Choose period or colon for section headings. Choose between H3 sub-sections or bold inline clauses.

15. **Standardize `owner` field format.** Choose between kebab-case identifiers and natural-language names.

16. **Standardize `cross_references` metadata format.** Choose between file paths, article numbers, or structured objects.

17. **Ensure bidirectional cross-references** where Articles reference each other.

18. **Add frontmatter to `letter-of-impetus.md`** if it is considered a governed document (it is linked from README).

---

### What the Docstitution Gets Right

This review would be incomplete without acknowledging the framework's substantial strengths:

- ✅ **Every document has YAML frontmatter** — the practice is universal even where the fields are incomplete.
- ✅ **No heading-level skips anywhere** — semantic heading hierarchy is flawless across all eight documents.
- ✅ **Plain-text readability is excellent** — every document is fully usable with `cat` or `less`.
- ✅ **H1 titles match metadata titles** in every document.
- ✅ **Voice and tone are consistent** — the constitutional register is maintained throughout.
- ✅ **Dual-audience structure is demonstrated** — structured tables, metadata, and semantic headings serve agents; narrative prose serves humans.
- ✅ **The Anti-Hypocrisy Commitment exists** — the Preamble explicitly holds itself accountable. This review is evidence that the commitment is real.

The violations are numerous but correctable. The framework's principles are sound. The implementation needs a remediation pass before the Convention can ratify with integrity.

---

*Respectfully submitted,*

*Washington (Convention President) · Madison (Documentation Architect) · Wythe (Compliance Architect)*

*"We hold ourselves to the standard we prescribe. Fix the frame before we sign it."*
