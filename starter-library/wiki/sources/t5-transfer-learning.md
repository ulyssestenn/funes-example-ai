---
title: "Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer (T5)"
type: source
tags: [transfer-learning, text-to-text, pretraining, scaling]
created: 2026-05-26
updated: 2026-05-26
---
# Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer (T5)
- **Raw file:** [LimitsofTransferLearning.pdf](../../raw/LimitsofTransferLearning.pdf)
- **Original:** Raffel et al. (Google), JMLR 2020 ([arXiv:1910.10683](https://arxiv.org/abs/1910.10683))

## Summary
T5 recasts every NLP problem as a **text-to-text** task so one model, objective, and decoding procedure apply everywhere. The paper is a systematic empirical survey comparing pre-training objectives, architectures, datasets, and transfer strategies, then scales the best recipe (with the new C4 corpus, up to 11B parameters) to reach state of the art on many benchmarks.

## Key takeaways
- Unified text-to-text framing handles translation, summarization, classification, QA, and even regression (emitting e.g. "3.8").
- Introduces **C4** (Colossal Clean Crawled Corpus), hundreds of GB of heuristically cleaned Common Crawl English text.
- Largest model is 11B parameters; **model scale** was the single most important ingredient for the best results.
- SOTA on 18 of 24 tasks, including a GLUE average of 90.3.
- A **span-corruption** denoising objective (dropping contiguous spans) worked best among compared objectives.
- Architecture closely follows the original Transformer but uses shared relative position embeddings and moves layer norm outside the residual path.

## Concepts extracted
- [Text-to-text framework](../concepts/text-to-text-framework.md)
- [Transfer learning (pre-train then fine-tune)](../concepts/transfer-learning.md)
- [Transformer](../concepts/transformer.md)
