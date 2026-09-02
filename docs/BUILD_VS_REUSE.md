# Build vs Reuse Decision

Status: accepted for V0 preflight

## Capability and constraints

Interview OS needs a personal, non-commercial learning product that runs on iOS and Android, supports highly customized interactive visuals, presents interview questions and scenarios, captures typed reasoning and assistance use, and can later connect to dataset-backed execution and Study OS learner evidence.

Current decision criteria:

- one codebase for iOS and Android;
- fast iteration for a single developer;
- strong support for custom animated/interactive UI;
- TypeScript/JavaScript ecosystem preferred when otherwise comparable;
- hidden evaluation/API secrets must not ship in the client;
- no requirement for a bespoke mobile rendering engine;
- no duplicate learner-state/research system when Study OS already owns the relevant semantics;
- no general-purpose run-bench platform in V0.

## Candidate register

### Learner evidence / adaptation

**Candidate: reuse `Pukujan/Study-os` concepts/contracts**

Disposition: **reuse/compose**.

Study OS already defines learner evidence, assistance/fading, transfer, retention, capability states, and curriculum-control concepts. Interview OS should emit compatible evidence rather than invent a second mastery model. A thin adapter may be needed once the exact integration contract is frozen.

**Candidate: build a new Interview OS mastery engine**

Disposition: **rejected for V0**.

Reason: duplicates Study OS responsibilities and creates two authorities for learner capability. Reconsider only if Study OS proves structurally incompatible with the mobile game's evidence needs.

### Mobile application framework

**Candidate: Expo + React Native + TypeScript**

Disposition: **selected for V0 unless a small UI spike exposes a blocking visual/performance constraint**.

Reasons:

- one project can target Android, iOS, and web;
- suitable for a highly custom app UI without maintaining separate native applications;
- fast personal-project iteration and a broad package ecosystem;
- supports a later native build/distribution path without requiring the first milestone to own native project plumbing.

Current reference: Expo SDK 57 / React Native 0.86 family as of the PAM preflight date. Exact dependency versions must be pinned when implementation begins rather than copied from this planning artifact.

**Candidate: Flutter**

Disposition: **serious alternative, not selected**.

Strengths: excellent custom rendering/animation model and a single iOS/Android/web codebase.

Trade-off: introduces Dart and a second application ecosystem without a demonstrated V0 requirement that Expo cannot meet. Reconsider if the visual interaction spike shows React Native/Expo cannot deliver the desired smooth custom system diagrams/animations economically.

**Candidate: separate SwiftUI + Android native apps**

Disposition: **rejected for V0**.

Reason: duplicates implementation effort and platform-specific state before the learning loop is validated.

**Candidate: mobile web/PWA only**

Disposition: **rejected as the primary product surface, retained as a useful Expo/web development target**.

Reason: the intended experience is a phone game and should preserve a credible native-app path, but web remains useful for rapid iteration.

### Question/game engine

**Candidate: generic quiz framework**

Disposition: **do not adopt as the core engine**.

Reason: the product requires typed reasoning, progressive assistance, scenario state, interactive system diagrams, dataset provenance, transfer variants, and later executable missions. A generic multiple-choice engine would become the wrong domain abstraction.

**Candidate: build a narrow mission engine**

Disposition: **build_new**.

Justification: the required capability is specifically an evidence-producing interview mission state machine, not a generic quiz. Existing quiz abstractions do not satisfy the Study OS evidence boundary or planned multi-stage scenario semantics. V0 must keep this engine intentionally small.

### Project methodology

**Candidate: `Pukujan/project-assurance-modules`**

Disposition: **reuse as projectization methodology, not runtime dependency**.

PAM defines the planning, scope, benchmark, continuity, provenance, and engineering-assurance obligations for the project. Runtime gameplay must not depend on PAM.

## Cheap probes required before deeper implementation

1. Build one Expo screen containing a tappable architecture diagram, animated state transition, tooltip/bottom-sheet term definition, and progressive hint control.
2. Verify that the same screen remains usable on a small Android and iOS viewport.
3. Do not run a larger Flutter comparison unless that spike exposes a concrete blocking constraint.

## Final implementation disposition

**Compose existing systems where they already own the problem; build only the game-specific mission/application layer.**

- Study OS: reuse for learner evidence semantics.
- PAM: reuse for projectization/assurance methodology.
- Expo/React Native: reuse for cross-platform application infrastructure.
- Interview mission engine: bespoke, narrow implementation earned by product-specific requirements.

## Reconsideration triggers

- Study OS cannot represent required mission/assistance evidence without corrupting its evidence model.
- Expo spike fails material animation, interaction, accessibility, or performance requirements.
- V0 proves that dataset-backed execution is the primary learning value rather than scenario/reasoning gameplay.
