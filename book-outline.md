# Detailed chapter outline

This outline specifies 30 chapters in eight parts. Chapter page allocations are estimates for the future manuscript and total 500 pages. They exclude front matter, references, index, and appendices.

Each brief preserves the approved chapter topics and adds the software-engineering connection, prerequisites, a workshop, a failure exercise, and assessable completion evidence. Reading links are sources for the concepts; the proposed exercises are original editorial designs.

| Part | Chapters | Main-text pages |
| --- | --- | --- |
| 1. Entering the discipline | 1–3 | 40 |
| 2. Foundations for engineering judgment | 4–6 | 60 |
| 3. Building an empirical development process | 7–10 | 65 |
| 4. Engineering knowledge and context | 11–14 | 70 |
| 5. Tools, workflows, and agents | 15–19 | 90 |
| 6. Adapting models and expanding capabilities | 20–22 | 60 |
| 7. Operating dependable AI systems | 23–27 | 80 |
| 8. Demonstrating professional competence | 28–30 | 35 |
| Total | 30 chapters | 500 |

## Part 1 — Entering the discipline

Estimated main text: 40 pages.

### Chapter 1 — What an AI Engineer Is Responsible For

**Page allocation:** 12. **Prerequisites:** Existing software-engineering experience.

**Software-engineering connection:** Architecture, ownership, interface design, and operational accountability remain the starting point.

**Topics and learning outcomes**

- Distinguish using AI during software development from building software whose behavior depends on AI.
- Map the overlapping responsibilities of software engineers, AI engineers, ML engineers, data engineers, researchers, and domain specialists.
- Introduce the system lifecycle: problem definition, evidence, implementation, operation, and improvement.
- Explain why a successful demonstration establishes only limited evidence of capability.

**Workshop:** Annotate a support application's architecture and assign responsibility for data, decisions, measurements, user outcomes, and incidents.

**Failure exercise:** A persuasive demonstration answers one question correctly but fails on outdated documentation and has no accountable owner.

**Completion evidence:** Produce an ownership map that covers model behavior and the surrounding system, and explain what the demonstration did and did not establish.

