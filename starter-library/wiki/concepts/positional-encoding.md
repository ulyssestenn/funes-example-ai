---
title: Positional encoding
type: concept
tags: [transformer, architecture]
created: 2026-05-26
updated: 2026-05-26
---
# Positional encoding
[Self-attention](./self-attention.md) is permutation-invariant — on its own it has no notion of token order. Positional encodings inject order by adding position-dependent signals to the input embeddings. The original Transformer uses fixed **sinusoidal** functions of varying frequency, chosen so the model can attend by relative offsets and extrapolate to longer sequences; learned positional embeddings perform comparably.

Later models vary this: BERT uses learned absolute position embeddings, while T5 uses shared **relative** position biases added to attention logits.

## Related
- [Self-attention](./self-attention.md)
- [Transformer](./transformer.md)
## Sources
- [Attention Is All You Need](../sources/attention-is-all-you-need.md)
## Topics
- [Transformer architecture](../topics/transformer-architecture.md)
