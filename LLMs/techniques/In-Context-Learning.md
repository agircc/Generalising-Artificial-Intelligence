# In-Context Learning

## Definition

Learning paradigm where models adapt to new tasks using examples provided in the input context without updating model parameters.

## Mechanism

```
Prompt: [Task Description] + [Examples] + [Query]
Response: [Prediction]
```

- **No Parameter Updates**: Model weights remain fixed
- **Example-Based Learning**: Few-shot demonstrations guide behavior
- **Emergent Ability**: Appears in sufficiently large models

## Types

### Few-Shot Learning
- **k-shot**: k examples per class
- **Typical Range**: 1-10 examples
- **Performance**: Improves with more examples

### Zero-Shot Learning
- **No Examples**: Task description only
- **Instruction Following**: Relies on pre-training knowledge
- **Generalization**: Tests model's broad capabilities

## Key Factors

| Factor | Impact | Optimization |
|--------|--------|--------------|
| **Example Selection** | High | Representative, diverse samples |
| **Example Ordering** | Medium | Consistent format, logical sequence |
| **Prompt Format** | High | Clear instructions, consistent structure |
| **Context Length** | High | Balance between examples and efficiency |

## Advantages

- **No Training Required**: Immediate deployment
- **Flexible**: Easy task switching
- **Interpretable**: Clear example-based reasoning
- **Efficient**: No computational overhead

## Limitations

- **Context Window**: Limited by maximum sequence length
- **Inconsistent**: Performance varies with examples
- **Scale Dependent**: Requires large models
- **Example Sensitive**: Quality and selection matter greatly

## Applications

- Rapid prototyping
- Domain adaptation
- Multi-task inference
- Interactive AI systems
