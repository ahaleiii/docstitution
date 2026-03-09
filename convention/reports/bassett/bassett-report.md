# Delegate Report: Bassett
**Role:** UX Platform Specialist (Windows) | **Experience:** 10 years | **Perspective:** Balanced

## Essential Document Types

**Strategy & Vision** — Product vision document; platform support matrix.
**Design & Experience** — Platform-specific quickstart guides; code sample libraries; environment setup guides.
**Development** — API reference docs; build and deployment guides; troubleshooting guides; configuration reference.
**Governance** — Platform convention standards; documentation style guide with OS-conditional content rules.

## Documents Most Critical to My Role

**1. Platform-Specific Quickstart Guides** — Step-by-step using Visual Studio, PowerShell, winget, MSBuild with correct Windows paths. The first doc a Windows dev touches — it must work on first attempt. When missing, devs hit errors on step one and lose trust. Agents need platform tags to select the right quickstart and understand backslash conventions.

**2. Code Sample Libraries** — Working examples using WinUI 3, .NET, Win32 with correct project structures and NuGet refs. Devs copy these directly; agents reference them to generate platform-correct code. Without Windows samples, agents generate forward-slash paths and bash syntax. Agents need metadata indicating platform, framework, and SDK version.

**3. Platform Support Matrix** — Supported OS versions, architectures, SDK requirements, known limitations. Devs and agents check compatibility before starting. Missing data means users attempt unsupported configs. Agents need structured data (JSON/YAML) for programmatic checks.

**4. Environment Setup Guides** — Visual Studio workloads, Windows SDK, .NET SDK installation, env vars, path config. Prerequisite for all dev work. Without them, hours lost to environment debugging. Agents need version-pinned requirements for auto-configuration.

**5. Build and Deployment Guides** — MSBuild config, MSIX packaging, code signing, CI/CD on Windows runners. Missing guides cause broken releases and failed submissions. Agents need declarative build specs they can execute directly.

## Human-Agent Documentation Considerations

1. **Platform metadata must be explicit.** Tag every code block and command with target platform. Agents default to Unix conventions — Windows devs suffer when `~/` appears where `%USERPROFILE%\` belongs.

2. **Use conditional rendering, not separate silos.** Single-source docs with platform-conditional sections let agents extract the Windows path without parsing separate documents.

3. **Mandate platform-aware doc linting.** Agents generating Windows content must use backslash paths and PowerShell syntax. Enforce this with automated rules.

## Documentation Anti-Patterns

1. **Unix-Only Defaults** — Only bash commands and forward-slash paths, with "Windows users: figure it out."
2. **The Platform Afterthought Tab** — macOS quickstart hastily adapted by swapping `brew` for `choco` without verifying the Windows workflow differs structurally.
3. **Hardcoded Paths Without Variables** — Using `/usr/local/bin` without `%PROGRAMFILES%` equivalents.
4. **Screenshot-Only Instructions** — macOS UI screenshots with no Windows equivalent.

## My Position for the Docstitution

Windows remains the most widely used desktop OS for development, yet docs routinely treat it as second-class. I have watched ten years of quickstarts that begin with `brew install` and end with a parenthetical "On Windows, try the installer." The Docstitution must mandate that any platform in the support matrix receives first-class documentation: dedicated quickstarts, native samples, and instructions respecting platform conventions.

This is also an agent accuracy issue. Agents trained on Unix-centric docs generate Unix-centric output unless explicitly given Windows alternatives with proper metadata. The Docstitution must require platform annotations on code samples and platform-specific setup variants. A doc claiming cross-platform support but demonstrating only one platform makes a promise it doesn't keep.

I hold a balanced perspective: not asking Windows to dominate, only to receive equal treatment. Platform parity is tractable — conditional content blocks, platform tags, and platform-aware linting solve it.
