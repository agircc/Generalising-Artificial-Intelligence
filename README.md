# Generalising Artificial Intelligence

## Project Overview

This repository provides a comprehensive collection of research on Artificial General Intelligence (AGI), organizing key theories, techniques, and challenges that define the path toward building truly general AI systems. The content covers a wide range of approaches to AGI, with a special focus on modern Large Language Model (LLM) methodologies—their limitations and the techniques developed to overcome them.

The project serves as a knowledge base for researchers, practitioners, and enthusiasts interested in understanding the multifaceted landscape of AGI research, from symbolic reasoning systems to neural architectures, and from cognitive theories to practical implementation challenges.

---

## Part I: General AI Theories and Techniques

### AI Theories

| Theory | Description |
|---------|-------------|
| [**Knowledge Representation**](theories/Knowledge-Representation.md) | Methods for formally structuring knowledge so machines can reason, learn, and make decisions, covering logic-based, semantic networks, and vector embedding approaches |
| [**Reasoning**](theories/Reasoning.md) | The process by which AI systems draw logical conclusions and make decisions, encompassing deductive, inductive, abductive, and commonsense reasoning types |
| [**Planning**](theories/Planning.md) | Fundamental AI subfield concerned with devising sequences of actions to achieve desired goals from initial states, including classical planning techniques and modern LLM-based approaches |
| [**Memories**](theories/Memories.md) | Specialized memory systems in AGI architectures including sensory, perceptual associative, spatial, episodic, declarative, procedural, and sequence memory types |
| [**Continuous Learning**](theories/Continuous-Learning.md) | The ability of models to incrementally learn from new data over time without forgetting previous knowledge, addressing catastrophic forgetting challenges |
| [**Critical Thinking**](theories/Critical-Thinking.md) | Advanced reasoning capabilities that enable systematic evaluation and analysis of information and arguments |
| [**Cognitive Architecture**](theories/Cognitive-Architecture.md) | Computational frameworks that model human cognitive processes and structures for building intelligent systems |
| [**Evaluation**](theories/Evaluation.md) | Methods and metrics for assessing AI system performance, capabilities, and limitations across different tasks and domains |
| [**Out-of-Distribution**](theories/Out-of-Distribution.md) | Challenges and approaches for handling data and scenarios that differ from training distributions |
| [**Curriculum Learning**](theories/Curriculum-Learning.md) | Training strategies that present learning materials in a structured progression from simple to complex |
| [**Argument from the Poverty of the Stimulus**](theories/Argument-from-the-Poverty-of-the-Stimulus.md) | Linguistic argument that children acquire complex language knowledge from limited input, with implications for efficient learning in AI systems |

### AI Techniques

| Technique | Description |
|-----------|-------------|
| [**Convolutional Neural Networks (CNN)**](techniques/CNN.md) | Deep learning models designed for grid-like data such as images, using convolution and pooling layers for hierarchical feature extraction |
| [**Deep Neural Networks (DNN)**](techniques/DNN.md) | Multi-layer artificial neural networks that form the foundation of modern AI, capable of learning complex patterns from raw data |
| [**Joint Embedding Predictive Architecture (JEPA)**](techniques/JEPA.md) | Self-supervised learning architecture that predicts internal representations of future or hidden parts of input, focusing on learning world structure |
| [**Planning Domain Definition Language (PDDL)**](techniques/PDDL.md) | Standard declarative language for formally describing planning problems and domains, widely used in AI planning competitions |
| [**Local Search for Planning Graphs (LPG)**](techniques/LPG.md) | Automated AI planner using local search strategies over planning graph representations for efficient action plan generation |
| [**Knowledge Graphs**](techniques/Knowledge-Graph.md) | Structured representations of facts and relationships between real-world entities, enabling semantic understanding and reasoning |
| [**Mamba**](techniques/Mamba.md) | Novel neural network architecture based on state space models, designed to replace Transformers with improved efficiency for long sequences |
| [**Reinforcement Learning (RL)**](techniques/RL.md) | Machine learning paradigm where agents learn optimal decision-making through interaction with environments using reward signals |
| [**Transformers**](techniques/Transformer.md) | Deep learning architecture using self-attention mechanisms, foundational to modern NLP models like BERT and GPT |
| [**Recurrent Neural Networks (RNN)**](techniques/RNN.md) | Neural networks designed for sequential data processing, maintaining memory of past inputs through internal loops |
| [**Non-Axiomatic Reasoning System (NARS)**](techniques/NARS.md) | General-purpose AI system designed for reasoning and learning in uncertain, incomplete, and changing environments |
| [**SOAR**](techniques/SOAR.md) | Cognitive architecture using State-Operator-Result structure for general problem-solving with goal-directed behavior and chunking learning |
| [**Cyc**](techniques/Cyc.md) | Symbolic AI system containing millions of human-level facts and formal logic rules for common sense reasoning |
| [**Learning Intelligent Distribution Agent (LIDA)**](techniques/LIDA.md) | Cognitive architecture simulating human mind processes through cognitive cycles, perception, memory, and decision-making |
| [**Hierarchical Temporal Memory (HTM)**](techniques/HTM.md) | Brain-inspired machine learning model based on neocortex structure, focusing on online learning and temporal pattern recognition |

