# Interview OS Agent Rules

## Authority

Live GitHub repository/issue/PR/CI state wins over stale handoff or planning text. Reconcile referenced live objects before mutation after a material session break or agent transfer.

## Current projectization boundary

Interview OS is being reprojectized under PAM revision `03fc55ae4036a9704cdb929fb3ae6dc520ae2183` because PAM issue #10 invalidated the closure semantics used by the original v0.1 build-vs-reuse preflight.

Current authority order:

1. live GitHub state for issue #8 / branch `pam-v0.2-reprojectization`;
2. `PROJECT_ASSURANCE.json`;
3. `HANDOFF_STATE.json`;
4. `assurance/RESEARCH_HANDOFF.md`;
5. `assurance/REUSE_ASSESSMENT.json`;
6. only then any newly regenerated scope/planning artifacts.

The following v0.1 files remain historical until explicitly regenerated under issue #8 and referenced as satisfied evidence by the current manifest:

- `docs/BUILD_VS_REUSE.md`;
- `docs/SCOPE_BOUNDARY.md`;
- `docs/PDD.md`;
- `docs/SDD.md`;
- `docs/INVARIANTS.md`;
- `docs/FAILURE_REGISTER.md`;
- `docs/BENCHMARK_POLICY.md`;
- `docs/DECISIONS.md`.

Do not infer authorization from the presence of those files. Old issues #1 through #6 are superseded and must not be executed as implementation backlog.

## Projectization gate

Do not create product/runtime code or a broad implementation backlog while `REUSE_008` is pending.

The current reuse assessment is a draft technical disposition. Project-owner review is required before it becomes the reviewed implementation disposition. After review, re-derive scope, routing gaps, planning foundation, benchmark obligations, and only then implementation issues.

## Handoff triggers

`HANDOFF_STATE.json` is the replaceable current resumable state packet.

Update it for material:

- session/agent responsibility transfer;
- active issue or PR transition;
- validation phase transition;
- blocker or next-action change;
- material plan/scope change.

Do not update it for every trivial edit.

Historical checkpoints are optional. When a milestone needs a durable historical checkpoint, copy the validated state into an append-only `docs/handoffs/` record rather than presenting an old checkpoint as current state.

## Hidden-evaluation boundary

Never place confirmatory/hidden question answers, dataset labels, seeds, private evaluator material, or protected transfer items in agent-visible handoff state.

## Learning/evaluation integrity

- Do not treat XP/streaks as mastery.
- Preserve assistance provenance.
- Do not relabel exposed practice material as unseen transfer evidence.
- Keep deterministic/dataset evidence separate from LLM-derived reasoning judgments.
- Unknown mission/evaluator/dataset versions fail closed rather than being guessed compatible.

## Ownership hypotheses pending reviewed scope

- Interview OS is expected to own gameplay/application behavior only to the extent the reviewed reuse decision leaves that capability uncovered.
- Study OS is the leading candidate for longitudinal learner-evidence/capability-state composition; exact ownership remains subject to contract inspection and reviewed scope.
- Design Bakery is an internal visual-language/content reference, not a runtime dependency by default.
- PAM is methodology/projectization, never a gameplay/runtime product dependency.
