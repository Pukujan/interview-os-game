# Interview OS projectization notes

This file records the initial projectization working state while PAM applicability is being resolved.

## Current product intent

Build a personal, non-commercial mobile interview-preparation game focused first on mid-level Applied AI engineering. The learning experience should combine rapid questions, scenario-based engineering decisions, typed reasoning, progressive hints, tappable jargon definitions, progression/levels, and selected dataset-backed or executable evaluation.

## Existing systems considered for reuse

- `Pukujan/Study-os`: learner evidence, assistance/fading, transfer, retention, capability-state concepts, and curriculum-control concepts.
- `Pukujan/project-assurance-modules`: projectization methodology only; not part of the game runtime.
- Public technical datasets and educational sources: content/evaluation inputs with explicit provenance.

## Primary scope risk

The product can easily expand simultaneously into a quiz app, RAG sandbox, DSA execution service, distributed-systems simulator, AI interviewer, curriculum engine, animation-heavy game, and multi-platform application. The first build must therefore freeze a narrow vertical slice before runtime implementation.

## Candidate first vertical slice

Applied AI / RAG only:

- terminology/tooltips;
- decision questions;
- typed `why?` reasoning;
- progressive hints;
- deterministic + rubric-constrained LLM evaluation;
- simple progression;
- one dataset-backed mission;
- Study OS-compatible learning-event output.

No full infrastructure simulator or general-purpose run bench in the first slice.
