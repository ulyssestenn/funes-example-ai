---
title: Training Compute-Optimal Large Language Models (Chinchilla)
type: source
tags: [scaling, compute, training]
created: 2026-05-26
updated: 2026-05-26
---
# Training Compute-Optimal Large Language Models (Chinchilla)
- **Raw file:** [TrainingComputeOptimal.pdf](../../raw/TrainingComputeOptimal.pdf)
- **Original:** Hoffmann, Borgeaud, Mensch, Sifre et al. (DeepMind), 2022 ([arXiv:2203.15556](https://arxiv.org/abs/2203.15556))

## Summary
Argues that contemporary LLMs are significantly **undertrained** because the field over-emphasized parameter count while holding data roughly fixed (~300B tokens). Training over 400 models (70M–16B params on 5B–500B tokens), the authors find model size and training tokens should scale **equally**. They validate this with **Chinchilla** (70B params, 1.4T tokens) at Gopher's compute budget; it outperforms much larger models.

## Key takeaways
- Compute-optimal rule: for every doubling of model size, double the training tokens (~20 tokens per parameter), correcting Kaplan et al.
- Parametric fit gives N_opt ∝ C^0.34 and D_opt ∝ C^0.28 (roughly equal exponents).
- Chinchilla (70B, 1.4T tokens) beats Gopher (280B), GPT-3 (175B), Jurassic-1 (178B), MT-NLG (530B).
- SOTA 67.5% average on MMLU, >7% over Gopher.
- Smaller compute-optimal models also cut inference/fine-tuning cost.
- High-quality data volume becomes the new scaling bottleneck.

## Concepts extracted
- [Compute-optimal training](../concepts/compute-optimal-training.md)
- [Scaling laws](../concepts/scaling-laws.md)
