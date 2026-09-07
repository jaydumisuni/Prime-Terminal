# Prime Terminal — PT0 Self-Audit Handoff

## Recovery authority

This branch is a **checkpoint only**. It is not frozen and must not be merged to `main` until the self-audit reaches a full fresh pass with no new material finding and independent freeze review returns 0 BLOCKER / 0 MAJOR.

- Repository: `jaydumisuni/Prime-Terminal`
- Baseline `main`: `a58628a9b22dc62d5c2475534964648e39323303`
- Checkpoint branch: `checkpoint/pt0-self-audit`
- Current exact full checkpoint: **v162**
- SHA-256: `8f6a7d5d602fd9cf74f26ff2b1e3dbef56e5cb97e7dc1e30b34b8f28af4ab9ec`
- Library path: `/Prime-Terminal/ROADMAP-pre-freeze-v162.md`
- Library file id: `file_00000000813c8207aea14351886243ce`
- PT0 status: **UNFROZEN**
- `main` must remain untouched while this audit continues.

## Current authority

A new chat must recover this handoff and the exact v162 Markdown before reasoning. Do not restart from the small roadmap on `main`, and do not reconstruct the candidate from summaries when the exact file is available.

## Latest closures

- v159: PT4 claimed session/transport/restore features became proof-matrix governed; restore/attachment authority is explicit.
- v160: script resolver/interpreter chains bind actual downstream consumption semantics; `/usr/bin/env`-class lookup cannot turn a predicted PATH result into trusted consumed-interpreter evidence.
- v161: canonical result constraints/mode/finalization/continuation envelope now propagate Requirement → Route Decision → Journal → Receipt.
- v162: canonical result incompleteness can terminate the journal/result as `RESULT_DATA_LIMIT_EXCEEDED`/`RESULT_DATA_INCOMPLETE` without falsely claiming `COMPLETED`; pre-route data-bearing provider discovery now has a defined `PREREQUISITE_BOUND_CONSENT` + immutable prerequisite consent target rather than referring to an undefined consent mechanism.

## Continuation procedure

1. Recover exact v162 and verify SHA-256.
2. Continue the **fresh beginning-to-end adversarial audit**, not only the latest edits.
3. Advance the candidate for every material correction batch; persist the exact file to `/Prime-Terminal/ROADMAP-pre-freeze-vNNN.md` and update this handoff.
4. Keep structural checks green: unique contract numbering, zero broken numbered refs, authoritative typed-outcome registry ↔ PT0 phase-gate parity, dependency-row ↔ readable-dependency parity, and proof-gate coverage.
5. Continue attacking field propagation, crash/recovery/reattach, provider/consent/recording/idempotency, executable/script/runtime actual-consumption, canonical result continuation/finalization, real PT1.5 authority-boundary proof, later-phase dependencies, stale/discretionary wording and security-negative parity.
6. Self-audit stops only when a fresh full pass from contract 1 through PT5 yields **no new material BLOCKER/MAJOR-level contract, authority, lifecycle, dependency, evidence, proof-gate or security finding**.
7. Only then hand the exact candidate to the independent reviewer. Freeze/merge only after independent review is 0 BLOCKER / 0 MAJOR and accepted findings are corrected/re-reviewed.

## Repository safety

Do not overwrite `main` from this checkpoint branch. This checkpoint exists so any later chat can recover the exact audit state if the current conversation is lost.
