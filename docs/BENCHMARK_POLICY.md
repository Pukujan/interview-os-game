# Benchmark, Dataset, and Hidden-Evaluation Policy

Status: V0 preflight

This policy applies to Interview OS missions that use external datasets, executable fixtures, quantitative metrics, hidden answer material, transfer items, or empirical model/system results.

## 1. Evaluation claims are narrow

A mission must state the claim its evaluation can support.

Examples:

- `retrieval recall@k on fixture X under config Y` supports a retrieval result, not general RAG quality;
- an authored reasoning rubric supports evidence that specific reasoning concepts were expressed, not a calibrated probability of interview success;
- a transfer item supports changed-surface performance on that item/family, not durable mastery unless Study OS retention requirements are separately met.

No aggregate score may silently combine retrieval, answer correctness, latency, cost, reasoning quality, safety, or citation quality into an undefined universal `AI engineering score`.

## 2. Exact protocol/data identity

Every dataset-backed result must preserve enough identity to reproduce it:

- source/dataset name;
- immutable revision, commit, digest, or locally curated fixture version where available;
- subset/split/item identity;
- transformations/filtering used to create the mission fixture;
- metric definition/version;
- relevant model/component/config identities;
- mission and evaluator version.

Mutable labels such as `latest` are not sufficient for retained evidence.

If an external dataset cannot be pinned reliably, V0 should create a small reviewed local fixture with its own version/digest and preserve the upstream source provenance.

## 3. Development, practice, transfer, confirmatory boundaries

Content visibility classes:

- `teaching`: examples/solutions may be exposed;
- `practice`: learner may repeat the item and inspect full feedback;
- `transfer`: changed-surface item intended to test application of the same capability;
- `confirmatory_hidden`: item/label/answer withheld until the declared evaluation event.

Rules:

- teaching/practice exposure is permanent provenance; an exposed item cannot later become unseen evidence;
- transfer-family membership is recorded separately from exact item identity;
- hidden/confirmatory items remain server-side or outside normal client packages until opened;
- once a hidden item's answer/label is exposed, future use must reflect that changed visibility;
- V0 does not require every mission to have hidden evaluation; the boundary exists only where the claim needs it.

## 4. Leakage and packaging controls

Before hidden/confirmatory evaluation is relied on, implementation must add fail-closed checks appropriate to the boundary:

- static/package scans for known hidden item IDs, labels, expected answers, or restricted fixture paths;
- tests that public mission payload generation excludes hidden fields;
- review of prompt/context packaging sent to the learner-side or reasoning evaluator;
- semantic review when token/path scans cannot establish that the answer was not leaked.

Hidden answers must not be placed in agent-visible handoff files.

## 5. LLM judge boundary

LLM reasoning evaluation is allowed for semantic interpretation of learner explanations under an authored rubric.

It is not the sole oracle for:

- deterministic answer-key correctness;
- executable code/test results;
- dataset metrics;
- latency/cost measurements;
- hidden-item identity;
- whether a protected answer leaked;
- release-significant benchmark claims where stronger evidence exists.

LLM evaluator outputs remain derived evidence and must use a validated structured schema.

## 6. Result artifacts

A retained dataset-backed result should include:

- claim/mission identity;
- timestamp/session identity where relevant;
- exact dataset/fixture/protocol identities;
- exact evaluator/model/config identities;
- raw deterministic metrics used by scoring;
- derived LLM rubric output separately identified;
- final game score separately identified;
- limitations/failures;
- whether the item was practice, transfer, or confirmatory at evaluation time.

Do not present a result from a missing/mismatched protocol as comparable to a prior run.

## 7. First V0 dataset-backed mission

The first adapter should use a deliberately small RAG fixture, likely curated from RAGBench or another explicitly selected source after mission contracts exist.

The first claim should be narrow, for example:

> Given this pinned corpus/query/evidence fixture and the declared retrieval/ranking result, can the learner correctly diagnose the failing stage and justify an intervention under the visible latency constraint?

V0 should not attempt to establish production-scale vector database performance.

## 8. Current implementation state

Policy/protocol boundary: defined in this document.

Still required before empirical V0 claims are considered closed:

- mission/source schema;
- exact first dataset fixture identity;
- packaging/leakage tests;
- reproducible result artifact schema;
- at least one replayable dataset-backed run.
