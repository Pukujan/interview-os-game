# Decision Log

This log records consequential V0 project decisions. Routine issue/task state remains in GitHub.

## D-001 — Treat Interview OS as a separate product surface

Status: accepted

Decision: `Pukujan/interview-os-game` owns the game/application layer. It does not replace Study OS and does not embed PAM as a runtime service.

Rationale: the three systems have distinct authority boundaries: Interview OS owns gameplay, Study OS owns longitudinal learner evidence/capability semantics, and PAM owns reusable projectization methodology.

Sources:

- `Pukujan/Study-os` product/evidence architecture reviewed during projectization.
- `Pukujan/project-assurance-modules@0e62c3e7cbb90e9242103238829bbf0cc2f94917`.

Reconsideration trigger: a concrete integration constraint demonstrates that the separation cannot preserve required evidence or product behavior.

## D-002 — V0 is Applied AI/RAG first

Status: accepted

Decision: validate the product with a small Applied AI/RAG vertical slice before activating broad DSA, ML, or general system-design content.

Rationale: the immediate interview target is Applied AI; a narrow slice can exercise terminology, decision reasoning, hints, diagnosis, progression, dataset-backed evidence, and a boss scenario without requiring multiple curricula.

Reconsideration trigger: the project owner's near-term interview target materially changes.

## D-003 — Defer the general-purpose run bench

Status: accepted

Decision: V0 may contain one bounded dataset-backed RAG adapter but does not build a generalized execution/simulation platform.

Rationale: the current product hypothesis can be tested with much less infrastructure. A general run bench is admitted only if V0 demonstrates a clear learning gap that static/multi-stage scenarios cannot address.

## D-004 — Reuse Study OS learning semantics

Status: accepted

Decision: Interview OS should emit versioned learning evidence compatible with Study OS concepts rather than create an independent canonical mastery model.

Rationale: Study OS already distinguishes observed, self-reported, and derived evidence and defines assistance/fading, transfer, retention, and capability-state semantics.

Reconsideration trigger: an explicit contract analysis shows that Study OS cannot represent the required evidence without semantic corruption.

## D-005 — Select Expo/React Native for the first application spike

Status: accepted with validation condition

Decision: use Expo + React Native + TypeScript for the V0 client unless a representative visual/interaction spike exposes a blocking constraint.

Rationale: one codebase targets iOS/Android/web and fits the small personal-project iteration requirement. The product does not currently justify separate native apps or a second application language ecosystem.

External references reviewed at decision time:

- Expo official documentation, current SDK reference and universal-app tutorial (September 2026).
- Flutter official multiplatform documentation as the serious alternative.

Validation condition: one representative screen must prove tappable system diagrams, tooltip/bottom-sheet interaction, progressive hint UI, animation, and small-screen usability.

## D-006 — LLM evaluates reasoning, not reality

Status: accepted

Decision: LLM output may map free-form explanations to an explicit rubric and create feedback, but deterministic keys, executable evidence, and dataset metrics remain authoritative where available.

Rationale: makes scoring inspectable and reduces arbitrary evaluator behavior.

## D-007 — Game progression and learning progression remain separate

Status: accepted

Decision: XP, levels, streaks, unlocks, and world progression are motivational game state. They do not constitute mastery evidence.

Rationale: avoids rewarding grinding as proof of capability and preserves Study OS's evidence-based model.

## D-008 — Hidden evaluation is conditional, not universal

Status: accepted

Decision: hide answers/items only when the evaluation claim benefits materially from an unseen boundary. Do not create secrecy merely for ceremony.

Rationale: this is a personal project; the goal is honest measurement and accidental-leakage prevention, not adversarial DRM.

## D-009 — Preserve source provenance even for personal/non-commercial content

Status: accepted

Decision: imported/scraped/public-source material may be used for personal study, but mission/source records should preserve where the material came from and distinguish source text from authored/derived game content.

Rationale: provenance is useful for technical correctness, refreshes, attribution, debugging, and later review independent of commercial licensing concerns.
