# Prime Terminal — Cookpit Roadmap Completion Handoff

**Repository:** `jaydumisuni/Prime-Terminal`  
**Execution machine:** `KRATOS`  
**Mission type:** roadmap completion only  
**Starting authority:** archived `PRE-PT0 SELF-AUDIT CANDIDATE v231 — UNFROZEN`  
**Snapshot filename:** `Prime-Terminal-ROADMAP-pre-freeze-v231.md`  
**Starting SHA-256:** `b5b09e4333c4f0b8f31d058090a968a99578dafdcced78a627686c9915222364`  
**Canonical `ROADMAP.md`:** unchanged/unfrozen until the freeze gate below is satisfied

## Purpose

This document is the durable handoff contract for transferring Prime Terminal roadmap completion into Cookpit. It does **not** transfer PT0 implementation authority and it does **not** declare v231 freeze-ready.

The exact archived state and continuation rules remain recorded in:

- `PRE_PT0_SELF_AUDIT_CHECKPOINT.md`
- `archive/PRE_PT0_SELF_AUDIT_v231.md`

Cookpit must recover and verify the exact archived v231 digest before creating a successor Review World.

## Cookpit mission

Cookpit's job is to finish the **Prime Terminal roadmap**, not to implement Prime Terminal.

The required loop is:

1. recover v231 and verify the starting SHA-256;
2. create a successor pre-freeze Review World without treating the archive as canonical/frozen;
3. rerun all mechanical checks whose evidence is stale at v231;
4. continue hostile whole-document saturation until a fresh complete pass finds no material BLOCKER or MAJOR defect;
5. produce the exact candidate digest and closure evidence for independent review;
6. obtain an independent review against that exact immutable digest;
7. if the reviewer finds any BLOCKER or MAJOR, return to the repair/self-audit lane, create a new Review World, rerun the affected closure checks and submit the new exact digest for review again;
8. repeat until the exact final Review World receives **0 BLOCKER / 0 MAJOR** and every roadmap freeze gate is satisfied;
9. freeze the roadmap and record the exact final digest/evidence.

Cookpit must not stop merely because a revision is large, mechanically green, archived, or has passed an earlier review. The stopping condition is the roadmap's own freeze condition.

## Required resumed checks

At minimum, the resumed successor must rerun the checks explicitly stale at v231, including:

- numbered-contract count/uniqueness and numbered-reference closure;
- Normalized Outcome Registry role/lifecycle/non-collapse/refinement closure;
- PT0 required outcome/registry parity;
- Derived PT0 Contract / Obligation Census with zero unmapped mandatory obligations and zero UNKNOWN closure items;
- Requirement → Route Decision → Attempt Journal → Receipt evidence-propagation parity for every load-bearing identity/generation introduced by later corrections;
- complete-set/cardinality/absence claims, including claimant, recognizer, policy, prerequisite, resource, route, stream, bootstrap, namespace and workload-member universes;
- authority-generation/freshness/coherence and hidden-world privacy noninterference;
- lifecycle state/transition totality and deterministic primary-outcome selection;
- phase/dependency/proof ownership closure, including implementation-candidate versus proven-active boundaries;
- adversarial falsifiers for every safety/authority-bearing contract whose correctness depends on omission-sensitive evidence.

A green historical result from before v231 normative edits does not satisfy the resumed Review World.

## Review boundary

Self-audit and independent review are different lanes.

Cookpit may perform aggressive internal hostile review, mechanical closure and repairs. That work does **not** count as the independent freeze verdict.

The independent reviewer receives the exact immutable candidate digest and must return its own disposition. Any normative correction after that review creates a new Review World and invalidates the prior freeze verdict for the changed bytes.

Freeze requires:

- mechanical/obligation closure under the final exact candidate;
- **0 BLOCKER / 0 MAJOR** from the independent reviewer against that same exact digest;
- all other freeze gates already defined by the roadmap.

## Hard stop after roadmap freeze

**Cookpit stops when the Prime Terminal roadmap freezes.**

It must **not automatically begin PT0 implementation**.

PT0 implementation is a separate later Cookpit generation/project with a new authority package, implementation scope, proof plan and activation decision. Roadmap freeze is therefore a handoff boundary, not permission to continue into code.

## GitHub / artifact discipline

- Do not treat `archive/PRE_PT0_SELF_AUDIT_v231.md` or `PRE_PT0_SELF_AUDIT_CHECKPOINT.md` as the roadmap itself; they are recovery/checkpoint records.
- Preserve exact successor candidate digests and Review World lineage.
- Do not replace canonical `ROADMAP.md` merely because Cookpit has a new candidate. Replace/freeze canonical roadmap only when the final roadmap freeze gate is satisfied.
- Keep independent-review evidence tied to the exact reviewed digest.
- Archive superseded pre-freeze generations when useful, but archive existence never implies approval.

## Out of scope for this Cookpit mission

The following are explicitly out of scope until a separate post-freeze decision starts a new Cookpit generation:

- PT0 implementation;
- terminal UI/mockup work;
- application coding;
- production routing/provider implementation;
- PT1+ implementation work;
- any claim that Prime Terminal is implemented, production-ready or visually complete.

## Completion record

When Cookpit reaches roadmap freeze, the completion record must identify at least:

- final frozen roadmap filename/ref;
- final SHA-256 / Git commit;
- final Review World identity;
- mechanical closure/census result;
- independent reviewer provenance and exact **0 BLOCKER / 0 MAJOR** verdict;
- explicit statement that Cookpit stopped at roadmap freeze and **PT0 has not automatically started**.
