# Interview OS — PAM v0.2 Scope Boundary

Status: projectization draft pending owner review of the material disposition

Methodology revision: `03fc55ae4036a9704cdb929fb3ae6dc520ae2183`

Source decision evidence: `assurance/REUSE_ASSESSMENT.json`

## 1. Current goal

Validate whether a **small, fun, mobile technical-interview learning loop** is valuable enough for repeated personal use before building broad curriculum or simulation infrastructure.

The first learning context is **mid-level Applied AI / RAG engineering** because it exercises conceptual knowledge, architecture trade-offs, debugging, evaluation, and production reasoning while allowing some later dataset-backed consequences.

The current project claim is deliberately narrow:

> Interview OS can present a compact technical mission, let the learner inspect terminology, make a decision, explain why, request progressively stronger assistance, receive evidence-separated feedback, and progress through a visually engaging game layer without confusing game progress with demonstrated learning.

## 2. Capabilities in the current assurance horizon

If the PAM v0.2 build-vs-reuse disposition is approved, the current horizon includes only the smallest end-to-end loop needed to test the claim above.

### 2.1 Mobile shell

- one Expo/React Native application codebase targeting iOS and Android;
- navigation sufficient for home/progression -> mission -> result -> next mission;
- mobile accessibility and touch-first interaction;
- a representative visual spike proving that the intended Design Bakery-derived visual language is comfortable on phone-sized targets.

### 2.2 Mission interaction

- a small authored Applied AI/RAG mission pack, not a broad curriculum;
- decision questions/scenarios that may include multiple-choice, ordering, diagnosis, or bounded architecture choices where pedagogically useful;
- short typed `why?` reasoning on selected missions;
- terminology entities that can be tapped for concise definitions without answer leakage;
- progressive hints with explicit assistance level/provenance;
- result feedback that separates answer correctness, reasoning evidence, assistance used, and game reward.

### 2.3 Evaluation boundary

- deterministic answer keys/rules where the task has an authored correct/acceptable decision set;
- constrained semantic interpretation for free-text reasoning against an authored rubric;
- a separate score aggregator that does not let an LLM override deterministic or empirical evidence;
- hidden/server-side material only where the mission actually requires a protected boundary;
- no claim that one score is a universal measure of interview readiness.

### 2.4 Progression

- game XP/levels/unlocks sufficient to make repeated use enjoyable;
- topic/capability evidence displayed separately from game XP;
- no mastery claim from streaks, XP, or repeated exposure alone.

### 2.5 Learning-evidence composition

- inspect and, if compatible, adapt to Study OS operations for attempt, assistance, assessment, transfer, and retention evidence;
- Interview OS may operate locally with game state before every Study OS integration is wired, but must not create a competing canonical mastery model.

### 2.6 Reusable content/data

- source/provenance metadata for imported or transformed educational material;
- one small RAGBench-derived or similarly justified dataset-backed **practice** fixture may enter V0 only after benchmark-integrity review establishes the exact revision, transformation, visibility class, and claim;
- public source material remains practice/development material after exposure and cannot be relabeled as unseen confirmatory evidence.

## 3. Explicit V0 non-goals

The following are outside the current assurance horizon even if they are part of the long-term vision:

- a general-purpose RAG execution/run-bench platform;
- arbitrary user code execution or a secure coding sandbox;
- a distributed-systems simulator;
- a complete DSA curriculum;
- a complete ML fundamentals curriculum;
- a complete system-design curriculum;
- a full voice mock-interview product;
- live collaborative whiteboards;
- multiplayer, leaderboards, social feeds, friends, or public profiles;
- public account infrastructure beyond what is strictly required for personal device use;
- subscriptions, payments, or commercial product infrastructure;
- a content-authoring CMS;
- automatic scraping/ingestion of thousands of interview questions;
- a generalized LLM-evaluation platform;
- a new proprietary RAG corpus when a reusable public fixture is sufficient;
- a second learner/mastery engine parallel to Study OS;
- separate SwiftUI and Android-native applications unless the cross-platform spike fails materially.

## 4. Deferred and rejected mechanisms

### Generalized run bench — `defer`

**Why:** high implementation and infrastructure cost before the core learning loop has demonstrated daily value.

**Reconsider when:** the small authored loop is used repeatedly and at least several high-value missions are materially limited by the absence of real execution rather than by content/interaction quality.

### Broad DSA / ML / system-design tracks — `defer`

**Why:** breadth would hide whether the underlying loop is good and would create large content/evaluation work before the Applied AI vertical is proven.

**Reconsider when:** the first track demonstrates repeat use and its content/evidence contracts are stable enough to generalize.

### DSA code sandbox — `defer`

**Why:** secure arbitrary execution is a separate project-sized problem. Early DSA can later use trace/ordering/pseudocode or tightly bounded fixtures before arbitrary execution is admitted.

**Reconsider when:** DSA becomes the next approved track and executable coding evidence is required for its current claims.

### Voice interviewer — `defer`

**Why:** voice adds latency, cost, interruption handling, speech recognition, and conversation-state complexity without proving the core reasoning loop.

**Reconsider when:** typed missions work and interview-conversation realism is the measured bottleneck.

### H5P Branching Scenario — `reject as V0 runtime`

**Why:** useful branching/content precedent, but adopting its content ecosystem does not remove enough bespoke mobile/evidence/evaluator work.

**Reconsider when:** Interview OS later needs a general authoring/runtime format and H5P interoperability becomes a concrete requirement.

