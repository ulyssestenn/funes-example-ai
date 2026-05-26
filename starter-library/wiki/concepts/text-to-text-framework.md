---
title: Text-to-text framework
type: concept
tags: [t5, transfer-learning, unification]
created: 2026-05-26
updated: 2026-05-26
---
# Text-to-text framework
T5's unifying idea: cast **every** NLP problem — translation, summarization, classification, QA, even regression — as mapping an input string to an output string, using one model, one loss, and one decoding procedure. A natural-language **task prefix** (e.g. `translate English to German:`, `cola sentence:`) tells the single model which task to perform. Classification becomes generating a class label as text; similarity regression becomes emitting a number like `3.8` as a string.

This uniformity let [T5](../sources/t5-transfer-learning.md) systematically compare objectives, datasets, and architectures on equal footing, and pre-train with a **span-corruption** denoising objective on the C4 corpus. It contrasts with [BERT](./masked-language-modeling.md)'s encoder-plus-task-specific-head approach.

## Related
- [Transfer learning (pre-train then fine-tune)](./transfer-learning.md)
- [Transformer](./transformer.md)
- [Masked language modeling](./masked-language-modeling.md)
## Sources
- [T5](../sources/t5-transfer-learning.md)
## Topics
- [Pre-training and transfer learning](../topics/pretraining-and-transfer-learning.md)