**Further reading:** [AI Engineering](https://www.sei.cmu.edu/artificial-intelligence-engineering/); [The Rise of the AI Engineer](https://www.latent.space/p/ai-engineer); [The Shift from Models to Compound AI Systems](https://bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/); [AI Engineering book and other resources](https://github.com/chiphuyen/aie-book).

### Chapter 2 — Choosing a Problem Worth Solving

**Page allocation:** 14. **Prerequisites:** 1.

**Software-engineering connection:** Requirements analysis becomes the basis for deciding which uncertainty the product can tolerate.

**Topics and learning outcomes**

- Translate a user need into a bounded task with observable outcomes.
- Compare conventional software, search, classical ML, and foundation-model approaches.
- Identify error costs, acceptable latency, human review needs, data availability, and circumstances where automation should stop.
- Separate business success from model metrics and convenient proxies.

**Workshop:** Write the support system's problem brief and compare manual triage, rules, search, and model-powered assistance.

**Failure exercise:** A team maximizes automated ticket closure while customers repeatedly reopen incorrectly resolved tickets.

**Completion evidence:** Specify users, baseline, acceptance criteria, failure costs, and a reasoned proceed, restrict, or reject decision.

**Further reading:** [Framing an ML problem](https://developers.google.com/machine-learning/problem-framing/ml-framing); [AI Engineering](https://www.sei.cmu.edu/artificial-intelligence-engineering/).

### Chapter 3 — Build Your First Measurable AI Feature

**Page allocation:** 14. **Prerequisites:** 2.

**Software-engineering connection:** API integration and defensive programming provide the structure for a minimal experiment.

**Topics and learning outcomes**

- Implement ticket classification and structured extraction through a minimal model integration.
- Introduce prompts, inputs, outputs, validation, timeouts, and basic usage accounting.
- Compare results against a simple conventional baseline.
- Collect representative examples and inspect failures before optimizing.

**Workshop:** Build an offline rules baseline and a separate live-model path for classifying fictional requests and extracting product, issue, and urgency fields.

**Failure exercise:** A valid-looking response invents a customer identifier; another request times out and leaves no recorded result.

**Completion evidence:** Deliver a runnable feature, a small labeled development set, an error report, and measured latency and usage. Mark fixture replay separately from live inference.

**Further reading:** [LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/spring-2023/); [Framing an ML problem](https://developers.google.com/machine-learning/problem-framing/ml-framing).

## Part 2 — Foundations for engineering judgment

Estimated main text: 60 pages.

### Chapter 4 — Probability, Statistics, and Experimental Thinking

**Page allocation:** 20. **Prerequisites:** 3.

**Software-engineering connection:** Testing discipline expands into statistical judgment about populations and repeated measurements.

**Topics and learning outcomes**

- Teach distributions, conditional probability, expectation, variance, and sampling through application examples.
- Explain precision, recall, thresholds, class imbalance, and asymmetric errors.
- Introduce confidence intervals and comparisons between candidate systems.
- Distinguish token likelihood, expressed confidence, and empirical reliability.

**Workshop:** Compare two ticket classifiers using confusion matrices, paired cases, bootstrap intervals, and per-category results.

**Failure exercise:** An apparent improvement comes from a changed traffic mix; a second comes from repeatedly selecting the best result on the same test set.

**Completion evidence:** Explain both misleading comparisons, define the unit of sampling, report uncertainty, and defend a valid experiment.

**Further reading:** [Machine Learning Crash Course prerequisites and prework](https://developers.google.com/machine-learning/crash-course/prereqs-and-prework).

### Chapter 5 — Machine Learning Fundamentals for Software Engineers

**Page allocation:** 18. **Prerequisites:** 4.

**Software-engineering connection:** Debugging and data modeling become tools for understanding what a model learns.

**Topics and learning outcomes**

- Explain parameters, objectives, loss, optimization, training, and inference.
- Introduce generalization, overfitting, regularization, and distribution shift.
- Establish training, development, and test separation; demonstrate leakage.
- Teach vectors, matrices, tensor shapes, and embeddings where the implementation needs them.

**Workshop:** Train a small text classifier, inspect loss and held-out errors, and compare it with the rules baseline.

**Failure exercise:** Near-duplicate conversations or customer-specific labels appear in both training and evaluation data.

**Completion evidence:** Detect leakage, rebuild the split by the relevant grouping unit, and explain the difference between training success and generalization.

**Further reading:** [Machine Learning Crash Course prerequisites and prework](https://developers.google.com/machine-learning/crash-course/prereqs-and-prework); [CS336 Language Modeling from Scratch](https://cs336.stanford.edu/).

### Chapter 6 — How Foundation Models Work—and Fail

**Page allocation:** 22. **Prerequisites:** 5.

**Software-engineering connection:** Mechanistic debugging becomes more effective when the reader understands the model's computational ingredients.

**Topics and learning outcomes**

- Build intuition for tokenization, embeddings, attention, transformers, and next-token prediction.
- Distinguish pretraining, supervised adaptation, preference optimization, and reinforcement learning.
- Explain context limits, decoding, reasoning-oriented inference, and computational tradeoffs.
- Investigate unsupported claims, sensitivity to instructions, knowledge limitations, and inconsistent behavior.

**Workshop:** Inspect tokenization and embedding behavior, trace a small attention example, and compare responses under controlled changes to input and decoding.

**Failure exercise:** A fluent explanation invents a product capability; a longer input causes a previously available fact to be missed.

**Completion evidence:** Connect observations to plausible mechanisms, preserve uncertainty, and avoid treating generated explanations as privileged access to internal computation.

**Further reading:** [CS336 Language Modeling from Scratch](https://cs336.stanford.edu/); [Lost in the Middle: How Language Models Use Long Contexts](https://aclanthology.org/2024.tacl-1.9/); [LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/spring-2023/).

## Part 3 — Building an empirical development process

Estimated main text: 65 pages.

### Chapter 7 — Prompts, Structured Outputs, and Application Contracts

**Page allocation:** 16. **Prerequisites:** 3, 6.

**Software-engineering connection:** Contracts and validation remain essential even when an upstream component returns plausible prose.

**Topics and learning outcomes**

- Design instructions, examples, task boundaries, and output specifications.
- Separate syntactic validity from semantic correctness.
- Handle refusals, missing fields, ambiguity, truncation, and unsupported requests.
- Version prompts and compare changes against evidence.

**Workshop:** Implement extraction with typed output, explicit unknown values, semantic checks, and a versioned prompt comparison.

**Failure exercise:** An output passes JSON validation but associates the request with the wrong tenant or invents a field value.

**Completion evidence:** Demonstrate that malformed and semantically invalid results cannot silently enter application state, and document unresolved ambiguities.

**Further reading:** [LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/spring-2023/); [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents).

### Chapter 8 — Designing Evaluation Data

**Page allocation:** 16. **Prerequisites:** 4, 7.

**Software-engineering connection:** Acceptance testing expands into sampling, annotation, and management of measurement data.

**Topics and learning outcomes**

- Translate requirements and observed failures into evaluation cases.
- Establish reference answers, rubrics, annotation instructions, and disagreement handling.
- Cover representative traffic, difficult cases, important subgroups, and negative examples.
- Protect held-out data and distinguish regression testing from capability exploration.

**Workshop:** Build a documented evaluation collection, with separate development and holdout partitions and an adjudication log for ambiguous labels.

**Failure exercise:** A suite tests when retrieval should occur but contains no cases where retrieval is unnecessary or unauthorized.

**Completion evidence:** Explain sampling choices, label provenance, coverage, intended uses, and limitations so another engineer can maintain the collection.

**Further reading:** [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents); [Model Cards for Model Reporting](https://arxiv.org/abs/1810.03993).

### Chapter 9 — Graders, Experiments, and Error Analysis

**Page allocation:** 18. **Prerequisites:** 8.

**Software-engineering connection:** Debugging now includes checking whether the test instrument itself is wrong.

**Topics and learning outcomes**

- Combine deterministic checks, human assessment, and model-based grading.
- Calibrate judges against human references and inspect disagreement.
- Use controlled comparisons, ablations, repeated trials, and error taxonomies.
- Diagnose whether failures originate in the model, context, data, application, or evaluation.

**Workshop:** Implement outcome checks and a rubric-based grader; compare grader decisions with human labels and reverse pairwise answer order.

**Failure exercise:** A judge prefers longer answers even when they contain unsupported claims; aggregate scores conceal a critical-category regression.

**Completion evidence:** Report judge agreement and error types, validate the comparison, and justify the next engineering change rather than merely report a score.

**Further reading:** [Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena](https://arxiv.org/abs/2306.05685); [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents).

### Chapter 10 — Selecting Models and System Approaches

**Page allocation:** 15. **Prerequisites:** 9.

**Software-engineering connection:** Architecture decision records gain task-specific behavioral evidence.

**Topics and learning outcomes**

- Construct a task-specific comparison across quality, latency, cost, operational constraints, and data handling.
- Distinguish hosted access, available weights, licensing, and deployment responsibility.
- Use public benchmarks as discovery signals and local evaluations as decision evidence.
- Decide whether a failure calls for better instructions, retrieval, tools, adaptation, or a different task design.

**Workshop:** Compare at least two candidates and the baseline using the same application cases and explicit constraints.

**Failure exercise:** A model with a stronger public benchmark performs worse on the support team's terminology or deployment requirements.

**Completion evidence:** Write a model-selection decision record, state evidence gaps, and define checks for future migrations. Recheck actual terms during implementation.

**Further reading:** [AI Engineering book and other resources](https://github.com/chiphuyen/aie-book); [The Shift from Models to Compound AI Systems](https://bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/); [Model Cards for Model Reporting](https://arxiv.org/abs/1810.03993).

## Part 4 — Engineering knowledge and context

Estimated main text: 70 pages.

### Chapter 11 — Data Engineering for AI Applications

**Page allocation:** 16. **Prerequisites:** 8, 10.

**Software-engineering connection:** ETL, database integrity, and access control become determinants of answer quality.

**Topics and learning outcomes**

- Build ingestion, parsing, normalization, deduplication, and versioning pipelines.
- Preserve document structure, source identifiers, provenance, and update history.
- Carry access permissions into downstream retrieval and storage.
- Handle deletions, stale content, conflicting sources, and corrupted documents.

**Workshop:** Ingest a versioned fictional documentation corpus and retain tenant scope, effective dates, source anchors, and deletion records.

**Failure exercise:** A deleted article remains in the index, or parsing separates a warning from the procedure it qualifies.

**Completion evidence:** Produce an inspectable corpus and demonstrate correct propagation of updates, deletions, and permission changes.

**Further reading:** [AI Engineering book and other resources](https://github.com/chiphuyen/aie-book); [Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence).

### Chapter 12 — Retrieval and Search Fundamentals

**Page allocation:** 18. **Prerequisites:** 5, 11.

**Software-engineering connection:** Search indexing and performance measurement extend to semantic representations.

**Topics and learning outcomes**

- Explain lexical search, dense embeddings, similarity, approximate search, and hybrid retrieval.
- Explore chunking, metadata filters, query rewriting, and reranking.
- Measure retrieval separately from generated answers.
- Diagnose vocabulary mismatch, weak coverage, distractors, and inappropriate filtering.

**Workshop:** Compare lexical, dense, and hybrid retrieval on labeled questions, using recall at a fixed cutoff and ranked relevance measures.

**Failure exercise:** Exact error codes disappear under semantic matching, while paraphrased questions defeat a lexical-only baseline.

**Completion evidence:** Identify the errors each strategy fixes or introduces and preserve permission filtering throughout the comparison.

**Further reading:** [Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](https://arxiv.org/abs/2005.11401); [Long Context vs. RAG for LLMs: An Evaluation and Revisits](https://arxiv.org/abs/2501.01880).

### Chapter 13 — Retrieval-Augmented Generation and Context Construction

**Page allocation:** 20. **Prerequisites:** 9, 12.

**Software-engineering connection:** Dependency management now includes the evidence supplied to the model.

**Topics and learning outcomes**

- Assemble questions, instructions, retrieved evidence, and output requirements into useful context.
- Connect generated claims to supporting passages.
- Handle insufficient evidence, contradictory sources, and unanswerable questions.
- Compare retrieval, long-context input, and hybrid approaches under a common evaluation.

**Workshop:** Add document-grounded answers with source anchors; separately score retrieval, claim support, completeness, and abstention.

**Failure exercise:** A real citation does not support its adjacent claim, or two valid documents describe different product versions.

**Completion evidence:** Produce supported answers, abstain appropriately, and defend the context strategy under measured quality and resource constraints.

**Further reading:** [Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](https://arxiv.org/abs/2005.11401); [Retrieval Augmented Generation or Long-Context LLMs? A Comprehensive Study and Hybrid Approach](https://aclanthology.org/2024.emnlp-industry.66/); [Long Context vs. RAG for LLMs: An Evaluation and Revisits](https://arxiv.org/abs/2501.01880).

### Chapter 14 — Conversation State, Memory, and Context Lifecycles

**Page allocation:** 16. **Prerequisites:** 13.

**Software-engineering connection:** State modeling and retention rules remain distinct from the model's text history.

**Topics and learning outcomes**

- Distinguish conversation history, application state, saved preferences, retrieved knowledge, and learned parameters.
- Design memory creation, retrieval, correction, expiration, and deletion.
- Compare summarization, selection, and reconstruction of context.
- Test whether important information survives long interactions and whether obsolete information persists.

**Workshop:** Implement inspectable session memory, user corrections, expiration, and reconstruction from authoritative application records.

**Failure exercise:** A compressed history loses a user constraint, or an outdated preference survives an explicit correction.

**Completion evidence:** Show correction and deletion working across subsequent calls; document what compaction preserves, loses, and cannot establish.

**Further reading:** [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents); [Lost in the Middle: How Language Models Use Long Contexts](https://aclanthology.org/2024.tacl-1.9/).

## Part 5 — Tools, workflows, and agents

Estimated main text: 90 pages.

### Chapter 15 — Designing Tools for Model Callers

**Page allocation:** 17. **Prerequisites:** 7, 14.

**Software-engineering connection:** API contracts, authorization, and least privilege constrain a new kind of caller.

**Topics and learning outcomes**

- Define clear tool purposes, arguments, results, and error behavior.
- Distinguish read operations, reversible changes, and consequential actions.
- Enforce authorization, validation, and scoped credentials in application code.
- Introduce tool interoperability and explain what a protocol does—and does not—guarantee.

**Workshop:** Expose ticket lookup and draft creation with explicit tenant identity, permission checks, validation, and auditable results.

**Failure exercise:** The model supplies another tenant's identifier or treats a tool's descriptive text as permission to perform an action.

**Completion evidence:** Demonstrate rejection of unauthorized requests and invalid arguments independently of prompt compliance.

**Further reading:** [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents); [OWASP GenAI LLM Top 10 2026](https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/).

### Chapter 16 — Reliable Model-Powered Workflows

**Page allocation:** 18. **Prerequisites:** 15.

**Software-engineering connection:** State machines and distributed-systems recovery provide explicit control over uncertain steps.

**Topics and learning outcomes**

- Combine models with explicit routing, state machines, parallel steps, and validation.
- Handle retries, idempotency, timeouts, partial completion, and compensation.
- Place human review at defined decision points.
- Select model-driven decisions only where they provide measurable value.

**Workshop:** Build a triage-to-draft workflow with review and restartable steps, using a simulated ticket service for mutations.

**Failure exercise:** A service commits an action but the response times out; blindly retrying would duplicate the action.

**Completion evidence:** Demonstrate interruption recovery, stable operation identifiers, and verified outcomes without duplicated side effects.

**Further reading:** [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents); [The Shift from Models to Compound AI Systems](https://bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/).

### Chapter 17 — Agent Loops and Harness Engineering

**Page allocation:** 20. **Prerequisites:** 16.

**Software-engineering connection:** Runtime design expands to governing model-selected actions and resource consumption.

**Topics and learning outcomes**

- Explain the interaction among model, tools, observations, state, and stopping conditions.
- Define the harness's responsibility for execution, permissions, resources, and recovery.
- Introduce planning, replanning, bounded exploration, and escalation.
- Compare a bounded agent with the existing explicit workflow.

**Workshop:** Build an investigation agent that can inspect approved documentation and ticket state, create a draft, and escalate unresolved work.

**Failure exercise:** The agent loops after receiving no useful new evidence or attempts to act after exhausting its budget.

**Completion evidence:** Enforce action, time, and spending limits in code and measure whether flexibility improves completion under comparable constraints.

**Further reading:** [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents); [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents).

### Chapter 18 — Long-Running Work and Multiple Agents

**Page allocation:** 19. **Prerequisites:** 17.

**Software-engineering connection:** Checkpointing, concurrency, and ownership become essential for continuity and coordination.

**Topics and learning outcomes**

- Persist goals, progress, artifacts, and checkpoints across sessions.
- Reconstruct context and reconcile recorded progress with actual environment state.
- Evaluate delegation, parallel research, specialization, and shared-state coordination.
- Diagnose duplicated work, conflicting results, communication overhead, and cascading failures.

**Workshop:** Resume a stopped investigation and compare a single investigator with bounded delegated research under the same total resource budget.

**Failure exercise:** Two workers duplicate a task or a resumed agent trusts a progress note that conflicts with the actual ticket state.

**Completion evidence:** Recover coherently, resolve conflicting work, and report both task outcomes and coordination overhead without assuming delegation is superior.

**Further reading:** [Effective harnesses for long-running agents](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents); [How we built our multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system).

### Chapter 19 — Evaluating Agents and Verifying Actions

**Page allocation:** 16. **Prerequisites:** 9, 18.

**Software-engineering connection:** End-to-end tests expand to repeated trials and inspection of external outcomes.

**Topics and learning outcomes**

- Measure completion, prohibited actions, resource use, and consistency across trials.
- Distinguish useful trajectory inspection from unnecessarily prescribing every step.
- Verify actual database or environment changes independently of the agent's narration.
- Build isolated test environments and examine simulator and grader limitations.

**Workshop:** Run isolated agent trials with outcome checks, authorization checks, and a calibrated communication rubric.

**Failure exercise:** An agent reports success without changing state; another achieves the requested state through an unauthorized action.

**Completion evidence:** Detect both failures and distinguish first-attempt success, success with retries, and consistency across trials.

**Further reading:** [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents); [Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena](https://arxiv.org/abs/2306.05685).

## Part 6 — Adapting models and expanding capabilities

Estimated main text: 60 pages.

### Chapter 20 — Fine-Tuning, Distillation, and Model Adaptation

**Page allocation:** 22. **Prerequisites:** 5, 9, 10.

**Software-engineering connection:** Controlled releases and data discipline govern changes to model parameters.

**Topics and learning outcomes**

- Determine whether an observed problem justifies changing model parameters.
- Prepare adaptation data and protect independent evaluation.
- Explain supervised fine-tuning, parameter-efficient adaptation, distillation, and preference-based methods.
- Measure improvements alongside regressions, maintenance burden, and operational cost.

**Workshop:** Adapt a small model for one support task or analyze supplied reproducible experiment records, comparing it with prompting and the original model.

**Failure exercise:** Task-specific accuracy improves while unsupported answers increase or training examples leak into evaluation.

**Completion evidence:** Defend adoption or rejection using independent results and maintenance costs; distinguish executed training from analysis of recorded results.

**Further reading:** [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685); [CS336 Language Modeling from Scratch](https://cs336.stanford.edu/); [AI Engineering book and other resources](https://github.com/chiphuyen/aie-book).

### Chapter 21 — Inference and Hosting Fundamentals

**Page allocation:** 20. **Prerequisites:** 6, 10, 20.

**Software-engineering connection:** Capacity planning and profiling apply to model memory and token generation.

**Topics and learning outcomes**

- Explain memory requirements, numerical precision, quantization, and hardware constraints.
- Introduce prefill, decoding, caching, batching, throughput, and tail latency.
- Compare managed inference with operating available model weights.
- Profile the actual workload before selecting optimizations.

**Workshop:** Benchmark a small model or a supplied deployment environment across input lengths and concurrency levels, retaining quality checks.

**Failure exercise:** A configuration improves throughput while making interactive tail latency unacceptable, or reduces memory at the expense of task quality.

**Completion evidence:** Identify the limiting resource and justify a deployment configuration with measured tradeoffs and clear hardware assumptions.

**Further reading:** [CS336 Language Modeling from Scratch](https://cs336.stanford.edu/); [A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues).

### Chapter 22 — Multimodal Systems: Documents, Images, Audio, and Video

**Page allocation:** 18. **Prerequisites:** 6, 9, 13.

**Software-engineering connection:** Media pipelines introduce new input quality, alignment, and evaluation responsibilities.

**Topics and learning outcomes**

- Extend the application to screenshots, scanned documents, and recorded support messages.
- Compare direct multimodal processing with OCR, transcription, and specialist components.
- Handle temporal alignment, missing modalities, image quality, and streaming interactions.
- Introduce generated media, provenance, consent, and modality-specific evaluation.

**Workshop:** Build a document-understanding extension; use a separate audio exercise to examine transcription and timing errors. Keep advanced video work in companion material.

**Failure exercise:** A text shortcut makes an image benchmark look successful even though the model ignores the image; a scan obscures a critical qualifier.

**Completion evidence:** Evaluate cases that require visual evidence, identify modality-specific errors, and trace output claims to the correct page, region, or time interval.

**Further reading:** [MMMU-Pro: A More Robust Multi-discipline Multimodal Understanding Benchmark](https://arxiv.org/abs/2409.02813); [Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence).

## Part 7 — Operating dependable AI systems

Estimated main text: 80 pages.

### Chapter 23 — Security and Trust Boundaries

**Page allocation:** 18. **Prerequisites:** 15, 19.

**Software-engineering connection:** Threat modeling and defense in depth extend across model-visible content and tool execution.

**Topics and learning outcomes**

- Threat-model prompts, retrieved documents, tool responses, dependencies, and generated outputs.
- Address injection, information disclosure, unsafe output handling, excessive authority, and resource exhaustion.
- Apply isolation, least privilege, secret protection, egress controls, and output validation.
- Test defenses against realistic application-level attacks.

**Workshop:** Attack and harden the fictional support service with malicious documents, cross-tenant requests, and unsafe output handling cases.

**Failure exercise:** A retrieved article instructs the agent to disclose private ticket content through an external tool.

**Completion evidence:** Show which attacks are prevented by enforced boundaries, record residual risks, and avoid claiming that finite testing proves immunity.

**Further reading:** [OWASP GenAI LLM Top 10 2026](https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/); [Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence).

### Chapter 24 — Human Interaction and Responsible Product Design

**Page allocation:** 16. **Prerequisites:** 2, 19, 23.

**Software-engineering connection:** User experience and accountability become part of the system's error-handling design.

**Topics and learning outcomes**

- Communicate capabilities and limitations in ways that help users act.
- Support correction, dismissal, escalation, cancellation, and recovery.
- Evaluate automation bias, inappropriate reliance, subgroup performance, and accessibility.
- Define accountable ownership and collaborate with privacy, legal, security, and domain specialists.

**Workshop:** Conduct a structured user walkthrough with a wrong answer, an ambiguous draft, and an interrupted task requiring human recovery.

**Failure exercise:** A nominal review step provides neither the evidence nor the controls a reviewer needs to catch an error.

**Completion evidence:** Demonstrate usable correction and recovery, identify affected users, and document unresolved risks and responsible owners.

**Further reading:** [Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/); [Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence); [AI Engineering](https://www.sei.cmu.edu/artificial-intelligence-engineering/).

### Chapter 25 — Production Architecture and Release Engineering

**Page allocation:** 17. **Prerequisites:** 16, 21, 23, 24.

**Software-engineering connection:** Release engineering must account for behavioral dependencies beyond application code.

**Topics and learning outcomes**

- Separate interactive requests, background jobs, ingestion, model access, and evaluation.
- Version code, prompts, models, retrieval indexes, and relevant configuration together.
- Design resource limits, graceful degradation, tenancy boundaries, and failure containment.
- Release through staged exposure with behavioral checks and rollback procedures.

**Workshop:** Package the support service with a release manifest and stage a candidate against a stable baseline in an isolated environment.

**Failure exercise:** A prompt update works with a new index but is accidentally deployed with the old one, or rollback would invalidate active work.

**Completion evidence:** Reproduce a release and rehearse a failed rollout while preserving user work and compatible state.

**Further reading:** [LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/spring-2023/); [A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues); [The Shift from Models to Compound AI Systems](https://bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/).

### Chapter 26 — Observability, Debugging, and Incident Response

**Page allocation:** 16. **Prerequisites:** 25.

**Software-engineering connection:** Tracing and incident analysis now include behavioral quality and sensitive context.

**Topics and learning outcomes**

- Trace requests across model calls, retrieval, tools, and state changes.
- Monitor outcome quality alongside availability and performance.
- Collect useful diagnostics while controlling sensitive-data exposure and retention.
- Reproduce failures, identify causes, respond to incidents, and turn findings into regression cases.

**Workshop:** Investigate a planted routing or retrieval regression using versioned traces, user reports, and production-like evaluation.

**Failure exercise:** Availability remains healthy while a subset of users receives worse answers; indiscriminate logging would expose private data.

**Completion evidence:** Write a postmortem supported by evidence, demonstrate recovery, and add a targeted regression case without retaining unnecessary sensitive content.

**Further reading:** [A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues); [Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence).

### Chapter 27 — Economics and Continuous Optimization

**Page allocation:** 13. **Prerequisites:** 9, 21, 26.

**Software-engineering connection:** Performance engineering expands to total cost of successful service.

**Topics and learning outcomes**

- Measure total cost per successfully completed task, including retries and human review.
- Compare caching, routing, smaller models, batching, and reduced context.
- Optimize quality, latency, and cost together; account for maintenance and resource consumption.
- Reevaluate earlier optimizations when models, traffic, or requirements change.

**Workshop:** Compare measured operating points for the support service and select an optimization subject to an explicit quality constraint.

**Failure exercise:** Lower token cost increases review work, or cached answers survive a documentation or permission change.

**Completion evidence:** Demonstrate a defensible improvement on held-out cases, count failed work, and state assumptions and uncertainty in cost estimates.

**Further reading:** [FrugalGPT: How to Use Large Language Models While Reducing Cost and Improving Performance](https://arxiv.org/abs/2305.05176); [Retrieval Augmented Generation or Long-Context LLMs? A Comprehensive Study and Hybrid Approach](https://aclanthology.org/2024.emnlp-industry.66/).

## Part 8 — Demonstrating professional competence

Estimated main text: 35 pages.

### Chapter 28 — Capstone: From Working Application to Defensible System

**Page allocation:** 16. **Prerequisites:** 19, 20, 22, 27.

**Software-engineering connection:** Engineering review joins implementation, experimental evidence, and operational responsibility.

**Topics and learning outcomes**

- Consolidate the application's requirements, architecture, data, evaluations, and operational controls.
- Run a fresh acceptance set that includes ordinary work and difficult scenarios.
- Conduct security, interruption, recovery, and model-change exercises.
- Present remaining limitations and make a supported release decision.

**Workshop:** Assemble the complete capstone evidence package and conduct an independent design and release review.

**Failure exercise:** The application passes a curated demo but fails fresh cases, exceeds its operating budget, or lacks a recovery path.

**Completion evidence:** Meet the published educational acceptance rubric or defend a restricted deployment or no-release decision with a remediation plan.

**Further reading:** [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents); [Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence); [Model Cards for Model Reporting](https://arxiv.org/abs/1810.03993).

### Chapter 29 — Working Effectively on an AI Engineering Team

**Page allocation:** 10. **Prerequisites:** 28.

**Software-engineering connection:** Collaboration and review incorporate data, graders, and model behavior as maintained assets.

**Topics and learning outcomes**

- Assign responsibility for product outcomes, datasets, evaluations, infrastructure, and incidents.
- Review changes to prompts, data, graders, tools, and models.
- Collaborate with domain experts to resolve ambiguous requirements and labels.
- Maintain decision records and prioritize work from observed failures.

**Workshop:** Review a proposed model upgrade with a domain reviewer, application owner, and operations owner; make the evidence and disagreement explicit.

**Failure exercise:** A team improves an evaluation score by changing the grader at the same time as the model, leaving the result uninterpretable.

**Completion evidence:** Lead a review that separates changes, resolves or records disagreements, and assigns accountable next actions.

**Further reading:** [AI Engineering](https://www.sei.cmu.edu/artificial-intelligence-engineering/); [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents).

### Chapter 30 — Building Your Career and Continuing to Learn

**Page allocation:** 9. **Prerequisites:** 29.

**Software-engineering connection:** Professional judgment is demonstrated through explainable decisions and reproducible work.

**Topics and learning outcomes**

- Assess competence through systems built, failures diagnosed, and decisions defended.
- Present a portfolio with reproducible experiments and operational evidence.
- Read papers critically: task, baseline, method, result, limitations, and applicability.
- Choose deeper paths in retrieval, evaluation, agent systems, model adaptation, inference infrastructure, multimodal systems, or security.

**Workshop:** Write a portfolio case study and evaluate one new research result for relevance to the support application's observed failure modes.

**Failure exercise:** A portfolio presents a polished interface and benchmark headline but cannot explain the data, experiments, or deployment limitations.

**Completion evidence:** Demonstrate independent understanding and produce a learning plan linked to observed skill gaps, without claiming a guaranteed job outcome.

**Further reading:** [AI Engineering book and other resources](https://github.com/chiphuyen/aie-book); [CS336 Language Modeling from Scratch](https://cs336.stanford.edu/); [AI Engineering](https://www.sei.cmu.edu/artificial-intelligence-engineering/).
