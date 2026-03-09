# Delegate Report: Bedford
**Role:** UX Platform Specialist (Mac/Linux) | **Experience:** 10 years | **Perspective:** Balanced

## Essential Document Types

**Strategy & Vision** — Product vision document; platform support matrix covering shells, terminals, and package managers.
**Design & Experience** — CLI reference docs; terminal-friendly quickstarts; plain-text README; man pages.
**Development** — API references with curl examples; build guides for Make/shell/CI; config reference for env vars and dotfiles; troubleshooting guides.
**Governance** — Style guide with plain-text rules and line-length conventions; contribution guide for CLI-based git workflows.

## Documents Most Critical to My Role

**1. CLI Reference Documentation** — Every command, flag, and env var following man page conventions. Primary reference invoked via `--help` or `man`. When missing, users can't discover features without leaving the terminal. Agents parse flag definitions to construct commands programmatically.

**2. Plain-Text README** — Project description, package manager installation, basic usage — renderable as plain text. The first file devs read via `cat README.md`. Without it, no entry point. Agents need a structured entry point to understand scope.

**3. Terminal-Friendly Quickstart Guides** — Copy-pasteable commands with expected output. Every command must work when pasted. Broken commands destroy trust. Agents execute these directly — must be idempotent and non-interactive.

**4. Configuration Reference** — Config paths (XDG), env vars, dotfile formats, precedence rules. Without this, users misconfigure. Agents need machine-parseable schemas to validate and generate config.

**5. Man Pages** — NAME, SYNOPSIS, DESCRIPTION, OPTIONS, EXAMPLES, EXIT CODES. Installable via package managers, offline-available. Agents parse roff reliably due to rigid structure.

## Human-Agent Documentation Considerations

1. **Docs must be plain-text-first.** If a doc can't be consumed through `cat` or `less`, it fails the portability test. No HTML embeds, no mandatory image rendering. Agents benefit equally — plain text is trivially parseable.

2. **CLI help text IS documentation.** The `--help` flag and man pages are primary doc surfaces, not supplements. Mandate they sync with canonical reference docs to prevent drift.

3. **Commands must be executable as-is.** Every shell command should be copy-pasteable. Include expected exit codes, avoid interactive prompts. Agents depend on this contract absolutely.

## Documentation Anti-Patterns

1. **Browser-Required Docs** — Docs needing interactive widgets or embedded videos with no text alternative. Terminal users and agents are locked out.
2. **Rich-Markdown Dependency** — GitHub-flavored extensions (Mermaid, nested HTML) that render as garbage in a terminal pager.
3. **The Unpasteable Command** — Examples with prompt characters (`$`), smart quotes, or invisible Unicode that break when pasted.
4. **Missing Exit Codes** — Docs showing only the happy path, never documenting failure output or exit codes.

## My Position for the Docstitution

The best documentation can be read with `cat` and `less`. This is not nostalgia — it is a design constraint that produces better docs for everyone. Plain-text-friendly formatting forces clarity: no hiding behind fancy rendering, no assumption about the reader's browser. When docs work in a terminal, they work everywhere — including inside AI agents that process text, not pixels.

Unix documentation conventions — man pages, `--help`, READMEs — endure because they are simple, predictable, and machine-parseable. The Docstitution should recognize these as first-class document types. Man pages have rigid structure that agents parse more reliably than free-form web pages. CLI help text is the most contextual documentation — available exactly where the developer is working.

I advocate for rich rendering where it adds value, but always with a plain-text fallback. No Docstitution document should require a browser. Commands must be pasteable. References must be greppable. If docs work in the harshest environment — a bare terminal over SSH — they will work beautifully everywhere else.
