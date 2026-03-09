# Delegate Report: GMorris
**Role:** TypeScript Developer | **Experience:** 12 years | **Perspective:** Balanced

## Essential Document Types

**Type-System Documentation**
- **TypeScript Interface & Type Definitions** — Exported types serving as the primary contract documentation for every module boundary.
- **JSDoc Annotations** — Inline comments expressing intent and constraints that type signatures cannot convey.
- **TypeDoc-Generated API References** — Auto-rendered documentation from source types and JSDoc for external consumers.

**Component & UI Documentation**
- **Storybook Stories** — Living, interactive examples of UI components showing every state and edge case.
- **Component Props Documentation** — Typed prop interfaces with JSDoc surfacing in IDE autocomplete and Storybook.
- **Design Token References** — Mappings between design system tokens and their CSS/JS representations.

**Project Documentation**
- **Architecture Decision Records (ADRs)** — Records explaining why a library, pattern, or structural choice was adopted.
- **Migration Guides** — Step-by-step instructions for consumers upgrading across breaking changes in shared packages.

## Documents Most Critical to My Role

1. **TypeScript Interface Definitions** — Contains every data shape, function signature, and union type. The compiler enforces them; the IDE surfaces them on hover. When types are `any`, refactors break silently. Agents use types as their highest-signal source for generating correct code.

2. **Storybook Stories** — Contains interactive examples of components across all meaningful states. I use Storybook as both workbench and docs browser. When missing, developers wire components into full pages to test them. Agents reference stories for component APIs and valid prop combinations.

3. **JSDoc on Complex Functions** — Contains the "why" types cannot express: valid ranges, performance traits, side effects. When absent, developers misuse utilities passing type-checks but failing at runtime. Agents consume JSDoc for accuracy beyond structural typing.

4. **Migration Guides** — Contains old-to-new API mappings, codemods, and breaking change justifications. When missing, teams pin old versions indefinitely. Agents automate upgrade PRs using these.

5. **ADRs for Library Choices** — Contains evaluated alternatives, criteria, and trade-offs accepted. When absent, teams relitigate decisions. Agents reference ADRs to generate code consistent with established patterns.

## Human-Agent Documentation Considerations

- **Treat types as the first documentation layer.** Use literal types, discriminated unions, and branded types before writing JSDoc. Agents extract more from precise types than from prose.
- **Keep documentation IDE-discoverable.** JSDoc, type hover, and Storybook keep docs at the point of use — where agents look first.
- **Write stories as executable specifications.** Each story is a machine-readable test case and a human-browsable example simultaneously.

## Documentation Anti-Patterns

1. **The `any` Escape Hatch** — Every `any` is an undocumented API surface that agents and developers must reverse-engineer from runtime behavior.
2. **Confluence Component Catalogs** — Documenting React components in an external wiki instead of Storybook; stale within one sprint.
3. **JSDoc That Restates the Type** — Writing `@param name - the name` on `name: string` adds noise and teaches nothing.
4. **README-Only Monorepo Docs** — A single root README for 40 packages. Each needs its own typed entrypoint documentation.

## My Position for the Docstitution

The type system is the most reliable documentation a TypeScript project possesses — checked by the compiler, surfaced by the IDE, consumed by agents on every request. The Docstitution should recognize typed interfaces as first-class documentation. When a type signature fully expresses a contract, no additional prose should be required. When it cannot, JSDoc fills the gap at the point of use.

Documentation outside the development environment gets ignored. Storybook, TypeDoc, and IDE-integrated JSDoc succeed because they meet developers and agents in their workflow. The Docstitution must prioritize formats discoverable at the point of consumption. Proximity to code and machine-checkability keep documentation alive.
