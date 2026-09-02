# Interview OS Agent Rules

## Authority

Live GitHub repository/issue/PR/CI state wins over stale handoff text. Reconcile referenced live objects before mutation after a material session break or agent transfer.

## Current projectization boundary

Before implementation expands, read:

- `PROJECT_ASSURANCE.json`;
- `HANDOFF_STATE.json`;
- `docs/PDD.md`;
- `docs/SCOPE_BOUNDARY.md`;
- `docs/BUILD_VS_REUSE.md`;
- `docs/SDD.md`;
- `docs/INVARIANTS.md`;
- `docs/FAILURE_REGISTER.md`;
- `docs/BENCHMARK_POLICY.md`;
- `docs/DECISIONS.md`.

Do not start deferred mechanisms merely because they appear attractive or feasible.

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

## Ownership

- Interview OS owns gameplay/application behavior.
- Study OS is the preferred longitudinal learner-evidence/capability authority.
- PAM is methodology/projectization, not a game runtime dependency.
