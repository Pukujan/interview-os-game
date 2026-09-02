# Scope Boundary

Status: accepted for V0 preflight

## Current outcome

Create a playable personal mobile learning game that materially improves preparation for a mid-level Applied AI engineering interview by forcing the learner to make technical decisions, explain why, use progressively stronger assistance when needed, and receive evidence-grounded feedback.

The first vertical slice validates the learning/game loop rather than the full long-term simulator vision.

## V0 claims/capabilities

V0 may claim only that it provides:

- a cross-platform phone-oriented interview practice surface;
- an Applied AI/RAG track with a small set of authored missions;
- tappable terminology definitions that do not count as hints;
- progressive hints with recorded assistance level;
- decision questions plus short typed reasoning;
- deterministic answer/rubric structure with constrained LLM interpretation for open-ended reasoning;
- simple game progression separate from mastery evidence;
- at least one dataset-backed RAG mission with explicit source/protocol identity;
- an output contract capable of mapping attempts to Study OS-style evidence.

V0 does **not** claim validated population-level learning effectiveness or calibrated interview pass probability.

## Explicit non-goals for V0

- full DSA curriculum;
- full ML curriculum;
- general system-design curriculum;
- hundreds or thousands of scraped questions;
- general-purpose RAG experimentation platform;
- arbitrary Python/code execution sandbox;
- distributed-systems simulator;
- production-scale vector database benchmarking;
- autonomous AI interviewer with unrestricted grading authority;
- social features, multiplayer, leaderboards, marketplace, or public accounts;
- desktop IDE experience;
- replacing Study OS learner-state semantics;
- building native SwiftUI and Android applications separately;
- validating long-term retention from the first playable build.

## Deferred mechanisms

### General run bench

Disposition: **defer**.

Reason: high infrastructure cost before the core loop is validated.

Admission trigger: repeated use of V0 shows that static/scenario feedback cannot teach an important class of Applied AI trade-offs and one executable RAG mission demonstrates clear additional learning value.

### DSA execution sandbox

Disposition: **defer**.

Admission trigger: Applied AI vertical slice is useful and DSA becomes an active interview goal requiring executable implementation evidence.

### Full system-design simulator

Disposition: **defer**.

Admission trigger: multi-stage static scenarios are insufficient to test bottleneck, capacity, reliability, or failure reasoning.

### Broad source scraping/import pipeline

Disposition: **defer**.

Reason: content volume is not the present bottleneck; question quality, evidence semantics, and game feel are.

Admission trigger: mission schema and review process are stable and the first manually curated content set demonstrates value.

### Complex adaptive curriculum engine inside Interview OS

Disposition: **reject as duplicate ownership**.

Study OS should remain the preferred longitudinal learning/evidence layer. Interview OS may select the next mission locally in V0 but must not silently create a competing mastery authority.

## Scope admission rule

New work enters the current V0 assurance horizon only when at least one is true:

1. it is necessary to make a listed V0 capability function end-to-end;
2. it closes a material invariant/failure mode that would invalidate V0 evidence;
3. a small empirical spike demonstrates the current mechanism cannot satisfy a V0 requirement;
4. the project owner explicitly changes the V0 outcome and records the decision.

Everything else is `measure`, `defer`, `reject`, or `not_applicable` rather than automatically becoming implementation work.

## Repository and subsystem boundary

`Pukujan/interview-os-game` is the product/application repository. It owns:

- mobile/web game UI;
- mission/content contracts;
- game progression state;
- reasoning-evaluator integration;
- dataset-backed mission adapters;
- product-specific source provenance;
- Study OS export/integration adapter;
- V0 application/backend interfaces.

It must not own:

- PAM methodology definitions;
- a second canonical Study OS learner model;
- generic research-assurance infrastructure;
- general-purpose benchmark framework unrelated to Interview OS missions;
- a universal RAG or code-execution platform in V0.

## First vertical slice

Target approximately 15 high-quality Applied AI/RAG missions:

- 5 terminology/intuition or rapid-decision missions;
- 5 architecture/trade-off decision missions;
- 3 debugging/diagnosis missions;
- 1 dataset-backed RAG mission;
- 1 multi-stage boss mission.

The exact count may change without expanding scope; the important boundary is a small curated slice that exercises all V0 interaction types.
