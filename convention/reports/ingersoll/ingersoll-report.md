# Delegate Report: Ingersoll
**Role:** C++ Developer | **Experience:** 20 years | **Perspective:** Balanced

## Essential Document Types

**Code-Level Safety Documentation**
- **Ownership & Lifetime Annotations** — Doxygen comments making explicit which entity owns each dynamically allocated resource.
- **Thread Safety Contracts** — Per-class documentation specifying concurrency guarantees and locking requirements.
- **Exception Safety Guarantees** — Per-function documentation stating no-throw, strong, or basic guarantee level.
- **Doxygen API Reference** — Structured documentation covering public symbols' preconditions and invariants.

**Build & Toolchain Documentation**
- **Build System Documentation** — Annotated CMake or Bazel files explaining targets, flags, and cross-compilation.
- **Toolchain Requirements** — Minimum compiler versions, C++ standard, and platform SDK requirements.
- **Third-Party Dependency Documentation** — External libraries with linkage type, license, and ABI notes.

**Systems Documentation**
- **Memory Model Documentation** — Allocation strategy, custom allocators, and deallocation responsibilities.
- **Architecture Decision Records (ADRs)** — Decisions emphasizing performance trade-offs and ABI stability.
- **Platform Portability Notes** — Platform-specific behaviors, conditional compilation, and alignment assumptions.

## Documents Most Critical to My Role

1. **Ownership & Lifetime Documentation** — Contains which entity owns each allocation and the deallocation chain. When missing, use-after-free bugs hide for months. Agents must understand ownership — one wrong assumption produces undefined behavior.

2. **Thread Safety Contracts** — Contains concurrency guarantees: internal locking, required mutexes, thread-affinity rules. When undocumented, data races produce crashes months later. Agents without these annotations generate subtly broken concurrent code.

3. **Build System Documentation** — Contains rationale for compiler flags, target graphs, and cross-compilation instructions. When absent, build modifications cost days of trial-and-error. Agents need this for correct CMake configs.

4. **Exception Safety Guarantees** — Contains the guarantee level (no-throw, strong, basic) per function. When missing, code corrupts state on exceptions. Agents need explicit levels for correct RAII patterns.

5. **Memory Model Documentation** — Contains allocation strategy, custom allocator interfaces, and pool configs. When absent, wrong pool usage degrades performance. Agents need this for project-specific allocation constraints.

## Human-Agent Documentation Considerations

- **Use structured Doxygen commands.** Use `@pre`, `@post`, `@threadsafety`, and `@ownership` so agents parse contracts programmatically.
- **Document undefined behavior boundaries.** Every function that can trigger UB must document those inputs — agents cannot infer UB risks from source alone.
- **Maintain a living build guide.** A version-controlled guide mapping sources to targets gives agents context to modify builds safely.

## Documentation Anti-Patterns

1. **The Naked `new`** — Heap allocations with no documented owner — a memory leak waiting to happen.
2. **"Thread-Safe" by Assumption** — Using a class concurrently because no one documented it is *not* thread-safe.
3. **Tribal Build Knowledge** — Builds working only on the original developer's machine due to undocumented flags.
4. **Doxygen Boilerplate Graveyards** — Every field says `@brief The X`. Restating names provides zero value.
5. **Undocumented Platform Assumptions** — Code assuming little-endian or 8-byte pointers without noting it. Silent assumptions become silent bugs.

## My Position for the Docstitution

A missing comment in C++ costs weeks of debugging. In managed languages, undocumented code frustrates; in C++, it endangers. Unclear ownership hides memory corruption. Absent thread safety contracts breed heisenbugs. The Docstitution must recognize that systems programming demands higher documentation standards for safety properties no type system fully encodes.

Agentic AI amplifies both the value and danger. A C++ agent must rely on documentation to avoid undefined behavior — the runtime will not save it. If the Docstitution does not mandate ownership, thread safety, and exception guarantee documentation, it licenses agents to generate code that compiles cleanly and corrupts memory. Every public function must declare these contracts — the minimum both humans and agents need.
