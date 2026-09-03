# V0 Invariants

Status: accepted for preflight

Each invariant must later connect to an executable test, review gate, or explicit residual-risk disposition.

## Learning/evidence invariants

### INV-001 — Game progression is not mastery

XP, streaks, completion counts, and level unlocks may motivate play but cannot be used alone to claim capability, transfer, retention, or interview readiness.

Validation: schema/state separation plus UI/content review.

### INV-002 — Assistance provenance is preserved

An attempt evaluated after a structural hint, scaffold, worked example, or complete solution cannot silently become unaided evidence.

Validation: mission-attempt schema requires assistance events/maximum assistance level; negative tests reject missing provenance for assisted attempts once the schema exists.

### INV-003 — Terminology help does not reveal the solution

A tooltip may define a term and give neutral context but must not recommend the action needed to solve the active mission.

Validation: authored content review plus targeted leakage tests for known answer terms where useful.

### INV-004 — Practice is not unseen transfer

Any item/answer/context exposed during teaching or ordinary practice cannot later be relabeled as an unseen transfer/confirmatory item.

Validation: immutable content visibility class and transfer-family/item identity.

### INV-005 — Derived LLM judgments remain derived

LLM interpretation of reasoning is derived evidence. It cannot be stored or presented as a directly observed learner fact.

Validation: evidence schema distinguishes observed/dataset/deterministic facts from derived rubric interpretation.

## Evaluation invariants

### INV-006 — Deterministic evidence outranks model improvisation

Where a mission has an authored key, executable assertion, dataset metric, or explicit constraint, an LLM cannot silently contradict it.

Validation: scoring combiner tests and adversarial evaluator fixtures.

### INV-007 — Unknown evaluation identity fails closed

Unknown mission versions, rubric versions, dataset revisions, or evaluator schema versions must not be interpreted using a guessed compatible version.

Validation: version-resolution negative tests.

### INV-008 — Empirical claims bind to exact inputs

A dataset-backed result must identify its dataset/fixture, transformation, metric/protocol, and relevant evaluator configuration sufficiently to reproduce the claim.

Validation: benchmark result schema and result-artifact tests.

### INV-009 — Hidden material remains outside normal client bundles

When a mission declares hidden/confirmatory material, the protected answers/labels/items must not be shipped in the ordinary client artifact.

Validation: packaging scan plus targeted semantic review before hidden evaluation matters.

## Ownership invariants

### INV-010 — Interview OS does not become Study OS 2

Interview OS owns gameplay, mission presentation, product-specific evaluation integration, and game progression. Longitudinal learner-capability authority remains in Study OS when integrated.

Validation: architecture/contract review; no new canonical mastery service without an explicit scope decision.

### INV-011 — PAM is not a runtime dependency

PAM guides projectization and assurance. Mobile gameplay/evaluation cannot require PAM services at runtime.

Validation: dependency/build review.

## Product invariants

### INV-012 — V0 works without a general run bench

The first end-to-end product must deliver useful decision/reasoning practice with at most one bounded dataset-backed adapter. A generalized execution/simulation platform is not a prerequisite.

Validation: scope gate and milestone acceptance review.

### INV-013 — Visuals serve an interaction or learning purpose

A significant visual/animation in the mission surface must communicate system state, consequence, hierarchy, progression, or interaction affordance rather than existing only as ornament that obstructs the task.

Validation: design review and phone usability test.

### INV-014 — Offline/local-only attempts are labeled honestly

If the authoritative evaluator is unavailable and a mission falls back to local practice, the result cannot be presented as if hidden/server/dataset evaluation ran successfully.

Validation: explicit attempt evaluation mode and failure-path tests.
