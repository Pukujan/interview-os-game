# PAM Preflight — Interview OS Game

Status: **ready for owner review; implementation-phase gaps remain open**

Methodology revision: `Pukujan/project-assurance-modules@0e62c3e7cbb90e9242103238829bbf0cc2f94917`

Active projectization issue: #1

Preflight PR: #7

## Project facts

```json
{
  "software": true,
  "projectization": true,
  "nontrivial": true,
  "empirical_quality_claims": true,
  "benchmark_or_dataset_use": true,
  "hidden_confirmatory_evaluation": true,
  "consequential_decisions": true,
  "durable_provenance_and_decision_lineage": true,
  "multi_session": true,
  "agent_assisted": true
}
```

## Selected profiles

- `projectization.software@0.1.0`
- `benchmark.empirical-work@0.1.0`
- `provenance.material-decisions@0.1.0`
- `continuity.material-work@0.1.0`

## Routed modules

| Module | Disposition | Why |
|---|---|---|
| `projectization.build-vs-reuse@0.1.0` | required | Existing systems/frameworks plausibly satisfy learner-state, methodology, and cross-platform app infrastructure needs. |
| `projectization.scope-boundary@0.1.0` | required | The idea has major horizontal expansion risk across quiz, simulation, datasets, DSA, ML, system design, AI evaluation, and mobile infrastructure. |
| `planning.foundation@0.1.0` | required | Product outcome, architecture, invariants, and failures must be frozen before implementation backlog growth. |
| `engineering.swe-ci-foundation@0.1.0` | required | This is maintained software; reproducible checks/CI are required as implementation begins. |
| `benchmark.integrity@0.1.0` | required | Dataset-backed missions, derived LLM evaluation, transfer items, and some hidden evaluation are intentional product features. |
| `provenance.decision-lineage@0.1.0` | required | Scope/reuse/evaluator/dataset/ownership decisions must remain replayable across sessions. |
| `continuity.structured-handoff@0.1.0` | required | The work is multi-session and agent-assisted. |

## Decisions frozen by the preflight

1. **V0 is Applied AI/RAG first.**
2. **V0 proves the small learning/game loop before the simulator vision.**
3. **General run bench is deferred.** One bounded dataset-backed RAG adapter is allowed.
4. **Study OS is reused for learner-evidence/capability semantics.** Interview OS does not become a second canonical mastery engine.
5. **PAM remains methodology, not runtime.**
6. **Expo + React Native + TypeScript is selected for the first UI spike**, conditional on representative visual/interaction validation.
7. **The LLM interprets reasoning under a rubric; it does not override deterministic/dataset reality.**
8. **XP/levels/streaks are game progression, not mastery evidence.**
9. **Hidden evaluation is used only where the claim benefits from it; practice exposure is permanent provenance.**
10. **Source provenance is preserved even for personal/non-commercial imported study material.**

## Planning foundation closed

The following projectization artifacts now exist:

- `docs/BUILD_VS_REUSE.md`
- `docs/SCOPE_BOUNDARY.md`
- `docs/PDD.md`
- `docs/SDD.md`
- `docs/INVARIANTS.md`
- `docs/FAILURE_REGISTER.md`
- `docs/BENCHMARK_POLICY.md`
- `docs/DECISIONS.md`
- `PROJECT_ASSURANCE.json`
- `AGENTS.md`
- `HANDOFF_STATE.json`

## V0 product boundary

First playable slice: approximately fifteen high-quality Applied AI/RAG missions spanning terminology/intuition, architecture decisions, diagnosis, one bounded dataset-backed mission, and one multi-stage boss mission.

The core interaction is:

```text
scenario/question
  -> decision
  -> short "why?"
  -> optional terminology/help
  -> deterministic + rubric-constrained evaluation
  -> consequence/feedback
  -> game progression
  -> learning evidence
  -> changed-surface follow-up
```

## Deliberately open PAM gaps

These are **not** projectization failures; they are the next executable evidence obligations and remain open in `PROJECT_ASSURANCE.json`.

### Build-vs-reuse

- run the representative Expo/React Native interaction spike;
- owner review/accept the implementation disposition.

### Software/CI

- establish the actual app's local lint/type/test lane;
- add executable software tests after contracts/code exist;
- keep mutable LLM/dataset integrations outside deterministic PR correctness checks where appropriate;
- obtain passing CI evidence.

An assurance-only workflow has been added to validate the PAM manifest/handoff while product code is still absent.

### Benchmark integrity

- pin the exact first RAG fixture/dataset/protocol identity;
- implement hidden-material packaging/leakage checks;
- define the retained result artifact contract;
- produce one replayable dataset-backed result.

### Provenance

- pin exact component/source identities for all admitted decisions that depend on mutable external state;
- record explicit project-owner acceptance/rejection/supersession through normal review.

### Continuity

- execute the pinned PAM validators against `PROJECT_ASSURANCE.json` and `HANDOFF_STATE.json` in CI/local environment;
- once green, update the manifest with exact validation evidence.

## Scope that must not enter V0 without a recorded re-scope

- general-purpose RAG/run-bench platform;
- arbitrary code execution sandbox;
- distributed-systems simulator;
- broad DSA/ML/general system-design curriculum;
- public accounts/social/multiplayer;
- separate SwiftUI and Android-native clients;
- generic curriculum/mastery engine duplicating Study OS.

## Next project action

Review PR #7 as the project-owner preflight gate. If the frozen product/scope/reuse decisions are accepted, run/observe the assurance validator, close the resulting manifest/handoff validation gaps, and then execute issue #2 (mission/content contracts) before issue #3 (first playable Applied AI/RAG slice).
