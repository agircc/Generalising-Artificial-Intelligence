# Adapter Modules

## Definition

Lightweight neural modules inserted between frozen transformer layers to enable task-specific adaptation without modifying pre-trained weights.

## Architecture

```
Output = LayerNorm(Input + Adapter(Input))
```

Adapter structure:
- Down-projection: d → r (bottleneck)
- Non-linearity (ReLU/GELU)
- Up-projection: r → d
- Residual connection

## Types

### Standard Adapters
- **Bottleneck Design**: Reduce then expand dimensions
- **Layer Placement**: After attention and feed-forward layers
- **Skip Connections**: Preserve original information flow

### Variants
- **Prefix Adapters**: Learnable prefix tokens
- **Parallel Adapters**: Parallel to existing layers
- **Scaled Adapters**: Adaptive scaling factors

## Benefits

| Advantage | Description |
|-----------|-------------|
| **Parameter Efficiency** | <1% of original parameters |
| **Modularity** | Easy task switching |
| **Stability** | Preserves pre-trained knowledge |
| **Compatibility** | Works with any transformer |

## Applications

- Cross-lingual transfer
- Domain adaptation
- Multi-task learning
- Few-shot learning

## Design Considerations

- **Bottleneck Size**: Trade-off between efficiency and capacity
- **Placement Strategy**: Which layers to insert adapters
- **Initialization**: Proper initialization for stable training
