# Interview OS — Research Handoff for PAM v0.2 Reprojectization

Status: current projectization input, pre-review

PAM methodology revision: `03fc55ae4036a9704cdb929fb3ae6dc520ae2183`

Active projectization issue: #8

## Why this handoff exists

The first Interview OS preflight used `projectization.build-vs-reuse@0.1.0`. PAM issue #10 later demonstrated that the old closure semantics allowed a plausible self-authored candidate register to stand in for sufficiently traceable alternative and reusable-asset discovery. Interview OS was the regression adopter that exposed the defect.

The old preflight and its implementation backlog are therefore historical evidence, not current authority. This handoff restarts projectization from the research inputs while preserving repository history.

## Problem and intended outcome

Build a personal, fun, mobile-first technical interview learning experience that helps the learner develop usable interview reasoning rather than merely recognize trivia answers.

The working product idea combines:

- compact technical questions and scenario missions;
- typed explanation of *why* a decision is correct;
- progressive hints that preserve assistance provenance;
- tappable jargon/tooltips that teach vocabulary without revealing the answer;
- visual/game progression inspired by Design Bakery's engineering-system aesthetic;
- mixed evaluation in which deterministic keys, executable/dataset evidence, and constrained LLM reasoning interpretation remain separate;
- longitudinal learning evidence such as assistance, transfer, and retention when Study OS contracts fit;
- later expansion from Applied AI/RAG into DSA, ML fundamentals, and system design only after the first loop proves useful.

## Current research conclusions treated as inputs, not final implementation decisions

1. **A generic four-choice quiz is too weak as the full product model.** The valuable loop includes decision-making, explanation, assistance, consequences, and transfer.
2. **The first build should remain small.** A large RAG/system-design simulator is a product vision, not a justified starting scope.
3. **Vocabulary help and solution hints are different interventions.** Tooltips should define terms without answer leakage; hints may progressively assist solving and must be recorded as assistance.
4. **Game progression and learning evidence are different.** XP/streaks/levels can motivate use, but they must not be silently equated with mastery.
5. **LLM output is derived evidence.** When stronger deterministic, executable, or dataset evidence exists, model judgment cannot override it.
6. **Reusable data/content exists.** Interview OS should not begin by inventing RAG corpora, retrieval benchmarks, or system-design question banks from scratch.

These are research hypotheses/constraints for projectization. They remain subject to the PAM build-vs-reuse and scope gates.

## Traceable internal discovery

The authenticated owner repository inventory was reviewed for reusable learning, evaluation, visual, and mobile assets.

### `Pukujan/Study-os`

Relevant because it already defines:

- learning episodes;
- observed vs self-reported vs derived evidence;
- assistance/fading;
- transfer and delayed retention;
- learner-state and assessment boundaries;
- explicit non-ownership of general RAG infrastructure and broad product UI.

Current hypothesis: **compose** through an adapter rather than duplicate learner-state semantics.

### `Pukujan/Eval-lab`

Relevant because it already demonstrates:

- deterministic gates that do not let model output determine the verdict;
- visible vs hidden test separation;
- evidence artifacts;
- evaluation frameworks such as Inspect AI and Promptfoo;
- fail-closed evidence/verification patterns.

Current hypothesis: do **not** adopt it as Interview OS runtime. Reuse design patterns or selected evaluation components only if later contracts justify them.

### `Pukujan/design-bakery`

Relevant because it is the requested visual reference and contains the ONI engineering-system language, including the `Build -> Break -> Debug -> Log -> Blueprint` motif and system-flow visualizations.

Current hypothesis: reuse the **visual grammar/design references**, not the complete web application architecture.

### `Pukujan/gemini-medical-frontend-react-native`

Relevant because it is a concrete prior owner Expo/React Native app using Expo Router, Haptics, Reanimated, TypeScript, and Android/iOS scripts.

Current hypothesis: use as concrete feasibility/reuse evidence for the mobile stack, not as the Interview OS application base.

## Traceable external runtime/application discovery

Concrete alternatives inspected rather than using abstract categories:

### `h5p/h5p-branching-scenario`

Branching interactive-content runtime with feedback/state semantics. Useful precedent, but it does not directly supply the mobile game progression, typed learner reasoning, Study OS evidence boundary, or protected evaluation model.

### `oppia/oppia`

Large interactive-learning platform with stateful explorations, rules, learner responses, and feedback. Strong learning-product precedent; substantially broader than the personal mobile V0.

### `GrillKit/grillkit`

Direct technical-interview comparator with question banks, structured sessions, scoring, follow-ups, coding exercises, and public/hidden tests. Important because the original preflight should have compared against a concrete interview trainer like this instead of `generic quiz framework`.

### `VC444/loadout`

