# Prime Terminal — Roadmap

**Repository:** `jaydumisuni/Prime-Terminal`
**Product:** Prime Terminal
**Authority:** THETECHGUY DIGITAL SOLUTIONS / Prime OS architecture
**Roadmap baseline:** 2026-09-05
**Status:** AUTHORITATIVE INITIAL ROADMAP

## Purpose

Prime Terminal is Prime OS's first-party terminal and universal command surface.

Its defining rule is:

> **You choose the command language. Prime chooses the execution backend.**

A Prime user should not have to remember whether an everyday operation is expressed using Linux/Bash vocabulary, Windows CMD vocabulary, PowerShell cmdlets or macOS-style commands before the terminal becomes useful. Where different dialects express the same operation, Prime Terminal normalizes them into one canonical Prime operation. Where semantics genuinely depend on a specific platform/runtime, Prime Terminal routes through Prime Exec to the appropriate available backend or reports the missing backend truthfully.

Prime Terminal is not "Bash with aliases" and it is not an AI prompt pretending to be a shell.

## Permanent architecture boundary

- Prime Terminal owns terminal presentation, interactive sessions, command parsing, dialect recognition, canonical command normalization and execution UX.
- Prime OS / Prime Core owns Host authority, Prime Exec, Workload Policy, runtime/backend availability, privileged capabilities and secure execution admission.
- Prime Terminal may execute ordinary native user workloads through an admitted terminal profile, but it must not invent a generic privileged shell mutation API inside Prime Core.
- Privileged/system actions must resolve through explicit Prime capabilities and authorization, not through hidden `sudo`, distro-specific helpers or UI-side privilege escalation.
- Dialect translation must be deterministic for supported command families.
- Hunter/AI may assist later, but AI output is never the execution authority.
- Unsupported platform semantics must fail explicitly instead of being approximated silently.

## Command classes

Prime Terminal distinguishes three classes of input:

1. **Canonical-overlap operations** — different dialects express the same useful operation and can map to one deterministic Prime semantic action.
2. **Native shell/runtime commands** — syntax belongs to an installed runtime such as POSIX shell or PowerShell and should execute through that runtime under Prime Exec/Workload Policy.
3. **Platform-specific operations** — the command requires Windows, Darwin/macOS, Android, JVM or another backend. Prime Terminal routes to an available backend or reports the exact missing capability.

Recognition is not execution permission. Prime Exec and Workload Policy remain authoritative.

---

# PT0 — Universal Command Contract

**Goal:** freeze what "one terminal that accepts different command languages" actually means before implementation accumulates ad-hoc aliases.

## Required contracts

- Prime Terminal Command v1 input model.
- Dialect Classification v1.
- Canonical Operation v1.
- Backend Selection v1.
- Command Result/Evidence v1.
- path normalization rules.
- quoting/escaping rules for supported dialects.
- pipeline/redirection ownership boundary.
- environment-variable semantics.
- working-directory semantics.
- ambiguity handling.
- explicit unsupported/missing-backend states.
- authorization boundary for system mutations.

## Initial dialect vocabulary

PT0 must explicitly define recognition for:

- POSIX/Linux shell vocabulary;
- Windows CMD vocabulary;
- PowerShell cmdlet vocabulary;
- common macOS command vocabulary where it overlaps POSIX or maps to a canonical Prime operation.

This is syntax/dialect recognition, not a claim that Prime locally implements every Windows or macOS API.

## Initial canonical operation families

At minimum:

- filesystem list;
- current directory / directory change;
- file read;
- copy;
- move/rename;
- remove;
- make directory;
- process list;
- clear terminal;
- open file/URL/resource;
- environment read/write for the active terminal session;
- command discovery/help.

Representative equivalences include:

| Prime semantic | POSIX/macOS | CMD | PowerShell |
| --- | --- | --- | --- |
| list directory | `ls` | `dir` | `Get-ChildItem` |
| read file | `cat file` | `type file` | `Get-Content file` |
| copy | `cp a b` | `copy a b` | `Copy-Item a b` |
| move | `mv a b` | `move a b` | `Move-Item a b` |
| remove | `rm a` | `del a` | `Remove-Item a` |
| processes | `ps` | `tasklist` | `Get-Process` |
| clear | `clear` | `cls` | `Clear-Host` |
| open resource | `xdg-open x` / `open x` | `start x` | `Start-Process x` |

The table defines intent equivalence only where semantics are compatible. Flags/options are not silently mistranslated unless PT0 defines them.

## Ambiguity rule

When input has more than one materially different valid meaning, Prime Terminal must either:

