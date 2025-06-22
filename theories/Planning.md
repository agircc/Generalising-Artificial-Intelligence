# 🧠 AI Planning

## What is Planning?

**Planning** is a fundamental subfield of Artificial Intelligence (AI) concerned with devising a **sequence of actions** to achieve a desired goal from a given initial state, optimizing performance measures along the way.

* “Planning is the task of finding a procedural course of action for a declaratively described system to reach its goals while optimizing overall performance measures.”
  — IBM

* “Planning is the art and practice of thinking before acting... to choose the course of action most beneficial with respect to one’s goals.”
  — Patrik Haslum

---

## 📌 The Basic Planning Problem

A classical planning problem consists of:

* **Initial state**: where the system begins
* **Goal states**: what the system aims to reach
* **Actions**: that can transition between states
* **Transition function**: deterministic mapping from current state + action → next state
* **Action cost**: non-negative, used for optimization

The goal is to find a **sequence of actions** that transforms the initial state into a goal state.

### Formal Representation:

```math
S = {S, s₀, S_G, A, f, c}
```

Where:

* `S` is the state space
* `s₀` is the initial state
* `S_G` are goal states
* `A` are actions
* `f(a, s)` is the transition function
* `c(a, s)` is the cost

---

## ❗ Why is Planning Hard?

* **State explosion**: The number of states can be astronomical (e.g., 10¹⁰⁰)
* **Infeasibility of full transition graphs**
* **Need for abstraction and heuristics**

Efficient planning relies on algorithms that avoid full enumeration of the state space.

---

## 🧭 Classical Planning Techniques

1. **STRIPS** (1970s): Backward total-order planning
2. **POCL (Partial Order Causal Link)**: Parallel goal pursuit and threat resolution
3. **GraphPlan** (1995): Builds planning graphs for backward search
4. **Heuristic Search Planning (HSP)**:

   * Uses heuristics derived from relaxed versions of the problem
   * Common relaxation: dropping **delete lists**
   * Defines cost approximation:

     ```math
     h⁺(Π) := c*(Π⁺)
     ```

     where Π⁺ is the relaxed problem

---

## 🧠 Planning in the Age of Large Language Models (LLMs)

Recent research explores how LLMs can participate in or support planning:

### 🔍 Key Strategies ([Huang et al., 2024](https://arxiv.org/abs/2402.02716))

* **Decomposition**: Divide tasks into subtasks (e.g., [ProgPrompt](https://doi.org/10.1109/ICRA48891.2023.10161330), Singh et al., 2023)
* **Multi-Plan Selection**: Generate multiple plans, select the best (e.g., [Self-Consistency](https://arxiv.org/abs/2203.11171), Wang et al., 2022)
* **External Planner Integration**: Use LLMs for task formalization, delegate planning (e.g., [LLM+P](https://arxiv.org/abs/2304.11477), Liu et al., 2023)
* **Self-Refinement**: Iteratively improve plans through feedback (e.g., [Self-Refine](https://papers.nips.cc/paper_files/paper/2023/hash/d9a2f5c8b1f9b58e9e1f3b119a301d7c-Abstract-Conference.html), Madaan et al., 2023)
* **Memory-Augmented Planning**: Use memory to store domain knowledge and past trajectories (e.g., [AgentTuning](https://aclanthology.org/2024.findings-acl.265/), Zeng et al., 2023)

---

## 🔍 Can LLMs Plan Effectively?

Studies suggest limitations:

* **Limited commonsense planning**: LLMs underperform humans in simple tasks (e.g., Blocksworld: 34% vs 78%)
* **Support role is promising**: LLMs as seed generators for symbolic planners improve outcomes
  — [Valmeekam et al., 2023](https://proceedings.neurips.cc/paper_files/paper/2023/hash/93fdb8361dc28ab580b1d087fb09fcd7-Abstract-Conference.html)

---

## 🧩 The LLM-Modulo Framework

A hybrid approach:

* **Generate-Test-Critique loop** ([Kambhampati et al., 2024](https://proceedings.mlr.press/v238/kambhampati24a.html))

  * LLMs propose plans
  * Critics evaluate under hard/soft constraints
  * Humans provide specifications and domain insights

---

## ✅ When to Use Planning?

Planning techniques are especially suitable when:

* The problem is **declaratively describable**
* There is **valuable domain knowledge**
* **Learning methods are ineffective** due to lack of data or structure
* **Explainability** is important
* The problem is **similar to well-studied planning scenarios**