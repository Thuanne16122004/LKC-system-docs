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

```text
[Feedforward Guides] ──► (Agent Action) ──► [Feedback Sensors]
(Steer Before Action)                        (Sense & Correct After Action)