- resolve it mechanically from known syntax/session context; or
- ask/show a concise disambiguation before execution.

It must not guess destructively.

## Exit gate

PT0 exits when the supported command families, dialect rules, canonical operation model, backend-selection behavior and failure semantics are versioned and testable without an AI model.

---

# PT1 — Terminal First Light

**Goal:** deliver a premium native Prime terminal that is useful on the first daily-usable Prime installation.

## Terminal fundamentals

- native Prime application profile.
- PTY-backed interactive sessions.
- tabs or equivalent multi-session workflow.
- reliable scrollback.
- keyboard selection/copy/paste.
- Unicode input/output.
- resize propagation.
- current working directory.
- environment variables.
- exit status reporting.
- signals/interrupt handling.
- bounded shell/process lifetime cleanup.
- session title/cwd awareness.
- Prime visual language consistent with the approved Shell without copying another terminal product.

## Execution baseline

- ordinary Linux-native commands can run under the admitted terminal workload policy.
- canonical PT0 operations work regardless of which supported dialect spelling is used.
- command results make the selected execution route inspectable when useful without forcing backend management onto ordinary users.
- unsupported platform-specific commands produce truthful capability errors.

## Required PT1 examples

A single Prime Terminal installation must accept, without manual mode switching:

```text
ls
dir
Get-ChildItem
```

and map all three to the same directory-list intent where no dialect-specific option changes semantics.

Likewise:

```text
ps
tasklist
Get-Process
```

must provide the same canonical process-list intent at the baseline semantic level.

PT1 must not pretend full PowerShell pipeline semantics or Windows command processor behavior merely because these common commands are recognized.

## Exit gate

Prime Terminal launches from Home as a real application, supports stable interactive PTY use, implements every PT0 initial canonical family, and has no static/proof-only command cards.

---

# PT1.5 — Cross-Dialect Physical Proof

**Goal:** prove the Prime Terminal promise on KRATOS instead of accepting parser unit tests as sufficient evidence.

## Required physical proof

In one terminal installation and without manual dialect mode switching:

- `ls`, `dir`, `Get-ChildItem` produce equivalent canonical directory results.
- `cat`, `type`, `Get-Content` read the same test file truthfully.
- `cp`, `copy`, `Copy-Item` produce equivalent bounded copy results.
- `mv`, `move`, `Move-Item` produce equivalent bounded move results.
- `rm`, `del`, `Remove-Item` produce equivalent bounded removal results with safety rules preserved.
- `ps`, `tasklist`, `Get-Process` produce equivalent canonical process observations.
- `clear`, `cls`, `Clear-Host` clear the active view.
- `open`, `start`, `Start-Process`/`xdg-open` resolve through the canonical resource-open path where semantics overlap.
- PTY resize, Ctrl-C/interrupt, Unicode, scrollback, copy/paste and nonzero exit codes are mechanically verified.
- an unsupported Windows-only command reports a missing Windows backend instead of executing an unrelated Linux program.
- an unsupported Darwin-only command reports a missing Darwin provider/backend instead of fake success.

## Exit gate

Evidence binds Prime Terminal revision, Prime OS generation, Prime Exec/capability versions and the exact command/result corpus used for proof.

---

# PT2 — Full Command Router

**Goal:** expand universal command handling from the PT1 baseline into a broad deterministic everyday command environment.

## Additional command families

- richer filesystem inspection and metadata.
- search/find operations.
- archives/compression.
- checksums/hashing.
- process inspection/control through appropriate Prime authority.
- network observation.
- environment/session management.
- device observation.
- system information.
- text filtering/transforms where semantics can be normalized safely.
- package/component discovery once Prime's component engine exists.

## Syntax depth

- dialect-aware option parsing.
- pipelines.
- stdin/stdout/stderr redirection.
- quoting/escaping.
- wildcard/glob semantics.
- environment expansion.
- command chaining.
- native-runtime escape/pass-through where an exact dialect runtime is intentionally selected.

Prime Terminal must not force incompatible shell grammars into a lowest-common-denominator parser. Canonical operations cover shared intent; exact language semantics remain owned by the corresponding runtime/parser.

## Exit gate

Supported cross-dialect commands have conformance fixtures proving equivalent canonical outcomes, while non-equivalent flags/syntax remain explicitly dialect-specific.

---

# PT3 — Runtime / Personality Routing

**Goal:** route genuinely platform-specific commands through the correct Prime execution backend.

## Backend model

Examples:

