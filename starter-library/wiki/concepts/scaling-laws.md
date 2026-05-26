---
title: Scaling laws
type: concept
tags: [scaling, compute]
created: 2026-05-26
updated: 2026-05-26
---
# Scaling laws
Empirical **power-law** relationships between a language model's test loss and the scale factors of training: model size N, dataset size D, and compute C. When not bottlenecked by the others, loss falls as `L(X) ∝ X^(−α)` for each factor, with fitted exponents (Kaplan et al.: α_N ≈ 0.076, α_D ≈ 0.095, α_C ≈ 0.050) holding across more than seven orders of magnitude. Performance depends strongly on scale and only weakly on architectural shape (depth vs width), and the curves are smooth enough to **extrapolate** final loss from early training.

Crucially, scaling laws predict *loss*, not specific task performance — which can appear discontinuously (see [emergent abilities](./emergent-abilities.md)). They also imply an optimal compute allocation, refined by [compute-optimal training](./compute-optimal-training.md).

## Related
- [Compute-optimal training](./compute-optimal-training.md)
- [Emergent abilities](./emergent-abilities.md)
- [In-context learning](./in-context-learning.md)
## Sources
- [Scaling Laws for Neural Language Models](../sources/scaling-laws.md)
- [Chinchilla](../sources/chinchilla-compute-optimal.md)
- [GPT-3](../sources/gpt-3-few-shot-learners.md)
## Topics
- [Scaling and emergence](../topics/scaling-and-emergence.md)
