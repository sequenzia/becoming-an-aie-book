# Project and assessment design

## The recurring support application

The fictional company, Cedar Support Software, sells a team collaboration product. Its support staff use a service that classifies incoming requests, extracts relevant fields, searches documentation, drafts responses, and investigates unresolved issues. The system assists support staff first. Any demonstration that changes tickets uses an isolated service with fictional records.

The application grows through five stages: measurable extraction, knowledge assistance, a controlled workflow, a bounded investigation agent, and a monitored release. The same problem brief, datasets, and evidence record evolve throughout, so readers can see the consequences of earlier decisions.

The textbook's examples use Python. Begin with explicit model calls and ordinary application code, then explain higher-level abstractions after readers can inspect the underlying flow. Keep the model boundary replaceable while preserving provider-specific capabilities explicitly; do not imply that every model supports the same inputs or guarantees. Exact package versions and provider setup belong in dated companion instructions verified when the labs are authored.

## Data and interface responsibilities

The planned corpus includes fictional product documentation with versions, effective dates, stable source anchors, access scopes, and revision history. It must contain outdated advice, conflicting versions, missing answers, ambiguous requests, corrupted extraction, and deliberately adversarial text. Customer and ticket records belong to two or more fictional tenants so isolation is demonstrable.

The companion implementation should provide these narrow boundaries:

- Model access accepts a task request and returns output, usage, timing, model identity, and a typed failure when applicable. A recorded fixture is identified as replay, not live inference.
- Retrieval accepts the question and an application-supplied identity scope and returns evidence with document identity, version, and source location. The model does not choose its own authorization scope.
- Ticket tools receive application-authenticated identity, validated arguments, and operation identifiers. Mutations return enough information for independent state verification.
- Evaluation records the case, system version, trial, checks, grader version, outcome, resources, and relevant error classification. Trial environments are reset between runs.
- Persistent progress distinguishes proposed work, attempted actions, verified outcomes, and unresolved tasks. Resumption reconciles the record with authoritative state.

These responsibilities are part of the blueprint. Detailed API schemas and wire formats are left to companion implementation after the selected technologies are documented and verified.

## Dataset development and separation

Author a small development collection first, then expand it as new capabilities appear. Preserve separately managed development, regression, challenge, and final acceptance collections, with documented purposes. Reuse across collections only when disclosed; the final acceptance collection must not be used for prompt, model, or grader tuning.

Proposed teaching-scale targets are 60 development requests for the first feature, 120 labeled retrieval questions for knowledge work, and 200 fresh final acceptance requests. These counts are planning targets, not evidence that the resulting sample proves production reliability. The final allocation must cover important errors, permission boundaries, and answerable and unanswerable cases. Group duplicate conversations and related customers when splitting where necessary to prevent leakage.

Each case needs an identifier, input, relevant context, reference outcome or rubric, provenance, capability tags, split assignment, and annotation notes. Document label ambiguity and adjudication. Keep expected outcomes and grader internals inaccessible to the agent during its trial. Do not invent human agreement measurements before annotations have actually been compared.

## Milestones and their review evidence

### Measurable feature through Chapter 10

The service classifies and extracts fields, rejects invalid outputs, and compares a rules baseline with model candidates. Required evidence includes the problem brief, development set, initial traces, prompt versions, confusion matrices, error taxonomy, grader checks, and a selection decision. The candidate may be rejected if the baseline is adequate or constraints are not met.

### Knowledge assistance through Chapter 14

The service ingests scoped documentation and answers with inspectable supporting evidence. Required evidence includes corpus versioning, update/deletion demonstrations, retrieval comparisons, claim-support checks, abstention analysis, and memory correction/deletion tests. Measure retrieval and generation separately before interpreting end-to-end outcomes.

### Controlled actions through Chapter 16

The service routes tickets and creates reviewable drafts with enforced identity and permissions. Required evidence includes tool contracts, a workflow state diagram, operation identifiers, interruption recovery, rejection of unauthorized actions, and independent verification that each intended mutation occurred once.

### Bounded investigation through Chapter 19

An agent can investigate an unresolved request using approved tools, produce a draft, or escalate. Required evidence includes action/time/spending budgets, stopping rules, isolated trials, external outcome checks, and a comparison with the explicit workflow. Delegation is retained only when its measured benefit justifies its overhead.

