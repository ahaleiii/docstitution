# Delegate Report: Sherman
**Role:** Senior Software Engineer | **Experience:** 30 years | **Perspective:** Balanced

## Essential Document Types

**Code-Level Documentation**
- **Inline Code Comments (WHY, not WHAT):** Comments explaining the reasoning behind non-obvious decisions, not restating what the code does.
- **README Files:** The first thing a developer reads — project purpose, setup, and how to contribute.
- **CHANGELOG:** A human-curated record of what changed, why, and what it means for consumers.

**Development Process**
- **Coding Standards:** Agreed conventions that prevent style arguments in code review and make codebases consistent.
- **Code Review Guidelines:** What reviewers should look for, what constitutes a blocking issue, and how to give constructive feedback.
- **Contribution Guides:** How to fork, branch, test, and submit changes — especially for open-source or cross-team projects.

**Operational**
- **Troubleshooting Guides:** Symptom-based documents that map observable problems to likely causes and fixes.
- **Deployment Checklists:** Ordered steps for releasing code, including pre-deploy checks and rollback procedures.
- **On-Call Runbooks:** Practical instructions for the person carrying the pager, not the person who designed the system.

**Design & Architecture**
- **Architecture Decision Records:** Brief documents capturing what was decided and why — emphasis on brevity and honesty.
- **API Documentation:** Endpoint references that stay current because they are generated from code, not written in a wiki.
- **Design Documents:** Lightweight proposals for significant changes, reviewed before implementation begins.

## Documents Most Critical to My Role

1. **Inline Code Comments Explaining WHY** — These are not documents in a folder; they live in the code itself, explaining why a workaround exists, why a particular algorithm was chosen, or why a seemingly wrong approach is actually correct. I write and read these every day during code review. When missing, engineers "fix" code that was intentionally written that way, reintroducing bugs that were solved months ago. Agents performing code analysis or suggesting refactors need WHY-comments to avoid undoing intentional trade-offs.

2. **README Files** — Contains what the project does, how to set it up, how to run tests, and where to find more information. I use the README as my first stop when touching an unfamiliar codebase. When absent or outdated, I spend thirty minutes asking around instead of thirty seconds reading. Agents use READMEs to understand project context before generating code — a bad README means bad suggestions.

3. **Troubleshooting Guides** — Organized by symptom ("build fails with error X," "service returns 503"), each entry maps to root causes and resolution steps. I consult these during incidents and contribute to them after every post-mortem. When they do not exist, engineers debug from scratch every time the same issue recurs. Agents can use symptom-based structure to match error outputs to known solutions automatically.

4. **Coding Standards** — Specifies naming conventions, error handling patterns, test expectations, and formatting rules for each language used. I enforce these in code review and reference them when onboarding new team members. Without them, every pull request becomes a style debate. Agents generating code should consume these standards to produce compliant output without human correction.

5. **Architecture Decision Records** — Short documents — one to two pages — capturing what was decided, what alternatives were rejected, and what trade-offs were accepted. I read these when I need to understand why the system looks the way it does. When missing, teams waste sprint cycles revisiting decisions that were already made. Agents benefit from ADRs to understand constraints before suggesting architectural changes.

## Human-Agent Documentation Considerations

- **Comments must explain WHY, not WHAT:** Code that says `i += 1` does not need a comment saying "increment i." It might need a comment saying "off-by-one correction for zero-indexed API response." Agents parsing code need the WHY to avoid breaking intentional logic during refactoring.
- **Put documentation where developers look:** Inline comments in code, READMEs in repositories, runbooks linked from alerting dashboards. If documentation lives somewhere developers do not already go, it will not be read — and agents will not find it either. Proximity to context matters.
- **Keep documents short enough to actually read:** A 40-page design document will not be read by humans or efficiently processed by agents. Break documents into focused, single-purpose pages. If a document tries to cover everything, it effectively covers nothing.

## Documentation Anti-Patterns

1. **Documentation Theater:** Writing extensive documentation to satisfy a process checkbox rather than to help anyone. Fifty pages of architecture docs that no one reads and no one maintains. If the audience cannot be named, the document should not exist.
2. **Comments Restating Code:** `x = x + 1 // add one to x` — these comments add noise, not signal. They train developers to ignore all comments, including the important ones.
3. **The Wiki Graveyard:** Documentation stored in a wiki that is not linked from code, not searchable from the IDE, and not maintained after the initial writing sprint. Knowledge goes to wikis to die.
4. **Aspirational Documentation:** Documents describing how the system should work rather than how it actually works. These are more dangerous than no documentation because they provide false confidence.
5. **Mandatory Templates With Empty Sections:** Requiring every document to fill out fifteen sections results in documents padded with "N/A" and "TBD." Templates should be guides, not bureaucratic forms.

## My Position for the Docstitution

Thirty years of writing software have taught me one thing about documentation: the best documentation is the documentation developers actually read. I have watched organizations produce thousands of pages of docs that nobody opens while engineers pass critical knowledge through Slack messages and tribal memory. The Docstitution must resist the temptation to mandate documentation volume and instead focus on documentation value. Every required document type should have a clear, named audience and a clear reason to exist.

I fight for inline code comments that explain WHY, not WHAT. I fight for READMEs that actually help. I fight for putting documentation where developers already look — in the code, in the repository, next to the thing it describes. Documentation that requires a separate tool, a separate login, or a separate search to find is documentation that will be ignored. The Docstitution should mandate proximity: docs live with the code they describe, versioned together, reviewed together, and maintained together.

I support structured documentation for agent consumption, but not at the cost of human readability. If adding frontmatter and metadata makes a document harder for a developer to write and maintain, we will end up with fewer documents, not better ones. The Docstitution must find the balance: lightweight structure that serves agents without burdening the humans who must keep the documentation alive.
