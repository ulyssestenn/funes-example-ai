---
title: In-context learning
type: concept
tags: [gpt, prompting, few-shot]
created: 2026-05-26
updated: 2026-05-26
---
# In-context learning
A large language model's ability to infer and perform a task purely from instructions and examples in its input context **at inference time, with no gradient updates**. [GPT-3](../sources/gpt-3-few-shot-learners.md) demonstrated this at 175B parameters across **zero-shot** (instruction only), **one-shot**, and **few-shot** (typically 10–100 demonstrations) settings. Larger models make increasingly efficient use of in-context information, and few-shot gains grow faster with scale than zero-shot — making in-context learning itself an [emergent ability](./emergent-abilities.md).

It offers an alternative to gradient-based [transfer learning](./transfer-learning.md): one frozen model serves many tasks via prompting. [Chain-of-thought prompting](./chain-of-thought.md) extends it by placing reasoning steps in the demonstrations.

## Related
- [Emergent abilities](./emergent-abilities.md)
- [Transfer learning (pre-train then fine-tune)](./transfer-learning.md)
- [Chain-of-thought prompting](./chain-of-thought.md)
- [Scaling laws](./scaling-laws.md)
## Sources
- [GPT-3](../sources/gpt-3-few-shot-learners.md)
- [Emergent Abilities of Large Language Models](../sources/emergent-abilities.md)
## Topics
- [Scaling and emergence](../topics/scaling-and-emergence.md)
