---
title: Attention Is All You Need
type: source
tags: [transformer, attention, architecture]
created: 2026-05-26
updated: 2026-05-26
---
# Attention Is All You Need
- **Raw file:** [AttentionIsAllYouNeed.pdf](../../raw/AttentionIsAllYouNeed.pdf)
- **Original:** Vaswani et al., 2017 — NeurIPS 2017 ([arXiv:1706.03762](https://arxiv.org/abs/1706.03762))

## Summary
Introduces the **Transformer**, a sequence-transduction architecture built entirely on attention, dispensing with recurrence and convolution. Removing sequential dependencies enables far more parallelization and shorter paths between distant tokens. It set new machine-translation state of the art while training in a fraction of the time of prior models, and became the substrate for essentially all later LLMs.

## Key takeaways
- 28.4 BLEU on WMT'14 EN–DE (>2 BLEU over prior best, including ensembles); 41.8 BLEU single-model on EN–FR.
- Big model trained in 3.5 days on eight P100 GPUs — a small fraction of prior SOTA cost.
- Encoder–decoder, each a stack of N=6 identical layers; d_model=512, FFN inner dim 2048, h=8 heads (d_k=d_v=64).
- Self-attention connects all positions in O(1) sequential operations vs O(n) for recurrence, easing long-range dependencies.
- The 1/√d_k scaling keeps softmax out of small-gradient regions for large d_k.
- Generalized to English constituency parsing, showing the architecture is not translation-specific.

## Concepts extracted
- [Self-attention](../concepts/self-attention.md)
- [Multi-head attention](../concepts/multi-head-attention.md)
- [Positional encoding](../concepts/positional-encoding.md)
- [Transformer](../concepts/transformer.md)
