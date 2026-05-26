---
title: Transformer architecture
type: topic
tags: [transformer, architecture, attention]
created: 2026-05-26
updated: 2026-05-26
---
# Transformer architecture
The attention-based neural architecture that replaced recurrence and convolution for sequence modeling and became the foundation of modern LLMs. This topic covers the core mechanism (attention), how order is represented, and how the pieces assemble into the encoder/decoder stacks reused by every later model.

## Concepts
- [Transformer](../concepts/transformer.md) — the overall encoder–decoder design; residual + layer-norm stacks; encoder-only / decoder-only / encoder–decoder families.
- [Self-attention](../concepts/self-attention.md) — scaled dot-product attention relating all positions in one step.
- [Multi-head attention](../concepts/multi-head-attention.md) — parallel attention over multiple projection subspaces.
- [Positional encoding](../concepts/positional-encoding.md) — injecting token order into a permutation-invariant model.

## Related topics
- [Pre-training and transfer learning](./pretraining-and-transfer-learning.md)
- [Scaling and emergence](./scaling-and-emergence.md)
