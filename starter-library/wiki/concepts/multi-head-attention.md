---
title: Multi-head attention
type: concept
tags: [transformer, attention, architecture]
created: 2026-05-26
updated: 2026-05-26
---
# Multi-head attention
Rather than computing a single attention function over d_model-dimensional keys, queries, and values, the Transformer linearly projects them h times into lower-dimensional subspaces (in the base model, h=8 with d_k=d_v=64), runs [self-attention](./self-attention.md) in parallel in each, then concatenates and projects the results. Each head can attend to information from a different representation subspace and position, which a single averaged head would blur together.

The total cost is similar to single-head attention at full dimension, since each head operates at reduced dimension.

## Related
- [Self-attention](./self-attention.md)
- [Transformer](./transformer.md)
## Sources
- [Attention Is All You Need](../sources/attention-is-all-you-need.md)
## Topics
- [Transformer architecture](../topics/transformer-architecture.md)
