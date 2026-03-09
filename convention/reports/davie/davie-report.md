# Delegate Report: Davie
**Role:** Mobile Developer | **Experience:** 9 years | **Perspective:** Balanced

## Essential Document Types

**Platform-Specific Guides**
- **iOS Development Guide** — Platform lifecycle, permission flows, and Human Interface Guidelines compliance.
- **Android Development Guide** — Android architecture patterns, permission models, and Material Design compliance.
- **Cross-Platform Strategy Doc** — Shared vs. platform-specific code decisions and parity expectations.

**App Store & Distribution**
- **App Store Submission Checklist** — Requirements for Apple and Google Play: metadata, screenshots, privacy labels, and review guidelines.
- **App Store Compliance Doc** — Feature-to-policy mapping with risk flags for rejection-prone patterns.

**Mobile Architecture & API**
- **Mobile API Contract Doc** — API docs for mobile constraints: payload limits, bandwidth-tuned pagination, offline-safe endpoints.
- **Offline-First Architecture Doc** — Sync strategy, conflict resolution, local storage schemas, and degraded-mode behavior.
- **Push Notification Docs** — Platform-specific registration, payload schemas, and deep link handling.

**Testing & Quality**
- **Device Matrix Doc** — Supported devices, OS versions, screen sizes, and testing priority tiers.

## Documents Most Critical to My Role

1. **App Store Submission Checklist** — Every requirement for store submissions: metadata, privacy declarations, entitlements. Used before every release to prevent rejections. Outdated checklists mean failed reviews and delayed releases. Agents validate readiness by checking items against current store policies.

2. **Offline-First Architecture Doc** — Sync strategy, conflict resolution, local schemas, and degradation behavior. Referenced during feature dev and debugging. Without it, developers make conflicting offline assumptions. Agents need structured sync rules to generate correct data-layer code.

3. **Platform-Specific Guides** — Platform lifecycle events, permission flows, and design guidelines. Consumed daily. Stale guides cause app review rejection. Agents must distinguish between platforms; a generic guide produces platform-incorrect code.

4. **Mobile API Contract Doc** — API behavior from mobile perspective: compression, pagination for bandwidth, cache-control. Generic API docs ignore mobile constraints, producing bloated payloads on 3G. Agents consume mobile contracts to generate bandwidth-efficient network code.

5. **Device Matrix Doc** — Supported devices, OS ranges, and testing tiers. Used in QA planning. Without it, teams test on flagships and miss real-world issues. Agents use the matrix for platform-conditional code and test configurations.

## Human-Agent Documentation Considerations

- **Platform tags on every document** — Metadata indicating which platform(s) apply (iOS, Android, both) so agents filter relevant guidance per target.
- **Store policy version tracking** — Compliance docs referencing specific policy versions so agents can flag outdated guidance.
- **Connectivity-aware sections** — Structured sections for online, offline, and degraded behavior so agents generate complete implementations.

## Documentation Anti-Patterns

1. **Platform-blind docs** — A single "mobile" guide without iOS/Android distinction. Different lifecycles and review processes guarantee bugs on one platform.
2. **Ignoring store constraints** — Treating submission as a deployment detail. Store rejections cost days; undocumented requirements cost releases.
3. **Desktop-assumed API docs** — APIs documented assuming unlimited bandwidth and persistent connections.
4. **Missing offline specs** — Features documented only for the online happy path.

## My Position for the Docstitution

Mobile is documentation on hard mode: two platforms with different rules, third-party review gates, and users on 3G with old devices. The Docstitution must recognize platform-specific documentation as a structural requirement, not a luxury. A single guide that says "works on mobile" guarantees bugs on one platform and rejection from the other's store.

I advocate for mandatory platform tagging, a living device matrix, and offline-first architecture docs for any networked feature. For agents, the critical need is platform awareness — agents generating code must know which platform, OS versions, and connectivity constraints apply. Documents must carry enough structured context for platform-correct output without humans specifying the target every time.
