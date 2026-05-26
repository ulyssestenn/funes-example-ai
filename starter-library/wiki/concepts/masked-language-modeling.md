---
title: Masked language modeling (MLM)
type: concept
tags: [pretraining, bert, objective]
created: 2026-05-26
updated: 2026-05-26
---
# Masked language modeling (MLM)
A self-supervised pre-training objective in which a random subset of input tokens is masked and the model must predict them from the surrounding context on **both** sides. This bidirectionality is what lets [BERT](../sources/bert.md) pre-train deep representations that condition on left and right context in every layer — unlike left-to-right language modeling. BERT masks 15% of tokens, replacing the chosen ones with `[MASK]` 80% of the time, a random token 10%, and leaving them unchanged 10%, to reduce the mismatch between pre-training and fine-tuning (where `[MASK]` never appears).

BERT pairs MLM with a secondary next-sentence-prediction (NSP) objective for sentence-pair tasks; later work found NSP largely unnecessary. The related text-corruption objective in [T5](./text-to-text-framework.md) masks contiguous spans instead of individual tokens.

## Related
- [Transfer learning (pre-train then fine-tune)](./transfer-learning.md)
- [Transformer](./transformer.md)
- [Text-to-text framework](./text-to-text-framework.md)
## Sources
- [BERT](../sources/bert.md)
## Topics
- [Pre-training and transfer learning](../topics/pretraining-and-transfer-learning.md)
