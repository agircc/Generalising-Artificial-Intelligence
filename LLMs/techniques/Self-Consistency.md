## 🔍 Problem Being Solved

Large Language Models (LLMs) like GPT-3 often struggle with **multi-step reasoning tasks** such as math word problems or commonsense questions. While **Chain-of-Thought (CoT) prompting** helps by generating intermediate reasoning steps, it typically relies on **greedy decoding**—which only selects one reasoning path.
This can lead to errors due to:

* Local optima in reasoning paths
* Overconfidence in a single, potentially flawed output
* Inability to leverage the model’s capacity for diverse thinking

**Goal**: Improve reasoning accuracy and robustness by **leveraging multiple diverse reasoning paths** rather than relying on just one.

---

## 🧠 What Is Self-Consistency?

**Self-consistency** is a **decoding strategy** for CoT prompting that:

* Samples multiple reasoning paths from the language model
* Aggregates the answers from these paths
* Selects the **most consistent answer** (e.g., via majority vote)

### Core Idea:

> If several different ways of thinking lead to the same answer, that answer is likely to be correct.

This mirrors how humans gain confidence in a solution when multiple methods point to the same conclusion.

---

## ⚙️ How to Use Self-Consistency

1. **Prompt the model** with a few examples using Chain-of-Thought formatting.
2. **Sample multiple outputs** (e.g., 20–40) instead of generating just one. Use temperature or top-k sampling to ensure diversity.
3. **Extract the final answer** from each sampled reasoning path.
4. **Aggregate the answers** using:

   * **Majority vote** (most common answer), or
   * **Probability-weighted vote** (if probabilities are available)
5. **Use the aggregated answer** as the final, self-consistent prediction.

This approach is plug-and-play: no fine-tuning or extra models needed.

---

## 🧩 General Methodology for Other Contexts

This idea can be **generalized beyond language models or CoT prompting**:

### ✅ Self-Consistency Framework:

1. **Identify a problem** that involves multiple steps or ambiguous reasoning paths.
2. **Generate multiple diverse solutions** to the same problem using a stochastic or exploratory process.
3. **Define a consistency criterion** (e.g., answer agreement, logic alignment, or semantic similarity).
4. **Aggregate results** to select the most consistent or commonly recurring solution.

### 🔄 Applicable Domains:

* **Multi-agent reasoning**: Agents propose different plans; choose the plan agreed upon by most.
* **Computer vision**: Ensemble outputs from diverse augmentations and select the most frequent classification.
* **Code generation**: Generate multiple solutions to the same programming problem and pick the one with consistent outputs.
* **Scientific hypotheses**: Propose multiple explanations, test them, and converge on the most consistent with known facts.

---

## 🧠 Benefits of the Approach

* Improved **accuracy**, especially in complex tasks.
* Better **robustness** to prompt errors or misleading reasoning paths.
* Built-in **uncertainty estimation**: if all paths disagree, model confidence is low.
* No need for labeled data or fine-tuning.

## Reference
Wang, X., Wei, J., Schuurmans, D., Le, Q., Chi, E., Narang, S., Chowdhery, A., & Zhou, D. (2022). Self-Consistency Improves Chain of Thought Reasoning in Language Models. https://doi.org/10.48550/arxiv.2203.11171

