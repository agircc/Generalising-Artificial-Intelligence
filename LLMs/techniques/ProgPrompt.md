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

🧪 In summary, ProgPrompt is a simple yet powerful method that bridges natural language understanding and symbolic robot control using structured code-based prompting.