### Operable system through Chapter 28

The service has reproducible releases, monitored quality, recovery paths, a threat model, and a fresh acceptance report. The model-adaptation and multimodal labs supply additional evidence but need not both become permanent production dependencies. Required evidence includes a release manifest, rollback rehearsal, incident report, cost analysis, human-recovery walkthrough, and explicit limitations.

## Proposed educational acceptance targets

The following values are authoring defaults for the fictional support application. Validate their feasibility when producing real labs. If they change, document the reason before evaluating the final candidate; never quietly relax them to fit observed results. They are neither measured performance nor universal production standards.

| Behavior | Initial teaching target | Required interpretation |
| --- | --- | --- |
| Ticket classification | Macro F1 of at least 0.85 on the final labeled classification subset | Report class counts, per-class scores, uncertainty, and baseline comparison |
| Structured extraction | At least 0.90 exact field accuracy for fields with determinate references | Report unknown and ambiguous fields separately and inspect critical identifier errors |
| Retrieval | Recall at 5 of at least 0.90 on answerable retrieval cases | Define relevant evidence and report results by query type |
| Grounded answers | At least 0.95 supported factual claims under a validated rubric | Also report answer completeness and abstention so silence cannot game the metric |
| Unanswerable requests | At least 0.90 appropriate abstention or escalation | Also report false abstentions on answerable requests |
| Action authorization | Zero unauthorized mutations in the complete boundary suite | A finite suite provides bounded evidence and does not prove security immunity |
| Recovery | No duplicate mutations or lost accepted work in the fault-injection suite | Verify actual state after timeout, retry, restart, and rollback |
| Resource control | Every tested run respects configured action and spending caps and stops within the documented timeout/cancellation policy | Include retries, concurrent work, and reservation of costs for in-flight calls |

For timing, begin with a teaching objective of p95 completion within 10 seconds for the single-call triage path and within 20 seconds for the knowledge-answer path at the companion lab's declared concurrency. The investigation agent has an initial two-minute run limit. Record hardware, network, provider, model, and concurrency; revise these authoring assumptions transparently if measured feasibility requires it.

Set a per-exercise spending cap in configuration before any paid call. The exact amount depends on dated prices and the selected lab model, so it must be set during lab authoring rather than guessed here. The capstone report must include cost per successful task and human-review assumptions, not merely token costs.

Use repeated trials for the bounded-agent subset, initially five runs per scenario, and report all results. Calculate uncertainty with a method that respects repeated trials of the same case. Do not treat those trials as five unrelated task samples or claim that these sample sizes establish rare-event safety.

## Failure exercises required across the book

| Scenario | Chapters | Observable check |
| --- | --- | --- |
| Missing evidence | 11, 13 | The system abstains or requests useful clarification |
| Conflicting documents | 11, 13 | The answer resolves version scope or exposes the conflict |
| Malformed or semantically invalid output | 3, 7 | Invalid data does not enter authoritative application state |
| Permission changes | 11, 15, 23 | Revoked data cannot be retrieved or reused from cache or memory |
| Duplicate execution attempt | 16, 19 | Actual state reflects at most one intended mutation |
| Interrupted work | 16, 18, 25 | Resumption reconciles progress with actual state |
| Prompt injection | 15, 23 | Untrusted content cannot grant authority or bypass enforced controls |
| Provider failure | 3, 25, 26 | Failure is recorded and the user receives a recoverable outcome |
| Budget exhaustion | 17, 27 | Work stops and completed versus unresolved work remains inspectable |
| Model upgrade regression | 10, 25, 28 | The fresh comparison detects the regression and supports rollback |
| Misleading grader | 9, 19 | Human-reference comparison exposes grader error |
| Ineffective human review | 24 | The walkthrough reveals whether a reviewer can recognize and correct the error |

## Capstone evidence package

The final submission must contain a problem brief and architecture decisions; a data record with provenance, permissions, splits, and versions; an evaluation report with grader validation and uncertainty; a release manifest; representative traces; a threat model; a resource budget and cost analysis; operating and incident procedures; a recovery demonstration; and a user-facing account of limitations and escalation paths.

