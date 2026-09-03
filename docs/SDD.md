# System Design — Interview OS Game V0

Status: V0 preflight

## Design goals

- keep the first playable product small enough to validate rapidly;
- preserve a native iOS/Android path from one application codebase;
- make mission evaluation inspectable and reproducible;
- keep hidden evaluation material and model credentials outside the client;
- separate game progression from learning/capability evidence;
- integrate with Study OS through a boundary contract rather than duplicated learner-state logic;
- allow richer run-bench execution later without designing a general simulation platform now.

## High-level architecture

```text
┌──────────────────────────────────────────────────────┐
│ Expo / React Native client                           │
│                                                      │
│ Track map / progression                              │
│ Mission renderer                                     │
│ Architecture/system-diagram interactions             │
│ Tooltips + hint UI                                   │
│ Local non-authoritative game state                   │
└───────────────────────┬──────────────────────────────┘
                        │ mission attempt
                        ▼
┌──────────────────────────────────────────────────────┐
│ Evaluation API                                       │
│                                                      │
│ Mission loader / version check                       │
│ Deterministic decision evaluator                     │
│ Rubric-constrained LLM reasoning interpreter         │
│ Hidden/transfer item access                          │
│ Dataset-backed mission adapter                       │
│ Evidence/result assembler                            │
└───────────────┬───────────────────────┬──────────────┘
                │                       │
                ▼                       ▼
       Content / datasets         LLM provider
       pinned mission data        structured output only
                │
                ▼
┌──────────────────────────────────────────────────────┐
│ Study OS boundary                                    │
│                                                      │
│ V0: versioned export/adapter contract                │
│ Later: direct integration if justified               │
└──────────────────────────────────────────────────────┘
```

PAM remains outside this runtime architecture and is used only to projectize/assure the repository.

## Client

### Selected platform direction

Expo + React Native + TypeScript, subject to the visual interaction spike defined in `docs/BUILD_VS_REUSE.md`.

### Client responsibilities

- navigation and track/world presentation;
- mission rendering from a versioned public-safe mission payload;
- local interaction state for the active mission;
- terminology/tooltips;
- hint request/display UX;
- typed reasoning input;
- interactive system diagrams/telemetry presentation;
- result/progression presentation;
- local game-state cache where safe.

### Client must not own

- LLM API credentials;
- hidden/confirmatory mission answers;
- authoritative rubric scoring code when it would expose hidden evaluation;
- private dataset labels intended to remain hidden;
- canonical Study OS mastery/capability state;
- empirical result fabrication.

## Mission/content model

A mission is versioned content with explicit capability intent. Planned core fields include:

- `mission_id` + version;
- track and concept/capability tags;
- mission type;
- prompt/scenario;
- visible constraints/telemetry;
- interaction schema;
- terminology references;
- assistance/hint ladder;
- deterministic accepted decision(s) where applicable;
- reasoning rubric;
- source/dataset provenance;
- transfer-family identity;
- evaluation policy;
- presentation/visual metadata.

The exact JSON schema is a post-preflight implementation task and must not silently change the evidence meaning of existing mission versions.

## Evaluation API

The backend/provider implementation is intentionally unresolved at preflight. The boundary is more important than the vendor.

### Request

```text
mission identity/version
attempt decision/action
free-form reasoning
assistance events
terminology lookup events
client-visible context revision
```

### Evaluation sequence

```text
validate request
  -> load exact mission version
  -> evaluate deterministic decision constraints
  -> execute dataset adapter if mission requires it
  -> send only allowed context + rubric to LLM reasoning interpreter
  -> validate structured LLM output
  -> combine evidence according to mission scoring policy
  -> return feedback + game result + learning evidence payload
```

The LLM cannot overwrite a deterministic failure/pass fact unless the mission explicitly defines an ambiguity resolver and that resolver is itself reviewable.

## LLM reasoning interpreter

Purpose: interpret what the learner actually argued, not decide empirical reality.

Input should contain only:

- the learner's explanation;
- the question/scenario context required to interpret it;
- an authored rubric;
- deterministic/dataset facts the feedback may reference;
- allowed feedback policy.

Output should be a strict structured object containing rubric-criterion coverage, confidence/ambiguity flags, and concise feedback. Raw prose model output is not authoritative state.

V0 should preserve the learner answer and the evaluator version/model identity when feasible so questionable scores can be replayed.

## Dataset-backed mission adapter

V0 implements only one narrow RAG adapter rather than a general benchmark platform.

Responsibilities:

- load a pinned dataset/fixture identity;
- expose only mission-visible material to the client;
- compute the defined metric/result deterministically where possible;
- preserve exact configuration and result identity;
- keep hidden/confirmatory labels server-side;
- fail closed when the declared dataset/protocol identity cannot be loaded.

Candidate first source: a small curated subset/fixture derived from RAGBench or another selected RAG evaluation dataset after the mission contract is frozen.

## Game progression

Game progression may be local in V0 and may contain XP, level unlocks, streaks, cosmetics/world state, and completion history.

It is explicitly non-authoritative for learner capability.

A progression update is derived from an evaluated attempt but cannot rewrite the underlying evidence record.

## Study OS integration boundary

Interview OS should emit a stable evidence payload containing at least:

- mission/capability identity;
- observed answer/decision;
- observed deterministic outcome;
- reasoning rubric result as derived evidence;
- assistance level/events;
- terminology lookup events;
- transfer-family/item status;
- elapsed/session metadata where available;
- evaluator/mission version identity.

V0 may persist/export this payload within Interview OS before direct Study OS ingestion exists. Lack of direct runtime integration must not justify inventing a competing mastery model.

## Content visibility classes

### Public/practice-visible

Safe to bundle in the client:

- terminology definitions;
- teaching missions;
- practice prompts;
- visible hints;
- non-secret diagrams/assets.

### Server-visible but client-hidden

- hidden answer keys where exposure would trivialize evaluation;
- transfer/confirmatory items not yet administered;
- private dataset labels/qrels;
- LLM evaluator prompts/rubrics when disclosure would materially leak solutions;
- API credentials.

A mission can use public deterministic keys if hiding them creates no actual integrity benefit; secrecy is not a substitute for good assessment design.

## State authority

- Git repository: mission definitions, schemas, decisions, project configuration.
- Evaluation API: authoritative result for a submitted online attempt at the exact evaluator revision.
- Client: current UI and local game-state cache.
- Study OS: preferred longitudinal learning/capability evidence authority when integrated.
- PAM: methodology/projectization state only; never runtime learner state.

## Failure behavior

- unknown mission/schema/evaluator version: reject rather than guess;
- missing dataset identity: dataset-backed mission cannot claim empirical result;
- invalid LLM structured output: preserve deterministic evidence and mark reasoning evaluation unavailable/retryable rather than fabricating a score;
- backend unavailable: allow local practice only for missions whose evaluation contract is intentionally client-safe, and mark the attempt accordingly;
- hidden material detected in client packaging: build/test failure once packaging checks exist.

## Deferred architecture

Not designed as V0 components:

- arbitrary code sandbox;
- generalized vector database benchmark service;
- distributed-systems simulation engine;
- multi-user auth/profile service;
- public content authoring CMS;
- multiplayer/social backend;
- generalized adaptive curriculum service.
