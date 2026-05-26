---
title: Chain-of-Thought Prompting Elicits Reasoning in Large Language Models
type: source
tags: [reasoning, prompting, emergence]
created: 2026-05-26
updated: 2026-05-26
---
# Chain-of-Thought Prompting Elicits Reasoning in Large Language Models
- **Raw file:** [ChainOfThought.pdf](../../raw/ChainOfThought.pdf)
- **Original:** Wei, Wang, Schuurmans, Bosma, Ichter, Xia, Chi, Le, Zhou (Google Research), 2022 ([arXiv:2201.11903](https://arxiv.org/abs/2201.11903))

## Summary
Shows that prompting an LLM with a few exemplars that include a **chain of thought** — intermediate natural-language reasoning steps leading to the answer — substantially improves performance on complex reasoning tasks, with no finetuning or rationale datasets. On GSM8K, PaLM 540B with just eight CoT exemplars reaches state of the art, beating a finetuned GPT-3 with a verifier.

## Key takeaways
- Works purely through prompting — no finetuning or task-specific data; one checkpoint serves many tasks.
- An **emergent ability of scale**: gains appear only around ~100B+ parameters; smaller models produce fluent but illogical chains.
- Gains span arithmetic, commonsense, and symbolic reasoning, largest for the biggest model (PaLM 540B).
- New SOTA on GSM8K; beats prior best on StrategyQA (75.6% vs 69.4%).
- Allocates more computation to harder problems and exposes an interpretable reasoning trace.
- Error analysis: most correct answers had logically valid chains; ~46% of wrong-answer chains were "almost correct."

## Concepts extracted
- [Chain-of-thought prompting](../concepts/chain-of-thought.md)
- [LLM reasoning](../concepts/llm-reasoning.md)
- [In-context learning](../concepts/in-context-learning.md)
- [Emergent abilities](../concepts/emergent-abilities.md)
- [Test-time compute](../concepts/test-time-compute.md)
