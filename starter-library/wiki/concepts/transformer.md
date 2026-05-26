---
title: Transformer
type: concept
tags: [transformer, architecture]
created: 2026-05-26
updated: 2026-05-26
---
# Transformer
A sequence-transduction architecture built entirely on [attention](./self-attention.md), with no recurrence or convolution. The original design is an **encoder–decoder**: the encoder maps an input sequence to continuous representations, and an autoregressive decoder generates the output one token at a time. Each is a stack of identical layers (N=6 originally), and every layer wraps its sublayers — [multi-head attention](./multi-head-attention.md) and a position-wise feed-forward network — in a residual connection followed by layer normalization, i.e. `LayerNorm(x + Sublayer(x))`. Order information enters via [positional encoding](./positional-encoding.md).

Three architectural families descend from it: **encoder-only** ([BERT](../sources/bert.md)), **decoder-only** ([GPT-3](../sources/gpt-3-few-shot-learners.md)), and full **encoder–decoder** ([T5](../sources/t5-transfer-learning.md)). It is the substrate for essentially all modern LLMs.

## Related
- [Self-attention](./self-attention.md)
- [Multi-head attention](./multi-head-attention.md)
- [Positional encoding](./positional-encoding.md)
- [Masked language modeling](./masked-language-modeling.md)
- [Text-to-text framework](./text-to-text-framework.md)
## Sources
- [Attention Is All You Need](../sources/attention-is-all-you-need.md)
- [BERT](../sources/bert.md)
- [T5](../sources/t5-transfer-learning.md)
- [GPT-3](../sources/gpt-3-few-shot-learners.md)
## Topics
- [Transformer architecture](../topics/transformer-architecture.md)