- Linux/POSIX native command → `NATIVE` Linux execution.
- PowerShell syntax → available PowerShell runtime under Prime Exec.
- Windows-only executable/command → Windows Personality, VM or approved Windows Provider according to its Application/Command Profile.
- Darwin/macOS-only command → Darwin/macOS Provider or later local compatibility backend when one is proven.
- JVM tooling → JVM runtime.
- Android tooling/workloads → Android build/runtime capability as appropriate.
- remote-specialized operations → explicit approved Provider.

Prime Terminal shows backend truth when it materially affects behavior, but ordinary commands should not require users to manually orchestrate VMs/providers.

## Required failure states

Examples include:

- `REQUIRES_WINDOWS_BACKEND`;
- `REQUIRES_POWERSHELL_RUNTIME`;
- `REQUIRES_DARWIN_PROVIDER`;
- `REQUIRES_ANDROID_CAPABILITY`;
- `BACKEND_INCOMPATIBLE`;
- `POLICY_DENIED`.

No generic "command not found" should erase a known runtime/capability diagnosis.

## Exit gate

Prime Exec selection is deterministic, policy-bound and evidenced; platform-specific commands never fall back to a different platform implementation silently.

---

# PT4 — Development Terminal

**Goal:** align Prime Terminal with Prime OS P2 Development Body and make it the primary interactive development surface.

## Tooling integration

- Git.
- Rust/Cargo.
- Python.
- C/C++.
- LLVM/Clang and GCC.
- Node/TypeScript.
- JVM tooling.
- .NET.
- Android tooling.
- containers.
- isolated build environments.
- cross-compilers.
- SDK/toolchain selection.
- signing and packaging workflows.
- release-provider workflows.

## Workspace experience

- named/restorable terminal sessions.
- project cwd/session restoration.
- environment/toolchain identity visible per session.
- split panes where justified by observed workflow needs.
- command history with privacy boundaries.
- safe links into Origins/project context without making Origins a prerequisite for basic terminal use.
- remote/provider session identity when commands execute away from the local Host.

## Exit gate

A Prime developer can build the supported P2 language/toolchain targets from Prime Terminal without dropping into a distro desktop or managing runtime plumbing manually.

---

# PT5 — Hunter-Assisted Terminal

**Goal:** add high-value intelligence without replacing deterministic terminal semantics.

Potential capabilities:

- natural-language command drafting.
- explain this command/result.
- translate a command between dialects.
- suggest corrections after deterministic parser/runtime errors.
- compose multi-step workflows for review.
- summarize logs/output.
- surface safer canonical Prime alternatives for risky operations.

## Hard boundary

Hunter may propose a command or canonical operation. Prime Terminal must show the concrete action and the normal parser/Prime Exec/Workload Policy path remains authoritative.

AI cannot silently reinterpret a command after the user submits it, cannot bypass authorization, and cannot convert an unsupported backend into fake success.

## Exit gate

PT5 exits when assisted workflows always resolve to inspectable deterministic commands/canonical operations before execution, authorization remains unchanged, and the same approved action can be replayed without requiring the AI model to reinterpret it.

---

# Prime OS integration

## P1

Prime OS may pin an exact reviewed Prime Terminal artifact into the immutable P1 image together with its Application Profile and workload policy. PT1/PT1.5 are intentionally smaller than the complete P2 developer terminal.

## P2+

Once the Prime component/package mechanism exists, Prime Terminal should normally evolve independently as a signed first-party component. Optional runtimes/toolchains are delivered through Prime's component/capability architecture, not permanently stuffed into the base image merely because Terminal can invoke them.

# Security and safety rules

- No hidden `sudo` compatibility layer.
- No terminal-specific bypass around Prime Workload Policy.
- No implicit privilege merely because a command spelling came from PowerShell or CMD.
- No AI-only interpretation for supported deterministic commands.
- No silent cross-platform fallback.
- Destructive canonical operations preserve or strengthen the safety semantics of the underlying Prime capability/runtime.
- Secrets in command history, evidence and AI-assisted flows require explicit redaction/storage policy.

# Non-goals

Prime Terminal is not:

- Bash with a skin;
- PowerShell reimplemented badly in Rust;
- a complete CMD clone;
- a macOS compatibility layer;
- an AI chat window with command execution;
- a replacement for Prime Exec;
- an unrestricted root shell API exposed by Prime Core.

# Completion definition

Prime Terminal reaches its first production baseline when PT0, PT1 and PT1.5 are complete on an installed Prime generation and the universal-command claim is backed by a reproducible cross-dialect evidence corpus.

The permanent product promise remains:

> The user chooses the command language. Prime determines the truthful semantic operation and execution backend.
