## 🧩 Problem to Solve

Large Language Models (LLMs) like GPT-4 are impressive in generating natural language responses and demonstrating linguistic competence. However, they **fail at solving complex long-horizon planning problems**—such as those found in robotics—because they lack:

* Reliable reasoning about **preconditions and consequences** of actions.
* The ability to ensure **feasibility or optimality** of action sequences.

In contrast, **classical symbolic planners** excel at these tasks when given a structured problem. The paper seeks to **combine the strengths of both LLMs and classical planners** to overcome these limitations.

---

## 🔧 What is LLM+P?

**LLM+P** is a modular framework that enhances LLMs with **optimal planning capabilities** by integrating them with symbolic **classical planners**.

It allows an LLM to:

1. **Translate** a natural language description of a task into a structured PDDL (Planning Domain Definition Language) format.
2. **Call a symbolic planner** (e.g., Fast-Downward) to compute a valid or optimal plan.
3. **Convert the resulting plan** back into natural language instructions or executable commands.

💡 Key insight: LLMs are **good translators** of natural language → PDDL and back, while classical planners are **good solvers** of planning problems.

---

## ▶️ How to Use LLM+P

The usage process follows three steps:

1. **Input**: Provide a natural language task (e.g., "Place the mustard bottle in the pantry and throw away the soup can").
2. **PDDL Translation**: Use the LLM (with example prompts) to generate a problem-specific PDDL file based on a pre-defined domain file.
3. **Plan Execution**:

   * Feed the PDDL files to a classical planner.
   * Use the LLM to translate the output plan back into human-friendly instructions or robot commands.

🎯 Context (a problem-PDDL pair) is critical to help the LLM generate valid PDDL.

---

## 🧠 Generalizable Methodology

LLM+P provides a **reusable method** for augmenting LLMs with external structured reasoning tools. The pattern is:

### **Modular Augmentation Framework**

1. **LLM as Natural Language Translator**:

   * Translates user input into a structured format required by external tools (e.g., PDDL, math expressions, logical formulas).

2. **External Solver as the Brain**:

   * Executes symbolic reasoning or optimization (e.g., classical planners, solvers, calculators).

3. **LLM as Output Interpreter**:

   * Converts structured results back into natural language or interactive actions.

---

## 📦 Potential Applications Beyond Planning

This framework can be applied to other domains where LLMs lack internal reasoning capabilities:

* **Mathematical problem solving**: LLM → Equation → Calculator → Result → LLM explains.
* **Formal logic tasks**: LLM → Logical expression → Theorem prover → Answer → LLM summarizes.
* **Code synthesis**: LLM → Specification → Static analyzer → Output → LLM explains.
* **Data querying**: LLM → SQL → Query engine → Data → LLM visualizes/explains.

---

## ✅ Summary

* **Problem**: LLMs can't reliably solve complex planning tasks alone.
* **LLM+P**: A hybrid framework that lets LLMs leverage classical planners for accuracy and optimality.
* **Usage**: LLM generates PDDL → Planner finds solution → LLM translates it back.
* **Methodology**: Treat LLMs as natural language translators that interface with reliable external solvers—making LLMs much smarter without retraining.

Let me know if you'd like this turned into slides or diagrams.



## Reference
Liu, B., Jiang, Y., Zhang, X., Liu, Q., Zhang, S., Biswas, J., & Stone, P. (2023). LLM+P: Empowering Large Language Models with Optimal Planning Proficiency. https://doi.org/10.48550/arxiv.2304.11477
