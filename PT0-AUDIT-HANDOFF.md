# Prime Terminal — PT0 Self-Audit Handoff

## Recovery authority

This branch is a **checkpoint only**. It is not the frozen roadmap and must not be merged to `main` until the self-audit reaches a full fresh pass with no new material finding and the independent freeze review returns 0 BLOCKER / 0 MAJOR.

- Repository: `jaydumisuni/Prime-Terminal`
- Baseline `main`: `a58628a9b22dc62d5c2475534964648e39323303`
- Checkpoint branch: `checkpoint/pt0-self-audit`
- Current full checkpoint: **v158**
- Current full-roadmap SHA-256: `f755b979a940a776c021dec29ddc40e18cf5cd69197b001fffa9b213a2ec93e3`
- GitHub `main` remains untouched.
- PT0 status: **UNFROZEN**.

## Full checkpoint recovery

The exact v158 Markdown is also persisted in the ChatGPT Library at:

`/Prime-Terminal/ROADMAP-pre-freeze-v158.md`

Library file id at checkpoint time: `file_00000000ca048211a734ec5265d91f63`

If this chat is lost, a new chat should recover this handoff first, then recover the exact full roadmap checkpoint before reasoning. Do not restart from the small `main` ROADMAP.

## Audit state

The self-audit has progressed far beyond the repository baseline. The current contract set includes, among other things:

- Prime Prompt input/session ownership and immutable submission context;
- cross-dialect lexical equivalence and frozen Prime grammar;
- canonical operation signatures, applicability and exact-runtime fallback;
- direct executable argument/resource semantics;
- executable object/content-generation launch binding;
- Process Launch Context / ambient-inheritance isolation;
- Runtime Bootstrap/startup-hook admission;
- stateful runtime command-boundary/result framing;
- Resource Identity Stability and approved projections;
- session-context/environment projection and cross-boundary environment disclosure;
- secret materialization + durable cleanup continuation;
- route prerequisites + residual cleanup;
- route candidate selection/ambiguity/effect dominance;
- authenticated backend/provider/channel identity;
- route-inherent effect/data-boundary semantics;
- cross-boundary consent, including live consent leases and cleanup continuation;
- dispatch/control idempotency and uncertainty semantics;
- Host-reboot durable Attempt Journal/recovery;
- late-result reconciliation and historical result-decoder continuity;
- canonical result delivery/pagination/finalization;
- process/runtime termination reporting;
- foreground/background workload containment and Background I/O ownership;
- terminal input/output/VT/escape/query-response security;
- foreground input/output recording and notification privacy;
- dynamic discovery evidence, rate/cost budgets, principal/session isolation and external-effect ledger;
- semantic profile trust/applicability + isolated evaluator execution;
- PT1.5 physical Core/authority-boundary proof requirements;
- PT4 diagnostic/file-hint, signing/release, background metadata and tunnel authority;
- PT5 assisted-plan, AI context/model boundary, external AI accounting and safe AI-response presentation;
- versioned replay/migration rather than re-executing retired contracts.

## Latest audit direction

Immediately before this checkpoint request, the active audit was continuing from v158 and had identified the next areas to keep attacking:

1. field propagation across Execution Requirement → Route Decision → Attempt Journal → Receipt;
2. PT4 feature-to-proof-matrix coverage so prose features cannot pass unproven;
3. script interpreter-chain actual-consumption binding;
4. canonical result delivery/finalization evidence propagation;
5. cross-contract lifecycle/recovery contradictions introduced by later corrections;
6. dependency/phase exit gates and non-vacuous proof requirements;
7. stale/discretionary wording and security-negative parity.

Do **not** assume these are the only remaining issues. Run a fresh beginning-to-end adversarial pass.

## Required continuation procedure

1. Recover this branch/handoff and the exact v158 full roadmap.
2. Verify the SHA-256 before editing.
3. Continue the self-audit locally/workspace-first; do not freeze merely because a prior pass looked clean.
4. After each material correction, advance the candidate version and update this handoff/checkpoint.
5. Run structural checks: unique contract numbering, broken contract references, outcome-registry ↔ phase-gate parity, dependency-row ↔ readable-dependency parity, and proof-gate coverage.
6. Run an independent fresh adversarial read from the beginning after the last correction.
7. Stop self-audit only when that full fresh pass yields **no new material BLOCKER/MAJOR-level contract, authority, lifecycle, dependency, evidence, proof-gate or security finding**.
8. Only then hand the exact candidate to the independent reviewer.
9. Freeze/merge only after independent review returns 0 BLOCKER / 0 MAJOR and all accepted findings are incorporated/re-reviewed.

## Repository safety

Do not overwrite `main` from this checkpoint branch. This branch exists so another chat can recover the work if the current conversation is lost.
