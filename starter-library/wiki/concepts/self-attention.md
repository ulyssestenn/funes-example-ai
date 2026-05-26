---
title: Self-attention
type: concept
tags: [transformer, attention, architecture]
created: 2026-05-26
updated: 2026-05-26
---
# Self-attention
A mechanism that relates different positions of a single sequence to compute a representation of each position as a weighted sum over all positions. The Transformer uses **scaled dot-product attention**: for queries Q, keys K, and values V, it computes `softmax(QKᵀ / √d_k) V`. The 1/√d_k factor keeps the softmax out of saturated, small-gradient regions when d_k is large.

Because every position attends to every other in a single step, self-attention has O(1) sequential path length (vs O(n) for recurrence), which makes long-range dependencies easier to learn and the computation highly parallelizable. In decoders, **causal masking** hides future positions to preserve the autoregressive property.

## Related
- [Multi-head attention](./multi-head-attention.md)
- [Positional encoding](./positional-encoding.md)
- [Transformer](./transformer.md)
## Sources
- [Attention Is All You Need](../sources/attention-is-all-you-need.md)
## Topics
- [Transformer architecture](../topics/transformer-architecture.md)
