# Prime Terminal — PT0 Self-Audit Handoff

## Recovery authority

This branch is a **checkpoint only**. It is not frozen and must not be merged to `main` until the self-audit reaches a full fresh pass with no new material finding and independent freeze review returns 0 BLOCKER / 0 MAJOR.

- Repository: `jaydumisuni/Prime-Terminal`
- Baseline `main`: `a58628a9b22dc62d5c2475534964648e39323303`
- Checkpoint branch: `checkpoint/pt0-self-audit`
- Current exact full checkpoint: **v161**
- SHA-256: `5e1033f5f4bb44f7f24354294054a5482dea69002862aa92e106457e200d1acb`
- Library path: `/Prime-Terminal/ROADMAP-pre-freeze-v161.md`
- Library file id: `file_00000000748c8208bc159275aeb8a4dd`
- Structural checkpoint: 100 contracts / 100 unique; 0 broken numbered contract refs; PT0 outcome registry ↔ phase gate 89/89 exact parity.
- PT0 status: **UNFROZEN**
- `main` must remain untouched while this audit continues.

## Current authority

A new chat must recover this handoff and the exact v161 Markdown before reasoning. Do **not** restart from the small roadmap on `main`, and do not reconstruct the candidate from summaries when the exact Library file is available.

## Latest closures

- v159: `Development Session Restore / Attachment Authority v1` + `PT4 Feature Claim Matrix v1` prevent PT4 prose/session/transport claims from passing without required proof.
- v160: `Interpreter Chain Consumption Binding v1` prevents `/usr/bin/env`-class or other resolver chains from turning a predicted lookup into trusted consumed-interpreter evidence; chain collapse requires semantic-equivalence proof.
- v161: Canonical Result Delivery contract propagation is explicit: Execution Requirement binds result constraints; Route Decision binds selected delivery/finalization/continuation envelope; Attempt Journal binds the pre-dispatch result contract and appends result/snapshot/materialization truth as it becomes knowable; Receipt remains final truth. Delivery/finalization/envelope changes before dispatch invalidate stale admission.

## Current audit frontier

No targeted finding is assumed to be the last. Continue a fresh adversarial audit across:

1. Requirement → Route Decision → Journal → Receipt field parity for every late-added contract;
2. lifecycle/crash/reboot/reattach interactions created by later corrections;
3. provider/data-boundary/consent/recording/idempotency interactions;
4. direct executable, script, runtime bootstrap, process-launch and actual-consumption boundaries;
5. canonical result completeness/paging/finalization/continuation effects;
6. PT1/PT1.5 physical-proof parity with real Prime P1 authority capabilities;
7. PT2/PT3/PT3.5/PT4/PT5 dependencies and non-vacuous exit gates;
8. stale/discretionary wording, typed-outcome registry parity and security-negative coverage.

## Continuation procedure

1. Recover exact v161 and verify its SHA-256.
2. Make corrections locally/workspace-first and advance the candidate version for each material correction batch.
3. Persist each checkpoint to `/Prime-Terminal/ROADMAP-pre-freeze-vNNN.md` and update this handoff.
4. Keep structural checks green: unique contract numbering, zero broken contract refs, outcome-registry ↔ phase-gate parity, dependency-row ↔ readable-dependency parity and proof-gate coverage.
5. After the final correction, run a fresh beginning-to-end adversarial read from contract 1 through PT5—not merely a targeted scan of recent edits.
6. Self-audit stops only when that fresh pass yields **no new material BLOCKER/MAJOR-level contract, authority, lifecycle, dependency, evidence, proof-gate or security finding**.
7. Only then hand the exact candidate to the independent reviewer.
8. Freeze/merge only after independent review returns 0 BLOCKER / 0 MAJOR and accepted findings are corrected/re-reviewed.

## Repository safety

Do not overwrite `main` from this checkpoint branch. This branch exists so any later chat can recover the exact audit state even if the current conversation is lost.
