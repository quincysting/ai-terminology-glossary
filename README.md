# AI Terminology

A working glossary of **186 AI terms across 12 sections**, each one glossed from a named book rather than from general usage. 22 books in the bibliography.

It also records two things a dictionary usually leaves out: words that carry **two unrelated meanings** in this field, and phrases in common circulation that **none of these books define**.

---

## The field

![Field map: the twelve families of AI vocabulary, grouped into foundations, build, operate and govern](diagrams/field-map.png)

Twelve families, four stages. The badge on each box is the number of terms in that section. Agents and orchestration (§5) and safety and governance (§11) are the two largest, and governance is the one stage that feeds backwards: what you are allowed to ship constrains what you build.

---

## Where the human sits

Most arguments about AI autonomy are really arguments about this one distinction, and there is a settled three-position vocabulary for it.

![The three oversight positions: human-in-the-loop, human-on-the-loop and full autonomy, with accountability fixed beneath all three](diagrams/oversight-spectrum.png)

- **Human-in-the-loop (HITL)** — approval required before enforcement.
- **Human-on-the-loop (HOTL)** — machines may initiate actions, but humans monitor and intervene as needed.
- **Full autonomy** — post-action human review only.

> Each trades speed for safety. The more autonomy, the greater the blast radius of mistakes.
>
> — Caroline Wong, *The AI Cybersecurity Handbook*

HITL and HOTL get used interchangeably and they are not the same. Leonid Kuligin is explicit that HOTL is oversight through *monitoring*: the implementations look alike because the annotation surfaces resemble each other, but the goals differ.

The accountability line is drawn in the same book, and it is the sharpest sentence in this whole family:

> We can outsource research, analytics, and option-generation to AI, but not responsibility, and never accountability.
>
> — Caroline Wong, *The AI Cybersecurity Handbook*

---

## Four autonomy ladders that do not agree

These books contain four separate graded models. They are not variants of one scheme, and treating them as interchangeable is a common mistake. Pick one deliberately and say which you mean.

| Model | Rungs | Source |
|---|---|---|
| Five-level business framework | prompt-based assistance → workflow automation → tool access → supervised autonomy → multi-agent | Liu, *Agentic AI Playbook*, Ch. 2 |
| Three-rung engineering ladder | assist → supervised → semi-autonomous | Andrei, *Agentic AI Systems*, Ch. 1 |
| SAE driving analogy | six levels, Level 0 fully manual → Level 5 fully autonomous | Bornet & Wirtz, *Agentic Artificial Intelligence* |
| Approval regimes for a coding agent | untrusted → progressively trusted, set by sandbox and approval flags | Vaughan, *Codex CLI*, Ch. 9 |

Two rules recur across all four, and both argue against starting high:

> Start with the lowest level of autonomy that can reliably solve the problem... Reliable results at a lower level are always better than unreliable results at a higher one.
>
> — Helena Liu, *Agentic AI Playbook*

> Think of autonomy as a ladder, not a switch.
>
> — Patrick A. Andrei, *Agentic AI Systems*, Ch. 1

Andrei is blunt about why it matters: "Many failures blamed on 'hallucinations' are governance failures. The system was allowed to act without clear stopping conditions, without verification, or without a safe exit."

For the operating model that follows, Trevoir Williams states it as a sequence: let AI assist, let humans decide, let automation execute, then validate the results.

---

## One word, two meanings

These are the homonyms that cause real confusion. When a conversation about AI goes in circles, it is usually one of these five.

| Word | Meaning A | Meaning B |
|---|---|---|
| `inference` | Running a trained model to get a prediction | Drawing conclusions from data under uncertainty |
| `bias` | The bias-variance tradeoff, a statistical property of a model class | Unfair or discriminatory behaviour toward groups of people |
| `supervised` | A learning paradigm that uses labelled data | An autonomy rung where a human approves consequential actions |
| `guardrail` | A runtime control on model input and output | An automatic data-quality check inside a training job |
| `augmentation` | Enhancing human work with AI | Synthetically expanding a training set |

Terms affected by one of these carry a small **two meanings** link in the glossary below.

---

## Five phrases in circulation, and what backs them

Phrases like these get used as if they were an agreed scale. Three are well sourced. Two are not, and it is worth knowing which, because a reader who looks them up will not find them.

| Phrase | Status | Nearest sourced term |
|---|---|---|
| **automated** | Sourced | Deterministic automation: fixed, predetermined tool chains that run the same steps regardless of results. Yildirim frames the move to agents as "a shift from checklists to cognition". |
| **AI-augmented** | Sourced | *Augmentation*, the middle of a three-mode value taxonomy: automation replaces process steps, augmentation enhances human work, data exploration uncovers insight. |
| **human-approved** | Sourced, as a mechanism | Human-in-the-loop: "approval required before enforcement". The *supervised* rung is tighter: approval before anything "external, costly, irreversible, or reputation sensitive". |
| **human-led** | **Not a defined level** | The *assist* rung: "the agent drafts and proposes, and a human decides and executes". |
| **exception-led** | **In none of these books** | *Supervised autonomy*: the agent acts on routine cases within clear rules and escalates exceptions. The idea is well sourced; the phrase is not the books' own. |

If you are building a framework and want these as your rung names, they work. Just expect readers to meet the sourced vocabulary instead.

---

## How the terms connect

The glossary's terms cross-reference each other 516 times. Those links are not evenly spread: the eight most-referenced terms fall into two clusters that barely touch.

![Cross-reference clusters: a build cluster of RAG, prompting and fine-tuning, an oversight cluster of guardrails, human-in-the-loop and explainability, and MLOps connected to neither](diagrams/hub-network.png)

