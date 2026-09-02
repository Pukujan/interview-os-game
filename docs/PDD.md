# Product Definition — Interview OS Game

Status: V0 preflight

## Problem

Technical interview preparation is fragmented across question banks, coding sites, system-design reading, ML references, and AI chat. Many products reward recognition of a correct option or completion count, but mid-level engineering interviews require the learner to make a decision under constraints, explain the reasoning, respond to changing information, and retain the underlying capability across differently worded problems.

Interview OS should make that practice short enough for a phone while preserving engineering judgment.

## Primary user

Initial user: the project owner.

Initial interview target: mid-level Applied AI engineering with emphasis on LLM applications, RAG, evaluation, AI systems design, production trade-offs, and adjacent ML/DSA/system-design fundamentals.

The project is personal and non-commercial at V0. No public-user growth requirements are assumed.

## Product thesis

A useful interview-learning game can be substantially smaller than a full engineering simulator if each mission combines:

1. a concrete technical situation;
2. one or more defensible decisions;
3. a short explanation of why;
4. terminology help that does not leak the solution;
5. progressively stronger hints whose assistance is recorded;
6. feedback grounded in authored rubrics, deterministic evidence, or datasets where possible;
7. changed-surface follow-up/transfer rather than repeated memorization;
8. game progression that makes repeated practice enjoyable without being mistaken for mastery.

## Core loop

```text
choose track / mission
        -> inspect scenario
        -> make decision
        -> explain why
        -> optionally use terminology or hints
        -> evaluate decision + reasoning
        -> show consequence / feedback
        -> record attempt evidence
        -> award game progression
        -> schedule/select changed follow-up
```

## V0 interaction modes

### Rapid decision

A concise technical decision with a single best answer under stated assumptions, followed by optional short reasoning.

### Scenario decision

A 2–5 minute problem containing constraints, telemetry, architecture context, or evaluation results. The learner chooses an intervention and explains the trade-off.

### Debug/incident mission

The learner inspects a failing technical system, chooses what evidence to inspect or which hypothesis to test, then proposes a fix.

### Boss mission

A multi-stage interview scenario in which constraints change after each decision. V0 boss missions are state-machine content, not full infrastructure simulation.

### Dataset-backed mission

A bounded mission whose evidence or outcome is derived from a pinned dataset/protocol rather than invented solely by an LLM.

## Help model

### Terminology tooltip

Purpose: define jargon such as `NDCG`, `HNSW`, `p95`, `reranker`, or `idempotency` without telling the learner what action to take.

Tooltips do not reduce game XP or count as problem-solving assistance, but repeated terminology lookups may be recorded separately as learning evidence.

### Progressive hints

Hints correspond to increasing assistance strength. V0 should preserve compatibility with Study OS assistance semantics:

- A0: no help;
- A1: reminder;
- A2: small cue;
- A3: structural/subgoal hint;
- A4: partial scaffold;
- A5: worked example;
- A6: complete solution.

V0 need not expose all levels in every mission, but it must record what was used.

## Evaluation model

The evaluator has three separable evidence sources:

1. **deterministic/authored decision evidence** — answer keys, constraints, executable assertions, known metrics, or authored accepted decision sets;
2. **dataset/run evidence** — observed results from a pinned fixture/protocol where a mission supports execution;
3. **LLM reasoning interpretation** — maps free-form explanation text to an explicit authored rubric and may generate feedback/follow-up wording.

The LLM is not allowed to invent empirical results or silently override deterministic evidence.

## Progression model

Game progression and learning evidence remain separate.

Game state may include:

- XP;
- levels;
- unlocks;
- streaks;
- cosmetic/world progression;
- mission completion.

Learning evidence may include:

- decision correctness;
- reasoning rubric coverage;
- assistance level;
- terminology lookups;
- transfer result;
- delayed result when later enabled;
- capability tags.

A high XP value alone is never presented as proof of interview readiness.

## Initial content world

V0 focuses on Applied AI / RAG. Candidate concept families:

- retrieval vs generation failure boundaries;
- chunking and metadata;
- embeddings and vector retrieval;
- hybrid retrieval;
- reranking;
- evaluation metrics and golden sets;
- grounding/citation quality;
- latency/cost/quality trade-offs;
- caching and production reliability;
- multi-tenant/security awareness;
- debugging changes in retrieval quality.

## Visual/game direction

The product should feel like an engineering game rather than a classroom quiz. Visual language should draw from the project owner's Design Bakery work: pipelines, system maps, components, signals, incidents, diagnostic tools, blueprint-like progression, and visible consequences.

Visuals must remain functional. Examples:

- tappable architecture components expose definitions/telemetry;
- failures visibly propagate through a pipeline;
- an unlocked skill/world represents actual available mission families;
- a hint may be presented as a diagnostic tool;
- a mission result can animate the system consequence rather than only showing a green/red card.

## Success criteria for the first playable milestone

The first milestone succeeds when:

1. the project owner can complete a 10–15 minute session on a phone without leaving the app for basic terminology;
2. at least three mission types feel meaningfully different from ordinary multiple-choice trivia;
3. typed reasoning is evaluated against explicit rubrics with inspectable feedback;
4. assistance use changes the evidence record without making tooltips punitive;
5. a dataset-backed RAG mission produces reproducible evidence at a pinned source identity;
6. game progression is motivating while capability evidence remains separately inspectable;
7. a changed-surface follow-up can distinguish memorized wording from transfer of the underlying concept;
8. the project owner chooses to return for another session without needing the full run-bench vision.

## Kill / re-scope criteria

Re-scope before adding major infrastructure if:

- typed `why?` answers add little learning value relative to simple Q/A;
- evaluation feedback feels arbitrary despite authored rubrics;
- the game layer adds friction without increasing practice frequency or engagement;
- dataset-backed missions do not add enough value to justify backend complexity;
- Study OS integration requires duplicating or weakening its evidence model;
- the first visual interaction spike cannot achieve the desired feel economically in the selected stack.

## Non-goals

See `docs/SCOPE_BOUNDARY.md`; those exclusions are authoritative for the V0 horizon.