---

## Part II: Large Language Model Challenges and Solutions

### LLM Problems

| Problem | Description |
|---------|-------------|
| [**Hallucination**](LLMs/problems/Hallucination.md) | LLMs generate plausible but factually incorrect or fabricated content, posing risks in critical domains |
| [**Lack of Interpretability**](LLMs/problems/Lack-of-Interpretability.md) | Black-box nature of LLMs makes it difficult to understand reasoning processes, limiting trust and accountability |
| [**Limited Reasoning Ability**](LLMs/problems/Limited-Reasoning-Ability.md) | Struggles with multi-step reasoning, mathematical problems, and causal inference requiring deliberate thought |
| [**Bias in Training Data**](LLMs/problems/Bias-in-Training-Data.md) | LLMs inherit and amplify social, gender, racial, and cultural biases present in training datasets |
| [**Context Window Limitation**](LLMs/problems/Context-Window-Limitation.md) | Autoregressive processing leads to quadratic scaling of computation and memory with context length |
| [**Outdated Knowledge**](LLMs/problems/Outdated-Knowledge.md) | Static training means LLMs cannot reflect real-time changes in world knowledge without retraining |
| [**Overreliance on Surface Patterns**](LLMs/problems/Overreliance-on-Surface-Patterns.md) | Performance drops when familiar tokens are replaced, revealing pattern matching rather than true reasoning |
| [**Brittleness to Prompt Variations**](LLMs/problems/Brittleness-to-Prompt-Variations.md) | Small changes in prompt phrasing can significantly degrade output quality and consistency |
| [**Confidently Wrong Outputs**](LLMs/problems/Confidently-Wrong-Outputs.md) | LLMs deliver incorrect answers with high fluency and confidence, misleading users |
| [**High Computational Cost**](LLMs/problems/Hight-Computational-Cost.md) | Training and fine-tuning require massive resources, limiting accessibility and raising sustainability concerns |
| [**Lack of Grounded Understanding**](LLMs/problems/Lack-of-Grounded-Understanding.md) | Reliance on surface-level pattern recognition without true semantic understanding or world grounding |
| [**Vulnerability to Prompt Injection**](LLMs/problems/Vulnerability-to-Prompt-Injection.md) | Malicious prompts can manipulate LLMs to bypass safety filters or produce harmful content |

### LLM Techniques

| Technique | Description |
|-----------|-------------|
| [**Fine-Tuning**](LLMs/techniques/Fine-Tuning.md) | Training technique that adapts pre-trained models to specific tasks or domains by updating model parameters |
| [**Adapter Modules**](LLMs/techniques/Adapter-Modules.md) | Lightweight modules inserted into pre-trained models for task-specific adaptation without full fine-tuning |
| [**aLoRA**](LLMs/techniques/aLoRA.md) | Advanced Low-Rank Adaptation technique for efficient parameter-efficient fine-tuning of large language models |
| [**LoRA**](LLMs/techniques/LoRA.md) | Low-Rank Adaptation method for efficient fine-tuning by adding trainable low-rank matrices to attention layers |
| [**Tool Integration**](LLMs/techniques/Tool-Integration.md) | Techniques for enabling LLMs to effectively use external tools and APIs to extend their capabilities |
| [**Tree-of-Thought**](LLMs/techniques/Tree-of-Thought.md) | Reasoning approach that explores multiple reasoning paths in a tree-like structure for complex problem solving |
| [**In-Context Learning**](LLMs/techniques/In-Context-Learning.md) | Learning paradigm where models adapt to new tasks using examples provided in the input context |
| [**Prompt Tuning**](LLMs/techniques/Prompt-Tuning.md) | Parameter-efficient fine-tuning method that optimizes continuous prompt embeddings while keeping model weights frozen |
| [**LLM-Modulo Framework**](LLMs/techniques/LLM-Modulo.md) | Neuro-symbolic framework using LLMs as idea generators with external verifiers in a Generate-Test-Critique loop |
| [**AgentTuning**](LLMs/techniques/AgentTuning.md) | Training method to enhance generalized agent abilities in LLMs while preserving general language understanding |
| [**Self-Refine**](LLMs/techniques/Self-Refine.md) | Zero-shot iterative framework enabling LLMs to improve their own outputs through self-feedback and revision |
| [**LLM+P**](LLMs/techniques/LLM-P.md) | Modular framework enhancing LLMs with optimal planning by integrating classical symbolic planners |
| [**ProgPrompt**](LLMs/techniques/ProgPrompt.md) | Programming-inspired prompting framework for robot task planning using structured, executable code-like prompts |
| [**Self-Consistency**](LLMs/techniques/Self-Consistency.md) | Decoding strategy that samples multiple reasoning paths and selects the most consistent answer via majority vote |

---

## Contributing

This project welcomes contributions in the form of:
- Additional theories and techniques documentation
- Updates to existing content with new research findings
- Corrections and improvements to current descriptions
- New problem identifications and solution approaches

Please ensure all contributions maintain the professional, academic tone and include proper references where applicable.

---

## License

This project is licensed under the terms specified in the [LICENSE](LICENSE) file.