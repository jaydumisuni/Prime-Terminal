# Prime Terminal — PT0 Self-Audit Handoff

## Recovery authority

This branch is a **checkpoint only**. It is not frozen and must not be merged to `main` until the self-audit reaches a full fresh pass with no new material finding and independent freeze review returns 0 BLOCKER / 0 MAJOR.

- Repository: `jaydumisuni/Prime-Terminal`
- Baseline `main`: `a58628a9b22dc62d5c2475534964648e39323303`
- Checkpoint branch: `checkpoint/pt0-self-audit`
- Current exact full checkpoint: **v165**
- SHA-256: `9ee3ca79a465a59ce8e94f76630e6d4a375ebfc1639858a502ffadb65dd1e6d9`
- Library path: `/Prime-Terminal/ROADMAP-pre-freeze-v165.md`
- Library file id: `file_0000000079b48211a4dfa29f45f23453`
- Structural checkpoint: 100 contracts / 100 unique; 0 broken numbered contract refs; PT0 outcome registry ↔ phase gate 90/90 exact parity.
- PT0 status: **UNFROZEN**
- `main` remains untouched.

## Latest material closures

- v159: PT4 session/transport/restore claims are proof-matrix governed; restore/attachment authority is explicit.
- v160: script resolver/interpreter chains bind actual downstream consumption; `/usr/bin/env`-class lookup cannot turn predicted PATH resolution into trusted consumed-interpreter evidence.
- v161: canonical result delivery/finalization/continuation contract propagates Requirement → Route Decision → Journal → Receipt.
- v162: canonical result incompleteness can terminate journal/result truth without false `COMPLETED`; pre-route provider disclosure gained a defined `PREREQUISITE_BOUND_CONSENT` target.
- v163: effectful canonical-result continuations now use either `IN_ATTEMPT_CONTINUATION` with worst-case continuation effects composed into the original Mutation Safety/durability decision, or separately admitted continuation attempts with their own delivery/idempotency evidence.
- v164: unproven interpreter-chain consumption has dedicated typed outcome `SCRIPT_INTERPRETER_CHAIN_UNPROVEN`; chain constraints now originate in Execution Requirement and carry through evidence.
- v165: Data Boundary Consent is explicitly shared by command routes and non-command capability operations; standalone external AI/tunnel/export/reconciliation/continuation actions can use exact `CAPABILITY_OPERATION_BOUND_CONSENT`, which cannot be reused as command-dispatch consent.

## Continuation procedure

1. Recover exact v165 and verify SHA-256 before editing.
2. Continue a **fresh beginning-to-end adversarial audit**, not just the latest contracts.
3. Advance the candidate for each material correction batch; persist `/Prime-Terminal/ROADMAP-pre-freeze-vNNN.md` and update this handoff.
4. Keep structural checks green: unique contract numbering, zero broken contract refs, outcome-registry ↔ PT0 phase-gate parity, dependency-row ↔ readable-dependency parity, and proof-gate coverage.
5. Continue attacking field propagation, crash/recovery/reattach, provider/consent/recording/idempotency, executable/script/runtime actual-consumption, canonical result continuation/finalization, PT1.5 real-authority proof, later-phase dependencies, stale/discretionary wording and security-negative parity.
6. Stop self-audit only when a fresh full pass from contract 1 through PT5 yields **no new material BLOCKER/MAJOR-level contract, authority, lifecycle, dependency, evidence, proof-gate or security finding**.
7. Only then hand the exact candidate to the independent reviewer. Freeze/merge only after independent review returns 0 BLOCKER / 0 MAJOR and accepted findings are corrected/re-reviewed.

## Repository safety

Do not overwrite `main` from this checkpoint branch. The checkpoint exists so any later chat can recover the exact audit state if this conversation is lost.