One cluster is about **getting a model to produce the right output** (retrieval, prompting, fine-tuning). The other is about **being allowed to ship it** (guardrails, human oversight, explainability, responsible AI). MLOps is the eighth hub and links to neither, despite 16 links elsewhere.

---

## Contents

1. [Foundations and model types](#1-foundations-and-model-types) · 15 terms
2. [Training and adaptation](#2-training-and-adaptation) · 22 terms
3. [Prompting and context engineering](#3-prompting-and-context-engineering) · 11 terms
4. [Retrieval and RAG](#4-retrieval-and-rag) · 16 terms
5. [Agents and orchestration](#5-agents-and-orchestration) · 22 terms
6. [Autonomy and human oversight](#6-autonomy-and-human-oversight) · 12 terms
7. [Tools, protocols and integration](#7-tools-protocols-and-integration) · 10 terms
8. [Evaluation and measurement](#8-evaluation-and-measurement) · 14 terms
9. [Serving and inference](#9-serving-and-inference) · 19 terms
10. [MLOps and the model lifecycle](#10-mlops-and-the-model-lifecycle) · 16 terms
11. [Safety, security and governance](#11-safety-security-and-governance) · 24 terms
12. [Failure modes](#12-failure-modes) · 5 terms

---

### 1. Foundations and model types

_15 terms._

**Large Language Models** — Large language models are transformer-based models pretrained on very large text corpora, coming in three architectural shapes — encoder-only, decoder-only, and encoder-decoder — trained on web-scale datasets such as Common Crawl, C4, The Pile, and...

**Foundation Models** — Foundation models are very large models pretrained on broad data and then reused across many downstream tasks — one model serving many tasks, in place of a separate task-specific model per problem.

**Transformer Architecture** — The Transformer is a neural-network architecture (Vaswani et al., 2017) built around self-attention.

**Attention Mechanism** — Attention is the mechanism that lets a sequence model compute a weighted combination over all positions at once instead of threading state through a recurrence.

**Self-Attention** — The core transformer mechanism. Each token in a sequence projects to three vectors via learned weight matrices.

**Tokenization** — Tokenization converts raw text into the discrete units a language model actually operates on, using subword algorithms (BPE, WordPiece, SentencePiece) that sit between character-level and word-level splitting.

**Embeddings** — An embedding is a learned dense vector representation of sparse, high-cardinality input — words, but equally users, products, or geographic entities — placing semantically similar items near each other.

**Embedding Models** — Models that convert text into dense numerical vectors capturing semantic meaning. Azure OpenAI Essentials Ch. 3 differentiates OpenAI's `text-embedding-ada-002`, `text-embedding-3-small`, and `text-embedding-3-large` on dimensionality...

**Multimodal AI** — Multimodal AI covers models that generate or reason across more than one modality — text, image, audio.

**Diffusion Models** — Diffusion models are generative models that learn to synthesize data by reversing a gradual noising process.

**Mixture of Experts** — Mixture of Experts (MoE) is a model architecture that replaces a dense layer with many parallel "expert" sub-networks plus a learned **gating** function that, per token, routes computation to only a small subset of experts.

**LLM Model Types** — The progression of LLM variants by training stage: **base** (pretrained next-token predictor), **instruction-fine-tuned** (RLHF/SFT-tuned to follow instructions and chat), and **domain-adapted** (further trained on specialized corpora).

**LLM Context Features** — The set of operational model attributes an LLMBA builder weighs when selecting an open model, beyond raw quality.

**LLM Inference Parameters** — LLM inference parameters are the sampling controls applied to a model's output-token probability distribution at generation time.

**Scaling Laws** — Scaling laws describe how model performance (loss) predictably improves as a function of model size, dataset size, and training compute, following power-law relationships.

<sub>[back to top](#contents)</sub>

### 2. Training and adaptation

_22 terms._

**LLM Pretraining** — LLM pretraining is the first, most compute-intensive training stage: a Transformer is trained on a very large unlabeled text corpus with a self-supervised next-token objective, learning general language and world knowledge before any task-specific...

**Fine Tuning** — The process of adapting a pre-trained model to a target task, domain, or instruction style by continuing training on a smaller dataset.

**Parameter-Efficient Fine-Tuning (PEFT)** — Parameter-efficient fine-tuning (PEFT) adapts a large pretrained model by training only a small set of new or selected parameters while freezing the original weights — capturing most of the gains of full fine-tuning at a fraction of the compute and...

**LoRA Fine Tuning** — LoRA (Low-Rank Adaptation) fine-tuning trains a small set of low-rank adapter matrices injected into a frozen base model, rather than updating all parameters.

**QLoRA** — QLoRA builds on by adding quantization: it applies quantization (including blockwise quantization internals) to lower the memory footprint of fine-tuning while still learning low-rank adapters on task-specific data.

**RLHF** — A post-training technique that fine-tunes a language model's outputs toward human preferences using a learned reward model, traditionally applied after a pretrain → supervised-fine-tuning (SFT) pipeline.

**Reinforcement Learning** — Reinforcement learning trains an agent to choose actions that maximize cumulative reward through interaction with an environment — framed formally as Markov decision processes, or practically as goal-centric reward shaping ("a few points for moving...

**Deep Reinforcement Learning** — Deep reinforcement learning uses neural networks as the function approximator inside RL — either for the value function or for the policy itself.

**Transfer Learning** — Transfer learning is the reuse of a model pretrained on a large general dataset as the starting point for a different, usually smaller, downstream task.

**Knowledge Distillation** — Knowledge distillation trains a smaller "student" model to reproduce a larger "teacher" model's behavior, compressing model size while retaining much of its accuracy.

**Model Distillation** — Model distillation transfers a large "teacher" model's capabilities into a smaller "student" model by training the student on the teacher's outputs.

**Model Quantization** — Quantization lowers the numeric precision of a model's weights and often its activations to cut memory footprint and inference latency, at some accuracy cost.

**Distributed Training** — Distributed training runs a single training job across many devices — and usually many machines — coordinating them with **collective operations** rather than shared memory.

**Data Parallelism** — Data parallelism (DP) replicates the **full model on every device**, gives each replica a different slice of the batch, and synchronizes gradients across replicas so every copy stays identical.

**Model Parallelism** — Model parallelism splits the **computation** of a single forward/backward pass across devices, so that one sample's pass requires several GPUs to complete.

**Hyperparameter Tuning** — Hyperparameter tuning (HPO) is the search over model configuration values that are not learned during training — learning rate, tree depth, layer sizes, regularization strength — evaluated by running repeated train-and-validate trials over a...

**Hyperparameter Optimization** — Hyperparameter optimization (HPO) is the automated search over the configuration values a model does not learn from data — learning rate, depth, regularization strength — under a fixed time or compute budget.

**Continual Learning** — Keeping a deployed model current as data shifts. Designing Machine Learning Systems Ch. 9 draws the central distinction between stateless retraining (full retrain from scratch on fresh data) and stateful training (incrementally updating...

**Curriculum Learning** — Training an agent on progressively harder versions of a task instead of the full difficulty from the start.

**Mixed Precision Training** — Mixed precision training runs most neural-network computation in lower-precision floating point (FP16 or BF16) while keeping numerically sensitive operations (weight updates, loss scaling) in FP32, exploiting dedicated hardware like CUDA tensor...

**LLM Alignment** — Shaping a model's **internal tendencies** so its outputs match a desired policy, as distinct from filtering outputs externally at runtime.

**Constitutional AI** — Anthropic's alignment method that replaces human preference labels with AI-generated ones against an explicit written set of principles (a "constitution").

<sub>[back to top](#contents)</sub>

### 3. Prompting and context engineering

_11 terms._

**Prompt Engineering** — Prompt engineering is the disciplined design of LLM inputs — instructions, context, examples, output schema, and inference parameters — to steer model behavior toward reliable, structured results without changing the model itself.

**Context Engineering** — Context engineering is the discipline of treating an agent's context window as a finite, precious resource and deliberately curating what enters it.

**In Context Learning** — In-context learning (ICL) is an LLM's ability to perform a new task purely from instructions and examples placed in the prompt at inference time, without any weight updates.

**Few Shot Prompting** — Few-shot prompting is supplying a small set of worked input/output pairs inside the prompt so the model infers the intended format and style from demonstration rather than from instruction.

**Few Shot Learning** — Few-shot learning is adapting a model to a task when only a handful of labeled examples exist.

**Chain-of-Thought (CoT)** — Having a model emit intermediate reasoning steps before its final answer. DeepSeek in Practice Ch. 2 covers both CoT and "long CoT", where the reasoning is structured into explicit `<think>` and `<answer>` blocks — an architectural...

**Context Compaction** — Context compaction is summarizing or clearing an agent's near-full context and reinitializing it, so a long-running agent can keep working without exhausting its context window.

**Prompt Caching** — Prompt caching reuses the computation for a frequently-sent prompt prefix across API calls, so repeated context is not re-processed on every roundtrip.

**CLAUDE.md** — CLAUDE.md is a special configuration/memory file that gives Claude Code persistent, project-specific context — architecture, conventions, build/test commands, tooling, and workflows — so you don't re-explain them every conversation.

**AGENTS.md** — A markdown instruction file that a coding agent loads from the repository root and from subdirectories to pick up project-specific context.

**Image Generation Prompting** — Image generation prompting is the practice of crafting text prompts to steer diffusion-based text-to-image models.

<sub>[back to top](#contents)</sub>

### 4. Retrieval and RAG

_16 terms._

**Retrieval Augmented Generation** — RAG grounds an LLM's generation in external knowledge by retrieving relevant chunks from a vector or keyword index at query time and injecting them into the prompt as context.

**Agentic RAG** — Retrieval-augmented generation in which an agent decides *when and what* to retrieve — issuing retrieval as a tool call inside a reasoning loop — rather than running a fixed retrieve-then-generate pipeline.

**Data Chunking** — Chunking is the splitting of source documents into retrieval units before they are embedded into a vector store.

**Semantic Chunking** — Semantic chunking is a document-splitting strategy for RAG pipelines that groups text by meaning rather than by fixed character/token counts — splitting where topic or embedding similarity between adjacent sentences drops, as opposed to character,...

**RAG Chunking** — The step in a RAG pipeline that splits preprocessed documents into retrievable units. The book lays out a taxonomy.

**Hybrid Search** — Retrieval that combines dense vector similarity with sparse keyword matching and fuses the two score sets into one ranking.

**Semantic Search** — Retrieval by meaning rather than by token match: content and query are both embedded, and results are ranked by distance in the embedding space.

**Vector Search** — Nearest-neighbour retrieval over an index of embedding vectors. Both sources treat it as a backend-selection problem rather than an algorithm.

**Vector Database** — A store that indexes and answers similarity queries over them — the retrieval substrate of a RAG pipeline, sitting between and the generator.

**Approximate Nearest Neighbor** — Retrieval of vectors that are near a query without guaranteeing the exact nearest, trading recall for speed and memory.

**HyDE** — HyDE (Hypothetical Document Embeddings) is a retrieval technique where an LLM first generates a hypothetical answer document for a query, then that hypothetical document — not the raw query — is embedded and used to search, closing the semantic gap...

**Knowledge Graph** — A knowledge graph stores entities as nodes and their relationships as typed edges, so retrieval can traverse connections rather than only match text.

**Long Context vs RAG** — The design decision between two ways of supplying an LLMBA with knowledge: **RAG** (retrieve and inject only the relevant chunks at query time) versus **long-context models (LCMs)** that load the entire corpus into a large context window (optionally...

**RAG With Citations** — "RAG done right" — a retrieve → summarize → cite → act discipline over a curated, minimum-viable knowledge base (chunked by headings), where citations are mandatory and conflicts are resolved by an explicit source-quality rubric (source type,...

**Entity Resolution** — Entity resolution is the process of determining that records from different sources referring to the same real-world financial entity (a company, security, or counterparty) are in fact the same, using rule-based, probabilistic, or deep-learning...

**Semantic Layer** — The layer that sits between physical storage and consumers, expressing data in business terms rather than table shapes.

<sub>[back to top](#contents)</sub>

### 5. Agents and orchestration

_22 terms._

**AI Agents** — An AI agent is an LLM-driven system that runs a perceive-reason-act-learn loop, built from five components — the model, memory, planning, tools, and reflection.

**Agentic AI** — An agent is best defined by **control flow, not capability**: an LLM generates text, RAG generates *grounded* text, tool use connects the model to external capabilities, and an agent *decides, acts, observes, and continues through a controlled loop*...

**Agent As Controlled Loop** — The reframing of an AI agent as a deterministic cycle — Input → Interpretation → Planning → Action (tool or draft) → Observation → State Update → Next Step, then repeat or finish — rather than a "smart personality".

**ReAct Agent Pattern** — A reasoning framework for LLM agents that interleaves explicit reasoning steps with actions (tool calls) and observations of their results, letting the model adjust its plan based on what each action returns rather than committing to a fixed...

**Multi Agent Systems** — A multi-agent system is one in which several LLM-driven agents work on a task together under an explicit coordination scheme rather than as a single agent loop.

**Multi Agent Orchestration** — The practice of wiring multiple agents (or multiple sessions of one agent) into a coordinated system rather than relying on a single agent loop.

**Multi Agent Communication Styles** — Multi-agent communication styles describe how data flows between agents in a multi-agent system, classified into three concrete patterns.

**Agent Coordination Patterns** — Structural patterns for composing multiple agents/workflows into a larger system. Yıldırım distills three core forms.

**Supervisor-Worker Pattern** — The supervisor-worker pattern is a multi-agent topology in which a supervisor agent coordinates specialized worker agents.

**Subagents** — Subagents are isolated Claude instances, each with their own fresh context window, system prompt, and tool permissions, that an orchestrator delegates a discrete task to — they do the work independently and return only the result.

**Agent Memory** — The persistence layer that lets an agent carry state across steps and across sessions, split into short-term memory (the working context of the current task) and long-term memory (what survives to inform later ones).

**Agent Memory Types** — A taxonomy of agent memory grounded in the CoALA framework: **short-term / working memory** (the context window, held as a rolling buffer) plus **long-term memory** split into **episodic** (case-based reasoning over past events), **semantic**...

**Agent Memory vs State** — The separation of short-term **session state** (the per-run workbench: goal, constraints, plan, execution record, open questions, assumptions) from **long-term memory** (durable knowledge persisted across runs under an explicit schema.

**Agent Skills** — Agent Skills (a.k.a. Claude Skills / Claude Code Skills) are organized folders of instructions, scripts, and resources that an agent discovers and loads dynamically to specialize at a task — "like an onboarding guide for a new hire".

**Agent Design Process** — The end-to-end method for taking an AI agent from opportunity to a system that runs in the business.

**Agent Job Description** — A one-sentence operator contract for an agent of the form: "It owns X outcome, under Y constraints, and it must produce Z artifacts every run".

**Agent As Tool Composition** — Agent-as-tool composition wraps a complete agent so it presents the same interface as an ordinary tool — in AWS Strands via `.as_tool()` — making the agent a callable, reusable unit.

**A2A (Agent-to-Agent Protocol)** — A2A (Agent-to-Agent) is Google's open protocol for standardizing communication *between* autonomous agents, where MCP standardizes communication between an agent and its tools.

**Agentic AI vs Traditional Automation** — The distinction between deterministic automation (fixed, predetermined tool chains — e.g. a scripted Nmap → subfinder pipeline that runs the same steps regardless of results) and agentic AI, where an LLM interprets a goal, selects the next tool,...

**Workflows vs Agents** — A hybrid architectural stance: hardcode the deterministic path as a workflow and agent-ify only the ambiguous decisions — "agent for decision points, workflow for deterministic execution".

**Harness Engineering** — The discipline of designing the infrastructure, constraints, and feedback loops that make AI agents reliably productive — "one level up" from both software engineering (which designs code) and prompt engineering (which designs instructions for a...

**Agent Observability** — The discipline of making an agent run reconstructable, keyed by a **run ID** as spine, capturing a minimal-but-strict log schema.

<sub>[back to top](#contents)</sub>

### 6. Autonomy and human oversight

_12 terms._

**Human-in-the-Loop (HITL)** — Human-in-the-loop (HITL) is the design pattern of inserting a human review or approval step into an agent's workflow rather than letting it act fully autonomously.

**Autonomy Ladder** <sup>[two meanings](#one-word-two-meanings)</sup> — A graded progression of agent independence — assist → supervised → semi-autonomous — framed as "a ladder you earn by demonstrating the loop can stop".

**Agent Autonomy Levels** — A graded framework classifying how much independence an AI agent has — most commonly a five-level progression.

**Agent Approval Ladder** — The set of trust regimes a terminal coding agent runs under, deciding which actions proceed automatically and which require explicit human approval.

**Autonomous AI** — Flexible, real-time-adapting decision-making systems, defined in Designing Autonomous AI's Introduction as distinct from rigid automated systems such as Dijkstra's algorithm or expert systems.

**Human Agent Collaboration** — The practice of running hybrid teams in which AI agents and people share the work. Agentic Artificial Intelligence Ch. 10 is the library's most direct treatment, and frames it as a leadership problem — work design, trust, change...

**Human Machine Collaboration** — Human-machine collaboration, per Radically Human, is framed as a "third stage" of AI adoption — following stage 1 (automation/replacement) and stage 2 (collaborative augmentation) — in which humans remain in the ascendant even...

**Automation / Augmentation / Data Exploration** <sup>[two meanings](#one-word-two-meanings)</sup> — A three-mode taxonomy of how AI creates value, from AI Innovation in Business Ch. 2's "five habits of highly effective AI organizations".

**Stop List and Approval Rules** — The "stop list" is a set of hard boundaries an agent may never cross — canonical examples.

**Agent Guardrails** <sup>[two meanings](#one-word-two-meanings)</sup> — A layered control system that keeps an agent inside defined bounds: four permission tiers per tool action (read-only / draft-only / execute-with-approval / auto-execute), two-step confirmation gates for irreversible actions (payload preview +...

**Runtime Guardrails** <sup>[two meanings](#one-word-two-meanings)</sup> — Controls applied to an LLMBA at inference time (as opposed to dev-time benchmarks) to filter, constrain, or block unsafe inputs and outputs in production.

**Agent Sandboxing** — Agent sandboxing contains an agent's execution within OS-level boundaries so it can work freely inside them while its blast radius is capped from the outside.

<sub>[back to top](#contents)</sub>

### 7. Tools, protocols and integration

_10 terms._

**Model Context Protocol (MCP)** — An open protocol (introduced by Anthropic in late 2024) that standardizes how LLM applications connect to external tools and data, acting as a "universal adapter" that eliminates per-tool custom integrations.

**Function Calling** — The mechanism by which a model, given a set of declared function specifications, emits a structured request naming one of them and supplying arguments — a **controlled contract** between the model and the application rather than a form of execution.

**Agent Tool Use** — Tool use is the rung where a model stops producing text and starts reaching external capability — but the mechanics are narrower than the phrase suggests.

**Programmatic Tool Calling** — Programmatic tool calling (PTC) has the model invoke tools by *writing and executing code* in a sandbox rather than emitting one tool-call JSON object per step.

**MCP Tool Design Methodologies** — A comparative framework for how much offensive methodology to embed in an MCP tool versus delegate to the LLM.

**MCP vs A2A** — MCP (Model Context Protocol) and A2A (Agent-to-Agent) are complementary open protocols operating at different layers.

**Claude Plugins** — Claude plugins are single-command-installable packages that bundle customizations so they can be shared and distributed.

**Claude Code Hooks** — Hooks are deterministic handlers that fire on Claude Code lifecycle events — file edits, tool calls, session start, compaction — to automate tasks, enforce rules, and inject context.

**Kernel Level Agent Sandboxing** — Restricting what an autonomous coding agent can do at the operating-system layer rather than the application layer, so the restrictions are enforced by the kernel and cannot be bypassed by the agent.

**Managed Agents** — Claude Managed Agents is Anthropic's hosted service for running long-horizon agents: you define the tasks, tools, and guardrails, and Anthropic runs the agent plus its orchestration harness (tool-calling, context management, error recovery) on...

<sub>[back to top](#contents)</sub>

### 8. Evaluation and measurement

_14 terms._

**Model Evaluation** — Model evaluation is offline measurement of a trained model before it reaches production. Designing Machine Learning Systems Ch. 6 covers the full offline toolkit — baselines, evaluation metrics, calibration, behavioral testing, and...

**LLM Evaluation** — LLM evaluation is the measurement of generated-output quality where outputs are open-ended and ground truth is usually absent — the reason traditional metrics run out.

**LLM Evaluation Tools** — The open-source frameworks that operationalize LLMBA evaluation at scale: **LangSmith** (orchestration over `hf_evaluate`, golden-dataset workflows, `num_repetitions` for nondeterminism, production monitoring), **Promptfoo** (YAML-driven CLI,...

**LLM-as-a-Judge** — Using an LLM to score or rank other models' outputs against criteria, replacing or augmenting human evaluation.

**Evaluating Evaluators** — The meta-evaluation problem: when you use an LLM (or model) as a judge, how do you know the judge itself is reliable? The book points to two approaches.

**Evals Gap** — The book's coined term for the chasm between traditional deterministic software testing and the evaluation of nondeterministic LLM-based applications.

**Agent Evaluation Suite** — A fixed test set — 30 cases split 10 normal / 10 edge / 10 adversarial — scored with binary success against the agent's SLA, tracking KPIs of success rate, time to complete (including human review), tool error rate, and cost per task.

**Agent Evaluation As Managed Service** — Bedrock AgentCore Evaluations is AWS's managed offering for evaluating agent behavior: it collects traces via AgentCore Observability, runs evaluation across defined levels, and supports custom evaluators.

**Model Benchmarking** — Model benchmarking is the quantitative comparison of candidate models on a defined task using a suite of metrics — lexical (BLEU, ROUGE, METEOR), semantic (embedding cosine similarity), and domain-specific (CLIP score for image-text alignment).

**Safety Benchmarks (SALAD, TruthfulQA, HarmBench)** — The three dev-time safety benchmarks the book uses to measure an LLM before deployment: **SALAD-Bench** (21K samples on a 6/16/66 hierarchical harm taxonomy, plus 5K attack-enhanced questions, scored by MD-Judge and MCQ-Judge), **TruthfulQA**...

**BLEU ROUGE for LLMs** — The reuse of classic n-gram-overlap NLP metrics — **BLEU** (precision-oriented, from machine translation) and **ROUGE** (recall-oriented variants ROUGE-1/2/L/Lsum, from summarization) — as a first-pass quantitative measure of LLMBA output against...

**A/B Testing** — An A/B test is a controlled experiment with two treatments (A and B) — often a new option B against an established default A — in which data is collected so that any observed difference between the groups must be due to either random chance in the...

**Machine Learning Model Evaluation** — Machine learning model evaluation is the lifecycle stage — following model training — in which a model's predictive performance is assessed before it is trusted or deployed.

**SageMaker Ground Truth** — SageMaker Ground Truth is Amazon's managed data-labeling service: it lets teams stand up a private (or public/vendor) labeling workforce and run structured labeling jobs for images and text, producing training-ready labeled datasets.

<sub>[back to top](#contents)</sub>

### 9. Serving and inference

_19 terms._

**Model Serving** <sup>[two meanings](#one-word-two-meanings)</sup> — Model serving is the runtime layer that exposes a trained ML model behind a callable interface — typically a REST/gRPC endpoint, a batch transform job, or an in-process library — and handles the operational concerns around it.

**ML Model Serving** — ML model serving is exposing a trained model's predictions through an API for consumption by other systems.

**Model Serving Frameworks** — Model serving frameworks are specialized runtimes for deploying trained models — for LLMs specifically, frameworks like vLLM and TensorRT-LLM — compared in Hands-On LLM Serving and Optimization Ch. 8, with Ch. 3 grounding the comparison...

**LLM Inference** <sup>[two meanings](#one-word-two-meanings)</sup> — LLM inference is generating output from a trained language model at serving time, characterized by autoregressive (token-by-token) generation split into a compute-bound "prefill" phase (processing the prompt) and a memory-bandwidth-bound "decode"...

**ML Inference** <sup>[two meanings](#one-word-two-meanings)</sup> — ML inference is the process of running a trained model against new input to produce predictions.

**Inference Optimization** — Inference optimization is the set of techniques for cutting the latency, memory footprint, and cost of serving a model without retraining it.

**Continuous Batching** — Continuous (also called **in-flight**) batching is a scheduling policy for LLM serving in which the engine **evicts a finished request from the batch and admits a waiting one mid-flight**, rather than holding the batch fixed until every sequence in...

**Speculative Decoding** — Speculative decoding accelerates autoregressive generation by having a **small draft model propose N tokens ahead**, which the large target model then **verifies in a single forward pass**.

**KV-Cache Optimization** — The KV cache stores the key and value projections already computed for previous tokens so that each decode step computes K and V only for the **new** token.

**Inference Time Compute** — Inference-time compute (test-time compute) is additional computation spent at inference — beyond a single forward pass — to improve output quality, via techniques like chain-of-thought scaling, self-consistency sampling, and process reward models.

**LLM Throughput Scaling** — LLM throughput scaling addresses growing request capacity on a managed LLM API without hitting rate limits — in Azure OpenAI, via quota management and Provisioned Throughput Units (PTU-M), a reserved-capacity purchase model sized against expected...

**Batch vs Real-Time Scoring** — The choice between scoring records in scheduled bulk versus on request. Automated Machine Learning with Microsoft Azure Ch. 8 codifies a five-step batch scoring procedure against a four-step real-time procedure, with explicit criteria...

**Batch vs Online Prediction** — Batch prediction precomputes model outputs for a known set of inputs on a schedule (hourly, nightly) and stores them in a database or feature store for later lookup.

**On Device Inference** — On-device inference is running a trained model's inference step locally on the device collecting the data, rather than sending that data to the cloud for processing.

**LLM Deployment** — LLM deployment, per LLMOps framing, is the operational process of shipping an LLM-backed application to production — containerized, API-first, behind versioned gateways — as either a modular (composable services) or monolithic architecture,...

**LLM Local Deployment** — LLM local deployment is running a language model entirely on local or on-premises hardware rather than a cloud API — e.g., via Ollama (model install/run, Modelfile customization for system prompts and moderation) paired with a local UI (Open WebUI...

**LLM Cloud Deployment** — LLM cloud deployment is running large language models through managed cloud services — e.g., AWS Bedrock (IAM-gated model access, boto3 streaming, CloudWatch observability) or Google Vertex AI (Model Garden, Colab Enterprise, gcloud auth, Vertex SDK...

**GPU Cluster Management** — GPU cluster management is the platform-operations work of provisioning, scheduling, and sizing GPU capacity for ML workloads on Kubernetes.

**Inference Cost Collapse** — The rapid, sustained decline in the cost of LLM inference: an a16z mid-2024 estimate of ~10x/year accelerated to **50–200x/year by early 2025**.

<sub>[back to top](#contents)</sub>

### 10. MLOps and the model lifecycle

_16 terms._

**MLOps** — The engineering discipline of running ML systems in production: pipelines, CI/CD, model registries, feature stores, monitoring, drift detection, and governance — i.e., the connective tissue that lets an ML org iterate on data and models without...

**LLMOps** — LLMOps is the operational discipline for LLM-backed applications, extending MLOps with concerns that classical ML pipelines do not have.

**ML Pipeline** — An ML pipeline is the orchestrated sequence that turns raw data into a deployed model — ingestion, preparation, feature engineering, training, evaluation, and serving — executed as versioned stages rather than as notebook steps.

**AI Pipeline** — The end-to-end sequence of steps an organization runs to turn data into a deployed AI capability.

**Feature Engineering** — The discipline of transforming raw input data into the numeric, categorical, or embedding representations a model actually trains on.

**Automated Feature Engineering** — Machine generation of model features. Automated Machine Learning Ch. 2 subdivides it into feature extraction, feature selection, and feature generation/construction.

**Feature Store** — A feature store is a shared registry in which features are computed once and consumed by both training pipelines and online serving, so the two paths cannot diverge — formalized as Pattern 26 in Machine Learning Design Patterns (~pp....

**Experiment Tracking** — Experiment tracking is the systematic logging of ML training runs — parameters, metrics, code versions, and artifacts — so experiments are reproducible and comparable.

**Mlflow Model Registry** — The MLflow Model Registry is the component that versions trained models and tracks their promotion through a lifecycle, decoupling "which model version exists" (training/tracking) from "which model version is live" (serving).

**Model Versioning** — Model versioning is Pattern 27 in Machine Learning Design Patterns (Ch. 6, ~pp. 305–325).

**Model Drift Detection** — Model drift detection identifies when a deployed model's performance degrades because the production data distribution has shifted from training — closing the production loop by signaling when retraining is needed.

**Training Serving Skew** — The divergence between how features are computed during training and how they are computed at inference.

**Canary Deployment** — A canary deployment releases a new version to a small slice of production traffic first, then progressively shifts more traffic to it as it proves healthy — 90-10, 75-25, 50-50 splits are typical staging points.

**Prototype to Production Pipeline** — A prototype-to-production pipeline is the transformation path from exploratory Jupyter/Colab notebooks to a production-deployed service, systematically replacing ephemeral conveniences with durable, versioned, observable infrastructure.

**Feature Training Inference Pipeline** — FTI is a three-pipeline architecture for ML systems: a feature pipeline (data → vector DB), a training pipeline (fine-tuning on GPU clusters), and an inference pipeline (RAG plus model serving), each independently deployable.

**Model Validation** — Model validation, per Machine Learning in Production Chs. 7–10, is applied as a recurring train/predict/validate triad for every algorithm covered (Jaccard, MinHash, cosine similarity, Mahalanobis distance, linear regression, random...

<sub>[back to top](#contents)</sub>

### 11. Safety, security and governance

_24 terms._

**Responsible AI** — Responsible AI is the set of principles, processes, and tooling that embed fairness, reliability, privacy, inclusiveness, transparency, and accountability into the AI lifecycle — design, data, training, evaluation, deployment, and monitoring —...

**AI Governance** — The organizational and technical machinery that bounds what AI systems may do, proves what they did, and assigns accountability for the consequences.

**AI Ethics** — AI ethics is the field covering equity, fairness, bias, transparency, policy, privacy, weaponization, and security in AI systems, together with the technical and policy mitigations available for each.

**NIST AI RMF** — The NIST AI Risk Management Framework (AI RMF) is a structured set of functions for managing risk in AI systems throughout their lifecycle.

**AI Lab Safety Frameworks** — The published risk-governance regimes frontier AI labs and policy centers use to gate model development and release against catastrophic capability thresholds.

**Six Phase Safety and Alignment Plan** — Souza's concrete operating model for shipping a safe, aligned LLMBA, structured as six sequential phases.

**Explainable AI** — The property that a system's outputs can be accounted for — either **by construction** (inherently interpretable models, or modular architectures where the decomposition *is* the explanation) or **post hoc** (SHAP, LIME, integrated gradients,...

**Model Interpretability** — Interpretability is the degree to which a model's decision process can be understood directly.

**Interpretable ML** — Interpretable ML refers to models that are transparent by design rather than explained after the fact — most notably Generalized Additive Models (GAMs) and Explainable Boosting Machines (EBMs).

**Algorithmic Fairness** <sup>[two meanings](#one-word-two-meanings)</sup> — The measurement and mitigation of bias in ML systems, treated sociotechnically rather than as a pure metric problem.

**Fairness In ML** — Fairness in ML is the engineering practice of measuring and then correcting disparate outcomes a model produces across demographic or otherwise protected subgroups.

**ML Bias and Fairness** <sup>[two meanings](#one-word-two-meanings)</sup> — ML bias and fairness concerns the risk that trained models encode and amplify discriminatory patterns from training data or design choices, producing systematically unequal outcomes across groups.

**Algorithmic Bias Audit** — An algorithmic bias audit is a systematic evaluation of a model's outputs for discriminatory patterns across demographic groups, applying a checklist of organizational, methodological, and transparency practices to detect and mitigate unfair...

**Differential Privacy** — Differential privacy is a formal guarantee that an output is statistically insensitive to any single training record, parameterized by an epsilon/delta privacy budget and enforced with calibrated noise.

**Privacy Preserving ML** — Machine-learning techniques that let models train or infer on sensitive data without exposing the raw data itself — the source's example applies this to IoMT (Internet of Medical Things) and edge computing, where patient data must stay protected...

**Prompt Injection** — An attack in which malicious instructions hidden in input text cause an LLM (or LLM-driven agent) to deviate from its intended task — leaking prompts, exfiltrating data, executing code, or transmitting malware.

**Jailbreaking** — Jailbreaking is the use of adversarial prompting to make an LLM override its ethical safeguards or content restrictions and produce restricted or harmful output.

**Red Teaming LLMs** — Adversarial testing of an LLM to surface harmful behavior before deployment. The book's foundational reference is Perez et al. 2022, "Red Teaming Language Models with Language Models," which uses a 280B "red" LLM to automatically attack a target and...

**LLM Safety Risks** — The category of attacks and failure modes specific to LLM-based applications, distinct from general AI risk.

**LLM Content Filtering** — LLM content filtering is the automated screening of model inputs and outputs against harm categories (hate, violence, sexual content, self-harm, etc.) with configurable severity and customizability.

**Model Transparency** — Model transparency, per Practical Automated Machine Learning on Azure Ch. 7, is Azure AutoML's set of features for understanding an automatically generated model pipeline — including guardrails reporting — framed as AutoML's...

**AI Transparency** — Disclosure of how an AI system works and decides. The Secrets of AI Value Creation Ch. 7 (Building Stakeholder Trust) treats transparency as a requirement *beyond* trust-building — distinctive in arguing that transparency carries...

**Adversarial AI** — The dual-use framing of AI in security: the same capabilities that accelerate an attacker's reconnaissance, phishing, and exploitation also act as a force multiplier for defenders' detection and response.

**Adversarial ML** — The study of attacks against machine learning models and the countermeasures for them, covering adversarial examples against tree-based models and image classifiers, data poisoning of the training set, and model extraction.

<sub>[back to top](#contents)</sub>

### 12. Failure modes

_5 terms._

**LLM Hallucination** — Hallucination is an LLM producing fluent, confident output that is fabricated or unsupported by its inputs.

**Overfitting** — Overfitting is when a model captures noise in the training data rather than the underlying signal, so it performs well in-sample but generalizes poorly to unseen data — the high-variance end of the bias-variance trade-off.

**Mode Collapse** — Mode collapse is a failure mode "inherent to GANs" in which the generator starts producing only a narrow variety of samples — collapsing onto a few "modes" of the data distribution — instead of capturing its full diversity.

**Data Leakage** — Data leakage occurs when information that would not be available at prediction time leaks into the training set, causing a model to appear more accurate during evaluation than it actually performs in production.

**Bias-Variance Tradeoff** <sup>[two meanings](#one-word-two-meanings)</sup> — The bias-variance tradeoff decomposes generalization error into bias — error from a model too constrained to capture the signal (underfitting) — and variance — error from fitting noise in the training sample (overfitting).

<sub>[back to top](#contents)</sub>


---

## Sources

Every definition traces to one of these. Chapter references appear in the entry where the book gives one.

- **Designing Autonomous AI** — Kence Anderson, 2022
- **Agentic AI Systems** — Patrick A. Andrei, 2026
- **Agentic Artificial Intelligence** — Pascal Bornet, Jochen Wirtz, Thomas H. Davenport, David De Cremer, Brian Evergreen, Phil Fersht, Rakesh Gohel, Shail Khiyara, 2025
- **Radically Human** — Paul R. Daugherty, H. James Wilson, 2022
- **AI Innovation in Business** — Jonny Holmström, 2026
- **Designing Machine Learning Systems** — Chip Huyen, 2022
- **Machine Learning in Production** — Andrew Kelleher, Adam Kelleher, 2019
- **Architecting Generative AI Applications** — Leonid Kuligin, 2026
- **The Agentic Enterprise** — Nitin Kumar, Vipin Kataria, 2026
- **Machine Learning Design Patterns** — Valliappa Lakshmanan, Sara Robinson, Michael Munn, 2021
- **Agentic AI Playbook** — Helena Liu, 2026
- **Automated Machine Learning** — Adnan Masood, 2021
- **Azure OpenAI Essentials** — Amit Mukherjee, Adithya Saladi, 2025
- **Practical Automated Machine Learning on Azure** — Deepak Mukunthu, Parashar Shah, Wee Hyong Tok, 2019
- **DeepSeek in Practice** — Andy Peng, Alex Strick van Linschoten, Duarte O. Carmo, 2025
- **The Secrets of AI Value Creation** — Michael Proksch, Nisha Paliwal, Wilhelm Bielert, 2024
- **Automated Machine Learning with Microsoft Azure** — Dennis Michael Sawyers, 2021
- **Codex CLI: Agentic Engineering from First Principles** — Daniel Vaughan, 2026
- **Hands-On LLM Serving and Optimization** — Chi Wang, Peiheng Hu, 2026
- **Agentic AI for DevOps Engineers** — Trevoir Williams, 2026
- **The AI Cybersecurity Handbook** — Caroline Wong, 2026
- **Agentic AI for Offensive Cybersecurity** — Orhan Yildirim, 2026

---

## Method, and what this is not

Each gloss summarises how a **named book** uses a term. It is not standards text, and where the books disagree the disagreement is recorded rather than resolved. Quotations are short and attributed; everything else is paraphrase.

Three honest limits:

- **Coverage follows the reading, not the field.** These are the books in one personal library. A term absent here is not a term that does not matter.
- **Some vocabulary is missing.** `context-window`, `model-drift`, `reward-hacking`, `goal-drift` and `context-rot` have no entry, because no source in this set defines them as named concepts. Failure modes (§12) is the thinnest section for that reason: five entries against §11's twenty-four.
- **Definitions age.** This vocabulary is moving quickly. Compiled November 2026.

Corrections and additions are welcome by issue or pull request, particularly a citation for anything listed above as missing.
