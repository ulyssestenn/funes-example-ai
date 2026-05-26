---
title: Scaling Laws for Neural Language Models
type: source
tags: [scaling, compute, training]
created: 2026-05-26
updated: 2026-05-26
---
# Scaling Laws for Neural Language Models
- **Raw file:** [ScalingLaws.pdf](../../raw/ScalingLaws.pdf)
- **Original:** Kaplan, McCandlish et al. (OpenAI / Johns Hopkins), 2020 ([arXiv:2001.08361](https://arxiv.org/abs/2001.08361))

## Summary
Establishes that the test cross-entropy loss of Transformer language models falls off as a smooth **power law** in three factors — model size (N), dataset size (D), and training compute (C) — across more than seven orders of magnitude. Architectural shape (width vs depth) matters little; scale dominates. Derives how to allocate a fixed compute budget and concludes (later revised by Chinchilla) that the most compute-efficient strategy trains very large models on modest data, stopping well before convergence.

## Key takeaways
- Power laws: L(N) ∝ (N_c/N)^0.076; L(D) ∝ (D_c/D)^0.095; L(C_min) ∝ (·)^0.050.
- Performance depends strongly on scale, weakly on architectural shape.
- Larger models are markedly more **sample-efficient**.
- Overfitting depends predictably on the ratio N^0.74 / D.
- Kaplan's compute-optimal recommendation: scale model size faster than data and stop before convergence (revised by Chinchilla).
- Training curves are universal/predictable, enabling extrapolation of final loss.

## Concepts extracted
- [Scaling laws](../concepts/scaling-laws.md)
- [Compute-optimal training](../concepts/compute-optimal-training.md)
