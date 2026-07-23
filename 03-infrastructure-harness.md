# Module 03: Infrastructure & Harness Engineering

Deploying RAG and Agentic AI into production requires scalable **data infrastructure** and robust **control systems (Harness Engineering)** to guarantee safety, quality, and deterministic execution.

---

## 1. RAG Infrastructure & Vector Databases

### Essential Components
* **Knowledge Base:** External repository containing unstructured data (PDFs, docs, codebases) transformed into numerical vectors.
* **Chunking Strategy:** Splitting documents into optimized text segments prior to vectorization.
  * *Overly large chunks:* Dilute semantic relevance and overwhelm the LLM context window.
  * *Overly small chunks:* Destroy broader semantic context.
  * *Hyperparameter Tuning:* Balancing chunk size is critical for retrieval precision.
* **Retriever:** Executes **Semantic Vector Search** to identify embeddings mathematically close to the user's query vector.
* **Integration Layer & Orchestration:** Frameworks (such as LangChain, LlamaIndex, or watsonx Orchestrate) managing prompt synthesis and data flow.

---

## 2. Harness Engineering for AI Agents

To grant AI agents operational autonomy—especially in coding and software delivery—developers must build an outer **Harness**.

$$\text{Agent} = \text{Model} + \text{Harness}$$

A harness is a cybernetic governor that combines feedforward guides and feedback sensors to keep autonomous agents bounded and self-correcting.

### Controls: Feedforward vs. Feedback

The Harness operates via two primary control mechanisms:
1. **Feedforward (Guides):** Steers, provides rules, context, and constraints to the Agent before code generation.
2. **Feedback (Sensors):** Measures, evaluates, and responds to output after code generation to execute self-correction loops.

---

## Control Dimensions: Direction vs. Execution Modality

Harness controls are categorized across two fundamental dimensions:

1. **Direction:**
   * **Guides / Feedforward:** Steers the Agent **before** code generation, improving first-pass accuracy.
   * **Sensors / Feedback:** Observes output **after** the Agent acts, providing feedback signals for automated self-correction.
2. **Execution Modality:**
   * ⚙️ **Computational (CPU):** Deterministic, millisecond-level execution speed, $0$ token cost.
   * ✨ **Inferential (GPU/NPU):** Probabilistic, incurs token costs, evaluates qualitative semantics and architecture intent.


## Change Lifecycle & Shift-Left Feedback

To optimize token costs and accelerate delivery speed (Shift-Left Quality), feedback sensors are distributed strategically across the development lifecycle:

1. **Local Pre-Commit (Developer Workspace):** Executes fast computational sensors (ESLint, Biome, TypeScript Compiler). Linter error messages are injected directly into the prompt so the Agent can self-correct locally before committing code.
2. **Integration Pipeline (CI/CD Server):** Asynchronously runs heavy inferential sensors (Review Agents) and expensive computational checks (Mutation Testing) upon Pull Request creation.

---

## Out-of-Lifecycle Continuous Governance

Background sensors run continuously outside the active change lifecycle to detect system degradation:

1. **Continuous Drift Sensors:** Periodically scans repositories to detect dead code, outdated or vulnerable dependencies, and test coverage decay.
2. **Continuous Runtime Health Sensors:** Monitors live operational metrics (Latency, Error Rate). Upon detecting anomalies, specialized agents collect log samples, diagnose root causes, and automatically open Pull Requests with proposed patches.

---

## Three Categories of Regulation

The Harness system regulates three distinct quality domains:

1. **Maintainability Harness:** Manages style, cyclomatic complexity ($< 10$), and code duplication via linters and static analysis.
2. **Architectural Fitness Harness:** Employs automated architectural fitness functions (ArchUnit) to enforce module boundaries, encapsulation, and logging standards.
3. **Behaviour Harness (Approved Test Suite Model):** Prevents AI from writing invalid "false-green" tests by requiring code execution against developer-approved test suites.