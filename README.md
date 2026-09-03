# Interview OS Game

Interview OS Game is a personal, non-commercial mobile learning-game concept for technical interview preparation.

## Current status: PAM v0.2 reprojectization

The original Interview OS preflight used `projectization.build-vs-reuse@0.1.0`. That adoption exposed the methodology defect recorded in `Pukujan/project-assurance-modules` issue #10: a plausible prose candidate register could close the gate without sufficiently traceable research into concrete product/runtime alternatives and reusable datasets/content.

The original preflight is therefore preserved as regression history but is **not current project authority**.

Current methodology pin:

`Pukujan/project-assurance-modules@03fc55ae4036a9704cdb929fb3ae6dc520ae2183`

Current projectization work:

- issue #8;
- branch `pam-v0.2-reprojectization`;
- `assurance/RESEARCH_HANDOFF.md`;
- `assurance/REUSE_ASSESSMENT.json`;
- `assurance/SCOPE_BOUNDARY.md`;
- `PROJECT_ASSURANCE.json`;
- `HANDOFF_STATE.json`.

Old issues #1 through #6 and the old `docs/*` preflight artifacts are superseded unless explicitly regenerated and referenced by the current PAM v0.2 manifest.

## Research direction

The product idea remains a fun, mobile-first interview learning experience rather than a plain four-choice quiz.

The working interaction thesis is:

```text
technical mission
  -> inspect jargon if needed
  -> make a decision
  -> explain why
  -> optionally request progressive hints
  -> separate deterministic / empirical / reasoning feedback
  -> see a visual consequence
  -> earn game progression
  -> preserve learning evidence separately
  -> later face changed-surface transfer
```

The first research context remains mid-level Applied AI / RAG, with DSA, ML fundamentals, and general system design as possible later tracks rather than assumed first-build scope.

## What the new reuse research found

The PAM v0.2 assessment now uses concrete internal/external alternatives instead of abstract categories.

Important internal candidates/assets include:

- `Pukujan/Study-os` for longitudinal learner evidence;
- `Pukujan/Eval-lab` as deterministic/hidden-evaluation precedent;
- `Pukujan/design-bakery` for the requested engineering-system visual language;
- an existing owner Expo/React Native application as mobile-stack feasibility evidence.

Concrete external alternatives/assets considered include:

- H5P Branching Scenario;
- Oppia;
- GrillKit;
- Loadout;
- Expo / React Native;
- Flutter;
- DeepEval;
- Ragas;
- Inspect AI;
- RAGBench;
- BEIR HotpotQA;
- System Design Primer.

The current machine-readable assessment proposes composing/reusing those systems and assets where they fit and building only the narrow uncovered game/mission layer. That disposition is still **draft** until project-owner review closes `REUSE_008`.

## Current scope draft

The fresh scope draft aims to validate one small end-to-end mobile learning loop before broad infrastructure:

- touch-first mobile shell;
- a small Applied AI/RAG mission set;
- jargon tooltips;
- progressive hints;
- selected typed `why?` reasoning;
- deterministic rules plus constrained reasoning interpretation;
- simple visual/game progression separated from mastery;
- Study OS evidence composition if its contracts fit;
- at most one small dataset-backed practice fixture after benchmark-integrity review.

A general run bench, arbitrary code execution, distributed-system simulation, broad multi-track curriculum, voice mock interview, social infrastructure, and commercial/public-user infrastructure are outside the current horizon.

See `assurance/SCOPE_BOUNDARY.md` for the explicit admission/defer/reject rules.

## Projectization gate

Do **not** start product/runtime implementation merely because the concept is clear.

Current order:

1. traceable internal/external reuse and asset discovery;
2. fresh scope boundary;
3. PAM routing/gap analysis;
4. project-owner review of the material build/reuse + scope disposition;
5. freeze the reviewed manifest;
6. only then regenerate product definition, architecture, invariants, benchmark plan, and implementation issues.

PAM is project methodology, not a game/runtime dependency.
