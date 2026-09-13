# Research foundation

The book teaches experienced software engineers to take responsibility for systems whose behavior depends on foundation models. Its intended reader can already program, test, debug, work with APIs and databases, and deploy ordinary applications. The learning path adds model understanding, data and experimental judgment, context construction, controlled action, and operational responsibility.

The professional outcome is concrete: given a real problem, the reader can choose an appropriate approach, define success, build and improve the system, constrain its authority, and operate it with evidence of acceptable behavior. This is an educational standard chosen for the book. It is not a universal credential or a promise of employment.

Research was consulted on September 5, 2026. Publication and update dates remain separate from access dates. The chapter sequence, fictional application, page allocations, workshops, and assessment targets are editorial recommendations derived from the evidence, rather than experimentally validated instructional prescriptions.

## The discipline and its boundaries

The Software Engineering Institute describes AI engineering as a broad combination of systems engineering, software engineering, computer science, and human-centered design, organized around human-centered, scalable, and robust and secure AI. The book adopts that concern for complete systems while focusing its practical work on applications built around foundation models. [CMU SEI AI Engineering](https://www.sei.cmu.edu/artificial-intelligence-engineering/).

Shawn Wang's 2023 essay describes the emergence of a foundation-model application specialty and acknowledges that boundaries between model and application work are permeable. It is useful evidence of professional framing, not a basis for current salary or employment forecasts. The book therefore treats role titles as overlapping responsibilities and avoids implying that classical ML work falls outside the broader discipline. [The Rise of the AI Engineer](https://www.latent.space/p/ai-engineer).

Berkeley's compound-systems perspective explains why the model alone is an insufficient unit of design: retrieval, tools, code, and repeated model calls interact to produce behavior. The instructional consequence is to teach component measurement and system-level judgment together. Direct access to this article timed out during research; substantial publisher-indexed text supplied its definition and design discussion. [The Shift from Models to Compound AI Systems](https://bair.berkeley.edu/blog/2024/02/18/compound-ai-systems/).

Chip Huyen's author-maintained description of AI Engineering establishes a closely related reference work covering foundation-model applications. It explicitly states that it is not a tutorial book. The proposed textbook's distinguishing contribution is the transition curriculum: progressive implementation, failure diagnosis, and observable competency milestones. This positioning is an editorial choice, not a claim that no other practical books exist. [AI Engineering book and resources](https://github.com/chiphuyen/aie-book).

## Accessible entry with substantive foundations

Google's introductory ML curriculum does not require previous ML knowledge. It expects programming and basic quantitative literacy and labels calculus optional for advanced topics. Stanford's Spring 2026 language-model construction course expects deeper mathematics, ML, and systems experience. These are different educational scopes, not conflicting accounts of a single prerequisite standard. [Google ML Crash Course prerequisites](https://developers.google.com/machine-learning/crash-course/prereqs-and-prework), [Stanford CS336](https://cs336.stanford.edu/).

The book consequently introduces a working feature early, then teaches the mathematics and ML concepts needed to investigate it. Probability, sampling, leakage, generalization, loss, embeddings, and model behavior are required core material. Full transformer construction, advanced optimization, and distributed training remain deeper pathways. The precise division is an editorial synthesis.

Full Stack Deep Learning's 2023 bootcamp combines applications, model foundations, prompting, augmented models, user experience, and operations. Its scope supports teaching the full lifecycle, while its age makes it unsuitable for selecting today's preferred tooling. Google's problem-framing guidance supplies the distinction between product outcomes, model tasks, and business metrics that anchors the opening project. [LLM Bootcamp](https://fullstackdeeplearning.com/llm-bootcamp/spring-2023/), [Framing an ML problem](https://developers.google.com/machine-learning/problem-framing/ml-framing).

## Evaluation and verification as recurring practices

Anthropic's 2026 engineering guidance distinguishes a task, a trial, a grader, a transcript, and the resulting environment state. This supports teaching evaluation from the first feature and later verifying whether agent actions actually occurred. The book's agent exercises distinguish what the system says from what the ticket database records. [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents).

Zheng and colleagues investigated model judges as approximations to human preference and documented position, verbosity, self-enhancement, and reasoning limitations. The book uses these findings to motivate judge calibration and disagreement analysis. Agreement with preferences is not equivalent to factual correctness or reliability on a new task. [Judging LLM-as-a-Judge](https://arxiv.org/abs/2306.05685).

Model Cards proposes reporting intended uses and performance under relevant conditions. That principle informs the capstone's explicit account of appropriate use, evaluation coverage, and limitations. Documentation accompanies the evidence; it does not substitute for it. [Model Cards for Model Reporting](https://arxiv.org/abs/1810.03993).

## Context and architecture choices require comparison

The original RAG paper combines parametric and retrieved non-parametric memory. Its trained architecture provides historical grounding, while contemporary application pipelines should be explained on their own terms. [Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](https://arxiv.org/abs/2005.11401).

Research comparing retrieval and long-context approaches reports tradeoffs that depend on tasks, methods, and resource constraints. A later evaluation revisits context relevance and retrieval choices, finding differences across question types. The book therefore requires an application-level comparison rather than asserting that one architecture always wins. [RAG or Long-Context LLMs](https://aclanthology.org/2024.emnlp-industry.66/), [Long Context vs RAG revisited](https://arxiv.org/abs/2501.01880).

Lost in the Middle identifies position-sensitive use of information in the models and tasks studied. Anthropic's context-engineering guidance treats instructions, tools, external data, and history as a managed resource and discusses compaction and persistent notes. Together they motivate experiments on context relevance, information preservation, and stale memory without asserting an identical limitation for every future model. [Lost in the Middle](https://aclanthology.org/2024.tacl-1.9/), [Effective context engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents).

Anthropic distinguishes explicit workflows from model-directed action and recommends increasing complexity when needed. Its multi-agent research account documents both benefits and coordination/resource burdens. Long-running harness experiments offer coding-specific examples of incremental work and persistent artifacts, with generalization still an open question. The book teaches explicit workflows before agents and asks readers to justify autonomy and delegation with comparable measurements. [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents), [Multi-agent research system](https://www.anthropic.com/engineering/multi-agent-research-system), [Effective harnesses](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents).

## Adaptation and multimodal understanding

LoRA supplies a concrete example of reducing the trainable parameter burden through low-rank adaptation while keeping pretrained weights frozen. It justifies an accessible adaptation lab, not a requirement to fine-tune every application. Stanford's model-building curriculum provides the route into deeper training and inference specialization. [LoRA](https://arxiv.org/abs/2106.09685), [Stanford CS336](https://cs336.stanford.edu/).

MMMU-Pro strengthens multimodal assessment by filtering questions answerable without visual input and changing the input format. This supplies a specific lesson for the book: an evaluation advertised as visual understanding must actually require the visual evidence. It does not establish the current accuracy of the proposed support application. [MMMU-Pro](https://arxiv.org/abs/2409.02813).

## Security and operational responsibility

OWASP's August 2026 guidance provides application threat scenarios and mitigations. NIST's Generative AI Profile supplies a voluntary lifecycle framework covering contextual risks including privacy, harmful bias, confabulation, and human interaction. These support explicit authority boundaries, threat exercises, data handling, and accountable ownership. Neither is presented as a compliance certification or as proof that an application is safe. [OWASP GenAI LLM Top 10 2026](https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/), [NIST AI 600-1](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence).

Human–AI interaction research proposes guidelines for communicating capabilities, correcting errors, and supporting control. Its relevance evaluation predates current foundation-model agents, so the book treats it as a design foundation and still asks readers to test their actual recovery interface. [Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/).

Anthropic's 2025 incident account documents behavioral degradation related to infrastructure changes and gaps in existing evaluation. It supports teaching quality monitoring alongside availability and linking incidents to versioned changes. FrugalGPT provides historical evidence that measured routing can improve quality/cost tradeoffs; its particular savings and prices are not transferred to current workloads. [A postmortem of three recent issues](https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues), [FrugalGPT](https://arxiv.org/abs/2305.05176).

## Research method and remaining limits

Discovery covered discipline definitions, comparable educational material, prerequisites, compound systems, retrieval and context, agents, evaluation, adaptation, multimodal benchmarks, security, human interaction, operations, and economics. Follow-up focused on consequential gaps: differing definitions, differing prerequisite levels, retrieval versus long-context claims, judge validity, and the current edition of security guidance. Important sources returned by focused research lanes were checked in the main research process.

Sources were selected for original evidence, official curricula, first-party production experience, and relevant institutional guidance. Some research-paper findings were assessed from original abstracts and publication metadata rather than full paper reproduction. The source ledger records access scope and limitations per item. No experiment in the proposed book has been run as part of this blueprint.

Research stopped once every major competency family had a relevant evidence basis, competing definitions were reconciled by scope, and architecture claims were bounded by their experiments. Additional broad searches were unlikely to change the chapter sequence. This is a curriculum synthesis, not an exhaustive systematic literature review, hiring-market study, legal analysis, or validation of a universal professional standard.

Before publication, recheck living guidance and run the book's actual experiments with dated model, dataset, environment, and pricing records. Attribute historical results as historical, and keep model-specific setup material in the companion repository.
