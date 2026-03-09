# Delegate Report: Mifflin
**Role:** Rust Developer | **Experience:** 8 years | **Perspective:** Agent Sympathizer

## Essential Document Types

**Project Foundation**
- README — Project overview with build instructions and MSRV policy.
- CONTRIBUTING — Workflow including `cargo clippy`, `cargo fmt`, and doc expectations.
- CHANGELOG — Semver-linked history emphasizing breaking changes.

**Technical Reference**
- API Reference — `cargo doc`-generated crate docs with tested examples.
- Trait Documentation — Contracts, invariants, and implementor guidance for public traits.
- Error Handling Guide — Error enum taxonomy and recovery strategies.
- Unsafe Code Justification — Per-block rationale with soundness proofs.

**Operational**
- Build & CI Guide — Toolchain versions, feature flags, and WASM targets.
- Migration Guide — Upgrade paths with before/after code examples.

## Documents Most Critical to My Role

**1. API Reference with Doc-Tests**
Contains crate docs with executable `/// # Examples` blocks validated by `cargo test`. Used on every refactor cycle. When stale, examples fail to compile — staleness is a test failure, not silent rot. Agents extract working code directly, knowing the compiler verified it.

**2. Trait Documentation**
Contains trait purpose, required invariants, and example implementations. Used whenever implementing trait boundaries. When missing, agents generate unsound implementations. Trait docs are type-level specs both audiences depend on.

**3. Error Handling Guide**
Contains error hierarchy, conversion paths, and context-adding patterns. Used during every error path design. When absent, error types proliferate without strategy and agents wrap errors inconsistently.

**4. Unsafe Code Justification**
Contains per-block safety invariants and reviewer sign-off. Used during code review and audits. When missing, unsafe blocks become black boxes agents cannot reason about.

**5. Build & CI Guide**
Contains toolchain pinning, feature flag matrix, and compilation steps. Used for environment setup. When incomplete, agents generate incompatible feature combinations.

## Human-Agent Documentation Considerations

1. **Make doc-tests the canonical example source.** Compiler-verified examples are trustworthy for agents to extract. Dead examples are worse than none because agents reproduce errors confidently.
2. **Encode invariants in doc comments, not just types.** Semantic invariants — "this must be called before init" — belong in comments where agents read them before writing code.
3. **Use structured error catalogs with machine-parseable codes.** Agents troubleshooting errors need a lookup table: code → cause → resolution.

## Documentation Anti-Patterns

1. **The Untested Example** — Code blocks never compiled, silently diverging from the API they demonstrate.
2. **The Safety Comment Vacuum** — `unsafe` blocks with no `// SAFETY:` comment, leaving agents unable to evaluate soundness.
3. **The Feature Flag Maze** — Dozens of Cargo features with no docs on valid combinations or incompatibilities.
4. **The Trait Without a Contract** — A public trait with signatures but no behavioral expectations.

## My Position for the Docstitution

Documentation should be held to the same standard as code: if it passes tests, it ships; if not, it blocks the build. Rust's doc-test system proves this is practical. The Docstitution should mandate that every code example be executable and CI-tested. Untested examples are not documentation; they are liability.

I approach this as an agent sympathizer because agents consuming unreliable docs generate code that looks correct but violates unwritten invariants. The fix is not dumbing down docs for machines but making them precise enough for a compiler to validate. Trait contracts, safety justifications, and error taxonomies benefit humans and agents equally. The Docstitution should enshrine the principle that documentation degrades to the level of its verification.