System-design interview practice with staged interview flow, an AI interviewer, timed sessions, and real-time architecture diagramming. Useful future system-design interaction precedent; not a complete match for the learning/evidence game loop.

## Traceable mobile framework discovery

### `expo/expo`

Serious candidate for the mobile shell. Fits the one-codebase Android/iOS requirement and aligns with existing owner React/TypeScript/Expo experience.

### `flutter/flutter`

Serious alternative with strong custom rendering and multi-platform support. It is not rejected as incapable; current trade-off is higher integration/context-switch cost relative to existing Expo/React Native assets.

## Traceable evaluation-framework discovery

### `confident-ai/deepeval`

General LLM evaluation framework with model-graded/custom metrics and RAG-oriented evaluation capabilities.

### `vibrantlabsai/ragas`

RAG/LLM evaluation library oriented toward datasets, experiments, and retrieval/generation quality metrics.

### `UKGovernmentBEIS/inspect_ai`

General AI evaluation framework with scoring, tool use, multi-turn evaluation, and model-graded evaluation.

Current conclusion: reusable evaluator infrastructure exists, so Interview OS should not blindly reinvent general evaluation tooling. However, none of these should automatically become the authority for human-learner reasoning or override deterministic game evidence. Selection is deferred until the learner-reasoning/evaluator contract exists.

## Traceable reusable dataset/content discovery

### RAGBench

Locator: `https://huggingface.co/datasets/galileo-ai/ragbench`

Potential use: Applied AI/RAG diagnosis, grounding, retrieval/relevance, answer-support, and evaluation missions. Prefer a small pinned transformed fixture rather than shipping the full dataset.

### BEIR HotpotQA

Locator: `https://huggingface.co/datasets/BeIR/hotpotqa`

Potential use: retrieval, reranking, multi-hop retrieval, query decomposition, and objective metric-driven missions. Probably a follow-on rather than the simplest first fixture.

### System Design Primer

Locator: `donnemartin/system-design-primer`

Potential use: future system-design curriculum/source material and scenario inspiration. Public practice material must never later be relabeled as unseen confirmatory evidence.

## Constraints carried into the reuse decision

- Personal/non-commercial first use.
- One mobile codebase for iOS and Android is preferred.
- The interaction must be more engaging than a plain quiz while remaining fast enough for repeat daily study.
- Technical terminology must be inspectable in-place.
- Assistance should be progressive and observable.
- Game progression must remain separate from evidence of learning.
- Hidden/protected evaluation material cannot live in ordinary client payloads.
- Deterministic/executable/dataset evidence outranks LLM interpretation where they conflict.
- Reusable data/content should be adapted with provenance rather than recreated by default.
- Broad run-bench infrastructure is not assumed to be in V0.

## Explicit non-goals before projectization review

- No broad implementation backlog.
- No universal RAG execution platform.
- No distributed-system simulator.
- No arbitrary code sandbox.
- No full DSA + ML + system-design + Applied-AI curriculum at once.
- No separate iOS and Android native applications unless cross-platform evidence fails.
- No new learner-mastery authority that competes with Study OS without a demonstrated incompatibility.

## Current draft implementation disposition

The machine-readable assessment in `assurance/REUSE_ASSESSMENT.json` currently proposes:

- **compose** Study OS for longitudinal learner evidence;
- **reuse** Design Bakery visual language;
- **configure** Expo/React Native for the mobile shell;
- **reuse/adapt** RAGBench and other sourced content/data where fit;
- **build new only** the narrow mission/game domain layer not covered by researched alternatives.

This is a **draft technical conclusion**, not the reviewed PAM gate decision. `REUSE_008` remains open until project-owner review.

## Unresolved questions

1. Does a representative Expo interaction spike support the desired animated Design Bakery-style mobile feel on both target form factors?
2. Which exact RAGBench subset/revision/transformation should become the first dataset-backed practice fixture?
3. Which exact Study OS application operation(s) should receive Interview OS attempt, assistance, reasoning, and assessment evidence?
4. Does the first evaluator need DeepEval/Ragas/Inspect AI, or is a small domain-specific rubric interpreter plus deterministic scorer sufficient?
5. After the reviewed reuse disposition, what is the smallest scope that tests whether the daily learning loop is genuinely valuable?

## Superseded material

The following are preserved only as v0.1 historical artifacts until explicitly regenerated under issue #8:

- `docs/BUILD_VS_REUSE.md`;
- `docs/SCOPE_BOUNDARY.md`;
- `docs/PDD.md`;
- `docs/SDD.md`;
- `docs/INVARIANTS.md`;
- `docs/FAILURE_REGISTER.md`;
- `docs/BENCHMARK_POLICY.md`;
- `docs/DECISIONS.md`;
- old issues #1 through #6.

Agents must not treat these artifacts as current closure evidence merely because they remain in Git history or in the working tree.