### Oppia — `reject as V0 runtime`

**Why:** mature stateful learning platform but far broader deployment/product topology than the personal mobile game.

**Reconsider when:** the project changes into a broad authored-learning platform rather than the current narrow app.

### GrillKit — `reject as V0 runtime`

**Why:** strongest direct interview-platform comparator, but it is organized around interview sessions/question banks/coding tasks rather than the intended learning-evidence/game progression boundary.

**Reconsider when:** the product objective shifts from learning-game progression toward realistic interview-session simulation, or a concrete reusable subsystem proves cheap to extract.

### Loadout — `reject as V0 runtime`

**Why:** useful system-design interview/diagramming precedent, but current scope is text/touch learning missions and Loadout imports voice/whiteboard/web assumptions.

**Reconsider when:** live architecture diagramming becomes an approved system-design-track requirement.

### Flutter — `defer/reject relative to Expo for V0`

**Why:** technically capable but higher current integration cost because React/TypeScript/Expo code and Design Bakery React assets already exist internally.

**Reconsider when:** the representative Expo visual spike fails a material rendering, interaction, accessibility, or animation requirement that Flutter can demonstrably satisfy.

### DeepEval / Ragas / Inspect AI / Eval Lab runtime integration — `defer`

**Why:** reusable evaluation capabilities exist, but the learner-reasoning rubric contract must be defined before choosing an implementation dependency.

**Reconsider when:** the domain evaluator contract exists and a concrete framework removes substantial custom code while preserving deterministic score authority and privacy boundaries.

### BEIR HotpotQA as first dataset fixture — `defer`

**Why:** valuable retrieval benchmark but substantially larger/more complex than needed to prove the first dataset-backed practice mission.

**Reconsider when:** the first RAGBench-style fixture is insufficient for retrieval/reranking/multi-hop objectives.

### Public social/commercial infrastructure — `reject for personal project horizon`

**Why:** no current user/value claim requires it.

**Reconsider when:** the project purpose explicitly changes from personal study to multi-user distribution.

## 5. Scope-admission rule

A new capability, dependency, framework, dataset, infrastructure mechanism, or track may enter the current assurance horizon only when all of the following are true:

1. it addresses a failure, acceptance criterion, or blocker of a **current** V0 claim;
2. the need is evidenced by a concrete observation, test, contract gap, or reviewed requirement rather than novelty/interest;
3. reuse/build alternatives appropriate to the materiality of the change have been checked;
4. its cost/risk does not exceed the current complexity budget without displacing something else;
5. the current manifest/scope/decision lineage is updated before implementation begins.

Use this disposition vocabulary:

- **mitigate-now** — required for a current acceptance criterion or integrity boundary;
- **measure** — uncertainty is material and cheap evidence should be collected before adding scope;
- **defer** — plausible future value, no current-claim need;
- **reject-current-horizon** — incompatible with the current project purpose/complexity budget;
- **not-applicable** — genuinely unrelated to the current project claim.

Interesting technology by itself is never an admission criterion.

## 6. Repository and subsystem boundary

### `Pukujan/interview-os-game` may own, after review

- mobile game UI and presentation;
- mission/content schemas specific to Interview OS;
- glossary/tooltip presentation;
- progressive-hint interaction and game-side assistance event capture;
- authored deterministic mission rules;
- domain-specific reasoning-rubric interface;
- game score/progression state;
- minimal server/API code required to keep credentials or genuinely protected evaluator material off the client;
- source adapters/fixtures that transform approved public assets into bounded Interview OS practice material;
- adapter code that emits compatible evidence to Study OS.

### `Pukujan/interview-os-game` must not own by default

- canonical longitudinal learner mastery/retention semantics already covered by Study OS;
- PAM methodology or adopter-independent assurance logic;
- a generic LLM evaluation platform;
- a generic RAG benchmark framework;
- a universal coding sandbox;
- Design Bakery's web product/runtime;
- entire external interview/learning platforms copied into the repository.

### External/internal component boundaries

- **Study OS:** candidate authority for longitudinal learning evidence; integrate through explicit contracts.
- **Design Bakery:** visual-language/reference asset source; port bounded tokens/motifs rather than couple the web application.
- **Expo/React Native:** candidate mobile framework, not product-domain authority.
- **RAGBench / BEIR / System Design Primer:** source assets with provenance/visibility rules, not product logic.
- **PAM:** projectization methodology only.

## 7. Complexity budget for the first approved implementation horizon

Before a generalized platform is admitted, prefer roughly:

- one mobile app;
- one bounded mission domain model;
- one small deterministic scorer;
- one constrained reasoning-evaluator interface;
- one minimal protected server boundary if required;
- one Study OS adapter surface;
- one small curated source/dataset fixture;
- enough missions to evaluate repeat use, not enough content to simulate an entire interview curriculum.

If the implementation begins requiring multiple orchestration services, a vector-database platform, arbitrary-code isolation, several independent evaluator frameworks, or multiple native clients before the first loop has been used, the scope has likely escaped the current horizon.

## 8. Review boundary

This scope file is derived from the PAM v0.2 research and reuse assessment, but the final implementation disposition remains unreviewed while `REUSE_008` is pending.

Owner review should accept, modify, or reject the combined proposition:

> compose/reuse the identified systems and assets; build only the narrow mobile mission/game layer; keep the V0 horizon above; regenerate planning only after that disposition is approved.
