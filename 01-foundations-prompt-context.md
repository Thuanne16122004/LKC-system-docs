# Module 01: Foundations — Prompt & Context Engineering

Large Language Models (LLMs) do not possess inherent long-term memory at inference time. The quality, structure, and relevance of the information placed into the **Context Window** determine the model's accuracy, reasoning capability, and tool-use effectiveness.

---

## 1. Prompt Engineering

Prompt engineering is the practice of designing, testing, and refining input queries to guide generative AI models toward producing precise, context-aware, and actionable outputs with minimal post-processing.

### Core Skills of a Prompt Engineer
To effectively optimize AI performance and collaborate across technical and business units, a qualified Prompt Engineer requires a mix of technical, analytical, and interpersonal competencies:

* **Understanding of LLMs:** Deep knowledge of how Large Language Models operate—including their underlying mechanisms, capabilities, and limitations—to craft optimal prompts and maximize output quality.
* **Strong Communication:** Clear articulation to define project goals, provide precise instructions to AI models, and collaborate seamlessly across multidisciplinary teams.
* **Translating Technical Concepts:** Ability to break down complex technical AI behaviors and concepts into accessible explanations for non-technical stakeholders.
* **Programming Proficiency (Python):** Hands-on experience with programming languages like Python to interact with APIs, customize AI solutions, and automate workflows.
* **Mastery of Data Structures & Algorithms:** Knowledge of computer science fundamentals to optimize prompt execution and understand the mechanics of generative AI systems.
* **Creativity & Ethical Risk Assessment:** Creative design of innovative prompts balanced with a realistic evaluation of technology risks to ensure responsible and ethical AI deployment.

### Core & Advanced Prompting Techniques
* **Zero-shot Prompting:** Querying the model to perform a task it has not been explicitly trained on without providing prior examples, testing its ability to generate relevant results independently.
* **Few-shot Prompting:** Providing a few sample pairs of [Input -> Output] (shots) within the context to help the model learn patterns and align with expected deliverables.
* **Chain-of-Thought (CoT) Prompting:** Instructing the model to break down complex tasks into intermediate reasoning steps before outputting a final answer, significantly improving NLP comprehension and logical accuracy.

### Best Practices
> **Golden Rule:** Clear, context-rich prompts produce optimal results.

1. **Be Specific and Explicit:** Define personas, output formats (JSON, Markdown, YAML), constraints, and boundaries.
2. **Understand Model Characteristics:** Tailor prompts to specific model strengths (e.g., ChatGPT for text ingestion/summarization vs. search-enabled models for real-time facts).
3. **Iterative Refinement:** Continuously test prompts across edge cases to minimize AI hallucinations and biased outputs.

---

## 2. Context Engineering

Context engineering is the overarching discipline of deliberately designing, structuring, and optimizing *everything* an LLM sees at inference time. It treats the context window as the model's short-term working memory.

### Elements of Context at Inference Time
* **System Prompt:** Core rules, guidelines, operational constraints, and persona.
* **User Query:** The active prompt submitted by the user.
* **Retrieved Information:** External documents or facts fetched via RAG or databases.
* **Structured Data:** Schemas, JSON objects, or CSV data injected into the window.
* **Interaction History:** The ongoing conversation transcript between the user and AI.
* **Tool Outputs:** Execution results from external APIs, code interpreters, or sub-agents.

### The 6 Key Steps of Context Management
1. **Context Selection:** Filtering out redundant or irrelevant data, reranking information, and preventing *Context Poisoning* (malicious or inaccurate data entering the context window).
2. **Context Structuring:** Organizing the context using standard data formats (Markdown, JSON) to clearly separate instructions from data and examples.
3. **Prompt Design & Engineering:** Defining rules, guardrails, and output format requirements.
4. **Context Compression:** Fitting the maximum amount of high-value information into a limited token budget without losing critical semantic meaning.
5. **Context Sequencing:** Managing the order of conversation history and retrieved data to maximize model attention efficiency.
6. **Tool & Memory Integration:** Bridging the LLM context window with short/long-term memory stores and external agentic tools.