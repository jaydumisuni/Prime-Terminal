# Prime Terminal — PT0 Self-Audit Handoff

## Recovery authority

This branch is a **checkpoint only**. It is not frozen and must not be merged to `main` until the self-audit reaches a full fresh pass with no new material finding and independent freeze review returns 0 BLOCKER / 0 MAJOR.

- Repository: `jaydumisuni/Prime-Terminal`
- Baseline `main`: `a58628a9b22dc62d5c2475534964648e39323303`
- Checkpoint branch: `checkpoint/pt0-self-audit`
- Current exact full checkpoint: **v160**
- SHA-256: `f8497ff4fc4b52cc3a24bdb6584bf3d8b514e3d661570e4710a59619c7f0b624`
- PT0 status: **UNFROZEN**
- `main` must remain untouched while this audit continues.

## Full-roadmap recovery

The exact v160 Markdown is persisted in the ChatGPT Library at:

`/Prime-Terminal/ROADMAP-pre-freeze-v160.md`

Library file id at checkpoint time: `file_0000000018448207b5a943147e530d88`

A new chat must recover this handoff and the exact v160 file before reasoning. Do **not** restart from the small roadmap on `main` and do not reconstruct the candidate from summaries when the exact file is available.

## What v159/v160 closed

- v159: PT4 user-facing prose claims were made mechanically accountable through `Development Session Restore / Attachment Authority v1` and `PT4 Feature Claim Matrix v1`; PT4 cannot pass while claimed restore/attachment/session features remain unproven.
- v160: `/usr/bin/env`-class and other script resolver/interpreter chains gained `Interpreter Chain Consumption Binding v1`; a predicted PATH lookup cannot be recorded as the interpreter actually consumed, and chain collapse is allowed only with semantic-equivalence proof.

## Current audit frontier

The next confirmed unresolved item is **Canonical Result Delivery field propagation**: contract 10G states that result-delivery mode, budgets, finalization/materialization state and continuation-effect envelope are evidence-bound, but v160 still does not carry the complete contract through Execution Requirement → Route Decision → Attempt Journal. Receipt already contains more of it. Close this propagation first, then continue a fresh adversarial read rather than assuming only this remains.

Continue attacking at least:

1. Requirement → Route Decision → Journal → Receipt field parity for every late-added contract;
2. lifecycle/crash/reboot/reattach interactions created by later corrections;
3. provider/data-boundary/consent/recording/idempotency interactions;
4. direct executable, script, runtime bootstrap and process-launch actual-consumption boundaries;
5. canonical result completeness/paging/finalization and continuation effects;
6. PT1/PT1.5 physical-proof parity with the real Prime P1 authority capabilities;
7. PT2/PT3/PT3.5/PT4/PT5 dependency and non-vacuous exit gates;
8. stale/discretionary wording, outcome-registry parity and security-negative coverage.

Do **not** assume these are the only remaining issues.

## Continuation procedure

1. Recover exact v160 and verify the SHA-256.
2. Make corrections locally/workspace-first; advance the candidate version for every material correction batch.
3. Persist the new full candidate to `/Prime-Terminal/ROADMAP-pre-freeze-vNNN.md` and update this handoff after each checkpoint.
4. Maintain structural checks: unique contract numbering, zero broken contract refs, authoritative outcome-registry ↔ PT0 phase-gate parity, dependency-row ↔ readable-dependency parity, and proof-gate coverage.
5. After the last correction, run a fresh beginning-to-end adversarial pass from contract 1 through PT5—not a targeted scan of the latest edits.
6. Self-audit stops only when that fresh pass yields **no new material BLOCKER/MAJOR-level contract, authority, lifecycle, dependency, evidence, proof-gate or security finding**.
7. Only then hand the exact candidate to the independent reviewer.
8. Freeze/merge only after independent review returns 0 BLOCKER / 0 MAJOR and accepted findings are corrected/re-reviewed.

## Repository safety

Do not overwrite `main` from this checkpoint branch. This branch exists so any later chat can recover the exact audit state even if the current conversation is lost.
