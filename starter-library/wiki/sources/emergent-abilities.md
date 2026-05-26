---
title: Emergent Abilities of Large Language Models
type: source
tags: [scaling, emergence, capabilities]
created: 2026-05-26
updated: 2026-05-26
---
# Emergent Abilities of Large Language Models
- **Raw file:** [EmergentAbilities.pdf](../../raw/EmergentAbilities.pdf)
- **Original:** Wei, Tay, Bommasani, Zoph, Fedus et al., TMLR 2022 ([arXiv:2206.07682](https://arxiv.org/abs/2206.07682))

## Summary
Defines an **emergent ability** as one absent in smaller models but present in larger ones, so it cannot be predicted by extrapolating small-model scaling curves. Plotting performance against training FLOPs, the authors show many tasks where accuracy stays near-random until a critical scale, then jumps sharply — a phase transition. They survey emergence in few-shot prompting and in augmented prompting strategies, and frame emergence (including emergent risks) as an open research direction.

## Key takeaways
- Emergence: "an ability not present in smaller models but present in larger ones"; a qualitative change from quantitative scaling.
- Emergent curves are flat/near-random until a critical scale, then rise sharply — unpredictable from extrapolation.
- Eight emergent few-shot tasks across five model families (e.g. 3-digit arithmetic emerges ~2·10²² FLOPs / 13B params).
- MMLU: models below ~10²² FLOPs (~10B params) are at chance.
- Augmented prompting strategies (chain-of-thought, instruction following) themselves only help past scale thresholds.
- The emergence threshold is not fixed — better data/training can shift it.

## Concepts extracted
- [Emergent abilities](../concepts/emergent-abilities.md)
- [In-context learning](../concepts/in-context-learning.md)
- [Chain-of-thought prompting](../concepts/chain-of-thought.md)
