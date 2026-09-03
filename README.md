# Interview OS Game

Interview OS Game is a personal, non-commercial mobile learning game for technical interview preparation.

The first product slice targets **mid-level Applied AI engineering**: LLM applications, RAG, evaluation, production trade-offs, and AI system-design reasoning. DSA, ML fundamentals, and general system design remain planned tracks rather than V0 implementation scope.

## Product loop

```text
scenario/question
  -> make a decision
  -> explain why
  -> optionally use terminology help or progressive hints
  -> deterministic + rubric-constrained evaluation
  -> see system consequence / feedback
  -> gain game progression
  -> preserve learning evidence
  -> encounter a changed-surface follow-up
```

The goal is not a four-choice trivia clone. Missions should feel like small engineering incidents, design decisions, debugging situations, and eventually bounded executable labs.

## V0 boundary

V0 intentionally proves the small learning/game loop first:

- Applied AI/RAG vertical slice;
- approximately 15 curated missions;
- tappable technical terminology;
- progressive hints with assistance provenance;
- short typed `why?` reasoning;
- deterministic answer/rubric structure;
- constrained LLM reasoning interpretation;
- simple game progression separated from mastery;
- one bounded dataset-backed RAG mission;
- Study OS-compatible learning-evidence output;
- Expo/React Native cross-platform UI spike.

The general run bench, arbitrary code execution, broad DSA/ML/SYS curriculum, public-user infrastructure, and distributed-system simulation are deferred.

## Projectization

This repository is being projectized with `Pukujan/project-assurance-modules`, pinned in `PROJECT_ASSURANCE.json`.

Start with:

- `docs/PAM_PREFLIGHT.md` — routed methodology and gap report;
- `docs/PDD.md` — product definition;
- `docs/SCOPE_BOUNDARY.md` — current claims, non-goals, and admission rule;
- `docs/BUILD_VS_REUSE.md` — reuse/build decisions;
- `docs/SDD.md` — system/ownership boundary;
- `docs/INVARIANTS.md` — properties that must remain true;
- `docs/FAILURE_REGISTER.md` — material failure modes;
- `docs/BENCHMARK_POLICY.md` — dataset/hidden-evaluation integrity;
- `docs/DECISIONS.md` — consequential decision lineage;
- `HANDOFF_STATE.json` — current resumable project state.

PAM is project methodology, not a runtime dependency.

## Relationship to Study OS

`Pukujan/Study-os` remains the preferred longitudinal learner-evidence/capability authority. Interview OS owns gameplay, missions, presentation, product-specific evaluation integration, and game progression. It should emit compatible evidence rather than create a second canonical mastery engine.

## Current execution order

1. Review/close PAM preflight (#1 / PR #7).
2. Define versioned mission/content/evidence contracts (#2).
3. Build the first Applied AI/RAG vertical slice (#3).
4. Establish the concrete dataset/hidden-eval implementation (#4).
5. Freeze the Study OS integration adapter (#5).
6. Develop the visual/game language against the working mission loop (#6).

Do not broaden implementation merely because a deferred mechanism is technically interesting.
