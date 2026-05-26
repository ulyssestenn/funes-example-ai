---
title: Compute-optimal training (Chinchilla scaling)
type: concept
tags: [scaling, compute, training]
created: 2026-05-26
updated: 2026-05-26
---
# Compute-optimal training (Chinchilla scaling)
Given a fixed compute budget, how large a model and how many training tokens minimize loss? [Chinchilla](../sources/chinchilla-compute-optimal.md) found that model size N and training tokens D should scale **equally** — roughly N_opt ∝ C^0.34 and D_opt ∝ C^0.28, i.e. for every doubling of model size, double the data (~20 tokens per parameter). This corrected the earlier [Kaplan scaling laws](./scaling-laws.md), whose recommendation to grow models faster than data left contemporary LLMs significantly **undertrained**.

The validating model, Chinchilla (70B params, 1.4T tokens), beat the 4× larger Gopher (280B) and GPT-3 (175B) at the same compute, while also being cheaper to run. A practical consequence: high-quality data volume becomes the new scaling bottleneck.

## Related
- [Scaling laws](./scaling-laws.md)
- [Emergent abilities](./emergent-abilities.md)
## Sources
- [Chinchilla](../sources/chinchilla-compute-optimal.md)
- [Scaling Laws for Neural Language Models](../sources/scaling-laws.md)
## Topics
- [Scaling and emergence](../topics/scaling-and-emergence.md)
