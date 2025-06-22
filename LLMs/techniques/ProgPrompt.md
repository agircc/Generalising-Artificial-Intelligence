# 🧠 ProgPrompt: Programming-Inspired Prompting for Robot Task Planning

## ❓ Why ProgPrompt?

Robot task planning in the real world requires two key capabilities:

1. **Commonsense reasoning** — Understanding typical object affordances and logical action sequences.
2. **Situated awareness** — Knowing which objects and actions are currently available in the environment.

While Large Language Models (LLMs) can generate action plans from natural language, they face major challenges:
- ❌ They may generate **invalid or impossible actions** (e.g., referencing unavailable objects).
- ❌ They **lack awareness of the current environment state**, such as the position or presence of objects.
- ❌ They often require **manual scoring or search** over possible actions to ensure correctness.

**ProgPrompt** addresses these limitations by guiding LLMs to generate structured, executable, and context-aware plans using code-like prompts.

---

## 💡 What is ProgPrompt?

**ProgPrompt** is a **programmatic prompting framework** that leverages LLMs' strengths in:
- Code understanding
- Commonsense reasoning
- Few-shot generalization

### Key features of ProgPrompt:
- ✅ **Import statements** for robot action primitives (e.g., `grab`, `putin`, `open`, `close`)
- ✅ **Object list** that reflects the current scene
- ✅ **Natural language comments** to describe plan steps (like a chain-of-thought)
- ✅ **Assertions** to check preconditions before executing an action, with built-in recovery
- ✅ **Example task functions** showing how to complete related tasks

This structure allows the LLM to **output complete executable Python-like plans** that are syntactically valid and semantically grounded.

---

## 🛠 How to Use ProgPrompt

1. **Declare robot capabilities**:
   ```python
   from actions import grab, putin, open, close, switchon, switchoff
   ```

2. **List objects currently in the environment**:

```
objects = ['salmon', 'microwave', 'plate', 'bowl', 'fridge']
```

3. **Provide a few example task plans:**
```
def throw_away_lime():
    # 1: find lime
    find('lime')
    # 2: grab lime
    grab('lime')
    # 3: open garbagecan
    open('garbagecan')
    # 4: put lime in garbagecan
    putin('lime', 'garbagecan')
    # 5: close garbagecan
    close('garbagecan')
```

4. **Prompt the LLM to complete a new function:**
```
def microwave_salmon():
    # 1: walk to kitchen
    walk('kitchen')
    # 2: find microwave
    find('microwave')
    # 3: open microwave
    assert('microwave' is 'closed') else: close('microwave')
    open('microwave')
    # 4: grab salmon
    assert('close' to 'salmon') else: find('salmon')
    grab('salmon')
    # 5: put salmon in microwave
    putin('salmon', 'microwave')
    # 6: close and start microwave
    close('microwave')
    switchon('microwave')
    ...
```

5. **Execute the generated plan:**
- In a simulator (e.g., VirtualHome)
- On a physical robot (with perception + grasping)

## 🔍 Implications
✅ Benefits of ProgPrompt:
- Executable output: The plans directly correspond to the robot’s available APIs and environment objects.
- Robust to errors: Uses assert statements and fallback actions to recover from unmet conditions.
- Highly generalizable: Easily adapted to new environments and new robots by changing the object list and action imports.
- Human-readable: Program format is interpretable and debuggable by humans.
- Code-native prompting: Leverages LLMs’ proficiency with code to produce logically valid sequences.

## 📈 Empirical Results:
Outperforms natural-language-based prompting baselines and open-ended plan generation.

Achieves high executability and goal completion in both simulated and real-world experiments.

CODEX > GPT-3 due to code fine-tuning, but base GPT-3 already performs well with ProgPrompt.





## Methodology
**Programmatic Prompting Methodology: Making LLM Plans Executable and Grounded**

This methodology is applicable to any domain where tasks need to be translated from high-level natural language descriptions into **structured, executable sequences**. Examples include robotic systems, software automation, virtual agents, educational tools, or intelligent assistants.

---

### **Step 1: Define the Action API**

Clearly define the set of primitive actions available in the environment or system.

* These actions should be represented as function names with parameters.
* Examples:

  * For software automation: `open(file)`, `click(button)`, `fill(form, data)`
  * For virtual characters: `walk_to(location)`, `speak(text)`, `interact_with(object)`
  * For household robots: `grab(obj)`, `putin(obj1, obj2)`, `open(container)`

This step constrains the LLM’s output space to only include allowed and meaningful operations.

---

### **Step 2: Provide Current Context**

List all **available objects or entities** in the current environment or task state.

* Use explicit object lists like:

  ```
  objects = ['banana', 'bowl', 'fridge', 'microwave']
  ```
* This ensures that the LLM only plans using relevant entities, avoiding hallucinations.

---

### **Step 3: Use Code-Like Prompting Structure**

Frame your prompt as if you are writing **part of a real program**, even if you’re not executing it as code.

* Structure the plan as a function:

  * Function name = task name (e.g., `def make_toast():`)
  * Body = sequence of action function calls
  * Add inline **natural language comments** to explain the purpose of each step
* Example:

  ```python
  def throw_away_apple():
      # Step 1: find apple
      find('apple')
      # Step 2: open garbage can
      open('garbagecan')
      # Step 3: put apple in garbage can
      putin('apple', 'garbagecan')
  ```

---

### **Step 4: Include a Few Example Programs**

Use few-shot prompting by providing 2–3 complete examples of prior task plans.

* These help the LLM learn:

  * How to structure the function
  * How to break down high-level goals into concrete actions
  * What valid syntax and semantics look like

---

### **Step 5: Prompt the LLM to Generate a New Task Plan**

Provide a high-level task goal (e.g., "clean the table") and ask the LLM to generate a structured function.

* Optionally, start the function definition and let the model complete it:

  ```python
  def clean_table():
      # Step 1: ...
  ```

---

### **Step 6: Use Assertions and Recovery (Optional)**

If your system allows environment state feedback, use **assert statements** to verify preconditions before each action.

* Example:

  ```python
  assert('apple' in 'hands') else: grab('apple')
  ```
* This adds robustness to the plan and handles dynamic conditions during execution.

---

### **Step 7: Map and Execute**

Take the LLM-generated plan and **map each action to a real system command**.

* Each function call (e.g., `grab('banana')`) should correspond to:

  * A callable API
  * A UI automation step
  * A physical robot skill
* Ensure environment compatibility before execution (e.g., object exists, action supported).

---

### **Implications and Best Use Cases**

**Domains that benefit from this method:**

* Robotics and autonomous agents
* RPA (Robotic Process Automation)
* Intelligent tutoring systems
* Game AI/NPC scripting
* Workflow management platforms
* Virtual assistants (task orchestration)

**Key benefits:**

* Encourages **structured thinking** in LLMs
* Prevents **action hallucination** by grounding in real actions and objects
* Produces **executable and interpretable plans**
* Easily extensible to new environments by changing action lists and context

## Reference
Singh, I., Blukis, V., Mousavian, A., Goyal, A., Xu, D., Tremblay, J., Fox, D., Thomason, J., & Garg, A. (2023). ProgPrompt: Generating Situated Robot Task Plans using Large Language Models. 2023 IEEE International Conference on Robotics and Automation (ICRA), 11523–11530. https://doi.org/10.1109/ICRA48891.2023.10161317
