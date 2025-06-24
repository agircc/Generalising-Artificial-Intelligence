# Out-of-Distribution (OOD) Generalization

## Problem Definition

Models trained on one distribution often fail when deployed on data from different distributions, limiting real-world applicability.

## Types of Distribution Shift

- **Covariate Shift**: P(X) changes, P(Y|X) remains constant
- **Label Shift**: P(Y) changes, P(X|Y) remains constant  
- **Concept Drift**: P(Y|X) changes over time
- **Domain Shift**: Systematic differences between training and test environments

## Detection Methods

### Statistical Approaches
- **Maximum Mean Discrepancy (MMD)**: Kernel-based distribution comparison
- **Kolmogorov-Smirnov Test**: Statistical hypothesis testing
- **Energy Distance**: Metric-based distribution divergence

### Deep Learning Approaches
- **Uncertainty Estimation**: Bayesian neural networks, dropout
- **Density Models**: Normalizing flows, VAEs
- **Feature-based**: Mahalanobis distance in feature space

## Mitigation Strategies

| Strategy | Approach | Effectiveness |
|----------|----------|---------------|
| **Domain Adaptation** | Align source/target distributions | High for known domains |
| **Data Augmentation** | Expand training distribution | Medium |
| **Robust Training** | Adversarial/distributional training | Medium-High |
| **Meta-Learning** | Learn to adapt quickly | High for few-shot |
