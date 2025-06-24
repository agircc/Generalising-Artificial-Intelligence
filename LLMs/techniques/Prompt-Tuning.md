# Prompt Tuning

## Definition

Parameter-efficient method that optimizes continuous prompt embeddings while keeping the entire pre-trained model frozen.

## Architecture

```
Input: [Soft Prompts] + [Hard Text Tokens]
```

- **Soft Prompts**: Learnable continuous embeddings (not discrete tokens)
- **Hard Prompts**: Fixed text tokens
- **Model**: Completely frozen pre-trained parameters

## Key Characteristics

- **Tunable Parameters**: Only prompt embeddings (~0.01% of model)
- **Task Conditioning**: Different prompts for different tasks
- **No Model Modification**: Original model remains unchanged
- **Fast Adaptation**: Quick training and deployment

## Comparison with Alternatives

| Method | Parameters | Training Speed | Performance |
|--------|------------|----------------|-------------|
| **Full Fine-tuning** | 100% | Slow | Highest |
| **LoRA** | 0.1-3% | Medium | High |
| **Adapters** | <1% | Medium | High |
| **Prompt Tuning** | <0.1% | Fast | Medium-High |

## Applications

- Multi-task learning
- Few-shot adaptation
- Resource-constrained deployment
- Continual learning
- Model serving optimization

## Design Choices

- **Prompt Length**: 20-100 tokens typically
- **Initialization**: Random or from vocabulary embeddings
- **Placement**: Prefix, suffix, or interleaved
- **Optimization**: AdamW with learning rate scheduling

## Advantages

- Minimal storage requirements
- Fast task switching
- No catastrophic forgetting
- Preserves model integrity
