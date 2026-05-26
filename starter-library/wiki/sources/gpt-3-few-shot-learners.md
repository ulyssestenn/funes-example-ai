---
title: Language Models are Few-Shot Learners (GPT-3)
type: source
tags: [scaling, in-context-learning, gpt]
created: 2026-05-26
updated: 2026-05-26
---
# Language Models are Few-Shot Learners (GPT-3)
- **Raw file:** [LanguageModelsAreFewShotLearners.pdf](../../raw/LanguageModelsAreFewShotLearners.pdf)
- **Original:** Brown, Mann, Ryder, Subbiah, Kaplan ... Amodei (OpenAI), 2020 ([arXiv:2005.14165](https://arxiv.org/abs/2005.14165))

## Summary
Trains **GPT-3**, a 175B-parameter autoregressive Transformer (10× larger than any prior non-sparse LM), and shows that scale alone dramatically improves task-agnostic **few-shot** performance — specifying tasks purely through text, with no gradient updates. GPT-3 reaches competitiveness with fine-tuned SOTA on many benchmarks while still struggling on others, and can produce news articles humans struggle to distinguish from human-written ones.

## Key takeaways
- 175B parameters — 10× larger than any previous non-sparse model.
- Evaluated zero-shot, one-shot, and few-shot (10–100 in-context demonstrations), all without gradient updates.
- Larger models make increasingly efficient use of in-context information; few-shot gains grow faster with scale.
- Strong on translation, QA, cloze, Winograd, and synthetic tasks (3-digit arithmetic, word unscrambling).
- Humans struggle to distinguish GPT-3-generated news from real articles.
- Honest about limits: weak on some NLI/reading tasks; raises data-contamination and bias/misuse concerns.

## Concepts extracted
- [In-context learning](../concepts/in-context-learning.md)
- [Emergent abilities](../concepts/emergent-abilities.md)
- [Scaling laws](../concepts/scaling-laws.md)
- [Transformer](../concepts/transformer.md)