Assess six dimensions on a 0–3 scale: problem framing, data and measurement, implementation and authority, reliability and operations, human responsibility, and independent explanation. A score of 0 means absent evidence; 1 means an unsupported assertion or demonstration alone; 2 means reproducible evidence with stated limitations; 3 means reproducible evidence plus independent challenge, failure analysis, and a defended decision. Require at least 2 in every dimension, with no unresolved critical authorization or data-integrity failure in any proposed release.

A supported no-release decision can satisfy the educational capstone when the reader diagnoses the failure, demonstrates the relevant controls, and supplies a concrete remediation or restricted-use plan. It does not count as a successful production release. Record educational completion and deployment readiness separately.

For independent explanation, ask the reader to trace one request, reproduce one comparison, diagnose an unfamiliar failure, and explain one rejected alternative. AI assistance may be used during development, but generated prose alone cannot establish the reader's understanding.

## Companion repository specification

The future companion repository should contain chapter checkpoints, a stable starting application, documented fictional data, separate evaluation collections, deliberately broken exercises, corrected reference implementations, model adapters, a fixture replay mode, evaluation runners, release manifests, and deployment examples. Each checkpoint must map back to the chapter's prerequisites and completion evidence.

Core labs should run on a laptop with bounded model access. Clearly label cloud, hardware, or paid-service requirements for advanced labs. Supply inspectable recorded results where an expensive experiment is optional, and identify the originating code, inputs, model version, date, and environment. If an experiment has not been run, label it as an exercise specification instead of providing invented measurements.

Do not create placeholder test results or empty checkpoint directories as evidence of companion completion. Build and verify each checkpoint when its chapter is authored. Maintain the teaching material through explicit versioned releases so readers can reproduce historical results even as live services change.

## Appendix briefs

### Python bridge

Provide a concise bridge for experienced programmers: environments, typing, data structures, exceptions, asynchronous I/O, numerical arrays, serialization, and test execution. Use it to remove ecosystem friction without reteaching programming. Keep changing installation commands in companion instructions.

### Mathematical reference

Provide notation and worked examples for vectors, matrices, dot products, probability, conditional probability, expectation, variance, logarithms, loss, gradients, precision, recall, F1, sampling intervals, and paired comparisons. Cross-reference the chapter where each concept first affects a decision.

### Terminology glossary

Define model, parameter, token, embedding, training, inference, context, retrieval, grounding, hallucination, adaptation, workflow, agent, harness, tool, evaluation, grader, verification, calibration, and drift. Record overloaded terms and distinguish authoritative application state from model-visible history.

### Engineering templates

Supply problem briefs, architecture decisions, dataset records, evaluation reports, grader-calibration records, threat models, release decisions, and incident reviews. Each template should ask for evidence and limitations and include a completed fictional example, clearly separated from real measured results.

### Advanced pathways

Offer deeper labs for a small transformer, optimization mathematics, preference training, distributed inference, graph-based retrieval, and browser or computer-use agents. Specify prerequisites, compute requirements, expected evidence, and risks. They extend the core learning path and are not required to complete the application-engineering book.

## Drafting sequence and publication checks

Draft Chapters 1–3 and the minimal companion baseline first, then validate the instructional loop with a representative software-engineering reader. Develop foundations and evaluation next, followed by data/context and controlled action. Author specialization labs after the relevant measurement infrastructure exists. Complete operations and the capstone against the same reproducible application.

The 500-page allocation covers main chapters. Front matter, index, references, and appendices are additional; use the remaining space within the approximately 450–550-page editorial range carefully and move expanded reference material to the companion repository if needed. Page budgets are planning estimates, not the length of this blueprint or a guarantee about final typesetting.

Before releasing a chapter, verify that its prerequisite concepts have been introduced; its code checkpoint runs; the failure exercise actually fails for the stated reason; its repair changes the measured outcome; its citations support the relevant claims; and its completion criterion can be assessed by someone other than the author. Check that the laboratory setup does not expose real customer data or perform real external actions unintentionally.

Before publishing the book, run all core checkpoints in a clean documented environment, recheck model and provider details, validate links and source dates, and distinguish observed results from illustrative calculations. Review the complete typeset manuscript for readability, cross-references, accessible figures, equations, tables, and code formatting. The learner standard is demonstrated competence, with no promise of a specific job title.
