---
title: Transfer learning (pre-train then fine-tune)
type: concept
tags: [pretraining, transfer-learning]
created: 2026-05-26
updated: 2026-05-26
---
# Transfer learning (pre-train then fine-tune)
The dominant NLP paradigm: first **pre-train** a model on a large, data-rich self-supervised task (e.g. [masked language modeling](./masked-language-modeling.md) or next-token prediction) to build general-purpose linguistic knowledge, then **fine-tune** the same weights on a smaller labeled downstream task. [BERT](../sources/bert.md) showed a single pre-trained encoder fine-tuned with one added output layer reaches SOTA across many tasks without task-specific architectures; [T5](../sources/t5-transfer-learning.md) systematized the recipe and found model scale to be the most important ingredient.

Fine-tuning on human-written demonstrations ([supervised fine-tuning](./supervised-fine-tuning.md)) and prompting-based adaptation ([in-context learning](./in-context-learning.md)) are alternatives to gradient-based downstream training.

## Related
- [Masked language modeling](./masked-language-modeling.md)
- [Text-to-text framework](./text-to-text-framework.md)
- [Supervised fine-tuning](./supervised-fine-tuning.md)
- [In-context learning](./in-context-learning.md)
## Sources
- [BERT](../sources/bert.md)
- [T5](../sources/t5-transfer-learning.md)
## Topics
- [Pre-training and transfer learning](../topics/pretraining-and-transfer-learning.md)
