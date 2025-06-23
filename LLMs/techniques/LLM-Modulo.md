## 🧩 What Problem Does LLM-Modulo Try to Solve?

The paper addresses a growing misconception in the AI community: that **Large Language Models (LLMs)**, by themselves, are capable of performing **planning** and **self-verification** tasks.

However, the authors argue:

* LLMs are fundamentally **System 1** tools (fast, intuitive, approximate) and lack **System 2** reasoning abilities (deliberate, logical, verifiable).
* LLMs often generate **plausible-sounding but incorrect plans**, and they **cannot reliably check or improve their own outputs**.
* There is a need for a framework where LLMs are **useful without overestimating their capabilities**.

---

## 🧠 What Is LLM-Modulo?

**LLM-Modulo** is a **neuro-symbolic planning framework** where:

* LLMs are used **not as planners**, but as **approximate knowledge sources and idea generators**.
* External **verifiers/critics** (symbolic or simulator-based) evaluate and refine the outputs from the LLM.
* The system forms a **Generate-Test-Critique loop** to arrive at **correct, executable plans**.

The term "Modulo" is inspired by **SAT Modulo Theories** — indicating that LLMs operate **under the guidance of external, trustworthy components**.

---

## 🛠 How to Use the LLM-Modulo Framework?

### Workflow:

1. **Problem Specification**
   A planning problem is defined (in natural language or structured form).

2. **LLM Guessing**
   The LLM generates a candidate plan, domain model, or reformulated specification.

3. **Critique Phase**
   A **bank of critics** evaluates the candidate based on:

   * Hard constraints: logical correctness, action preconditions/effects.
   * Soft constraints: preferences, human-likeness, style.

4. **Meta Controller (Backprompting)**
   Gathers critic feedback and prompts the LLM to revise the candidate.

5. **Repeat**
   The loop continues until a **valid solution** is confirmed by all relevant critics.

### Roles of the LLM:

* Generate plausible plan candidates.
* Translate formats (e.g., from natural language to PDDL).
* Assist in domain model acquisition.
* Refine incomplete user goals.
* Suggest types of critics needed.

---

## ✅ Generalizable Methodology for Other Contexts

The **LLM-Modulo approach** can be extended to any task involving structured decision-making, where correctness matters but LLMs cannot be trusted alone:

| Application Area           | LLM Role                                    | External Critics                          |
| -------------------------- | ------------------------------------------- | ----------------------------------------- |
| **Reinforcement Learning** | Generate policies, reward functions         | Simulator, evaluator                      |
| **Robotics**               | Propose action sequences, translate formats | Safety checker, motion planner            |
| **Software Engineering**   | Generate code stubs, comments, tests        | Type checker, unit tests                  |
| **Travel Planning**        | Suggest itineraries, format plans           | Budget/time checker, diversity critic     |
| **Education**              | Generate quiz questions, explanations       | Curriculum constraints, factual validator |

**Core Methodology:**

1. Let LLMs ideate freely (generate).
2. Critically evaluate with formal tools or simulators (test).
3. Loop with feedback until constraints are met (critique).
4. Optional: fine-tune with verified examples for future use.

---


## Reference
Kambhampati, S., Valmeekam, K., Guan, L., Verma, M., Stechly, K., Bhambri, S., Saldyt, L., & Murthy, A. (2024). LLMs Can’t Plan, But Can Help Planning in LLM-Modulo Frameworks. https://doi.org/10.48550/arxiv.2402.01817
