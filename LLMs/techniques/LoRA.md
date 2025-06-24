# Low-Rank Adaptation (LoRA)

## Definition

Parameter-efficient fine-tuning method that adds trainable low-rank matrices to attention layers while keeping original weights frozen.

## Architecture

```
W = W₀ + ΔW = W₀ + BA
```

Where:
- `W₀`: Frozen pre-trained weights
- `B ∈ ℝᵈˣʳ`, `A ∈ ℝʳˣᵏ`: Trainable low-rank matrices
- `r`: Rank (typically r << min(d,k))

## Key Benefits

- **Memory Efficient**: Only 0.1-3% of original parameters
- **No Inference Latency**: Matrices can be merged during deployment
- **Task Switching**: Easy swapping between different LoRA modules
- **Preserve Knowledge**: Original model remains unchanged

## Hyperparameters

| Parameter | Typical Range | Impact |
|-----------|---------------|--------|
| **Rank (r)** | 8-64 | Higher rank = more capacity |
| **Alpha** | 16-32 | Scaling factor for adaptation |
| **Dropout** | 0.1-0.3 | Regularization |

## Applications

- Multi-task learning
- Personalization
- Domain adaptation
- Continual learning

## Variants

- **AdaLoRA**: Adaptive rank allocation
- **QLoRA**: Quantized LoRA for memory efficiency
