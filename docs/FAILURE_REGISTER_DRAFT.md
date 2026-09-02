# Failure Register Draft

Initial material failure modes to resolve before implementation:

1. Scope explosion: quiz, mobile game, RAG lab, DSA runner, system simulator, AI interviewer, and curriculum engine are all built at once.
2. Duplicate learning state: Interview OS recreates capabilities already owned by Study OS.
3. Trivia drift: questions reward vocabulary recall rather than interview reasoning and transfer.
4. LLM oracle failure: free-form model grading becomes inconsistent or authoritative without deterministic evidence.
5. Hint leakage: tooltips or progressive hints reveal answers while still counting as unaided evidence.
6. Benchmark contamination: practice examples or solutions leak into transfer/hidden evaluation.
7. False progression: XP/streaks are interpreted as mastery despite missing transfer or retention evidence.
8. Visual overload: game graphics add cognitive load without improving the learning action.
9. Dataset/version drift: results become irreproducible because source identities are mutable or undocumented.
10. Platform-first waste: substantial iOS/Android infrastructure is built before the core learning loop proves useful.
