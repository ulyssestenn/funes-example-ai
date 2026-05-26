---
title: Emergent abilities
type: concept
tags: [scaling, emergence, capabilities]
created: 2026-05-26
updated: 2026-05-26
---
# Emergent abilities
An ability is **emergent** if it is absent in smaller models but present in larger ones, so it cannot be predicted by extrapolating the performance of smaller models. Plotted against training compute, an emergent task's accuracy stays near random until a **critical scale threshold**, then rises sharply — a phase transition rather than a smooth curve. This is why smooth [scaling laws](./scaling-laws.md) for loss do not forecast when specific capabilities appear.

Examples include multi-step arithmetic, multitask understanding (MMLU near chance below ~10²² FLOPs), and the usefulness of augmented prompting strategies like [chain-of-thought](./chain-of-thought.md) and [in-context learning](./in-context-learning.md). The threshold is not fixed — better data or training can shift it — and emergence may also produce unforeseen **risks**.

## Related
- [Scaling laws](./scaling-laws.md)
- [Compute-optimal training](./compute-optimal-training.md)
- [In-context learning](./in-context-learning.md)
- [Chain-of-thought prompting](./chain-of-thought.md)
## Sources
- [Emergent Abilities of Large Language Models](../sources/emergent-abilities.md)
- [GPT-3](../sources/gpt-3-few-shot-learners.md)
- [Chain-of-Thought Prompting](../sources/chain-of-thought-prompting.md)
## Topics
- [Scaling and emergence](../topics/scaling-and-emergence.md)
