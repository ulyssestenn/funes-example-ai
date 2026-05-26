---
title: Pre-training and transfer learning
type: topic
tags: [pretraining, transfer-learning, objectives]
created: 2026-05-26
updated: 2026-05-26
---
# Pre-training and transfer learning
How models acquire general-purpose knowledge from large unlabeled corpora and then adapt to specific tasks. This topic covers the self-supervised objectives used to pre-train [Transformers](./transformer-architecture.md) and the strategies for adapting them downstream — from gradient fine-tuning to prompting.

## Concepts
- [Transfer learning (pre-train then fine-tune)](../concepts/transfer-learning.md) — the dominant pre-train-then-adapt paradigm.
- [Masked language modeling](../concepts/masked-language-modeling.md) — BERT's bidirectional fill-in-the-blank pre-training objective.
- [Text-to-text framework](../concepts/text-to-text-framework.md) — T5's reframing of every task as string-to-string.
- [Supervised fine-tuning](../concepts/supervised-fine-tuning.md) — adapting on demonstrations (also the first RLHF stage).

## Related topics
- [Transformer architecture](./transformer-architecture.md)
- [Scaling and emergence](./scaling-and-emergence.md)
- [Alignment and preference learning](./alignment-and-preference-learning.md)
