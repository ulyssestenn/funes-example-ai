---
title: Test-time compute
type: concept
tags: [reasoning, inference]
created: 2026-05-26
updated: 2026-05-26
---
# Test-time compute
The idea that a model can spend **more computation at inference time** — by generating longer reasoning before answering — to solve harder problems, separate from the compute spent during training. [Chain-of-thought prompting](./chain-of-thought.md) is an early form: longer reasoning chains let the model allocate more steps to harder questions. [DeepSeek-R1](../sources/deepseek-r1.md) makes this explicit, with RL-trained models autonomously growing their response length and accuracy improving as they "think" longer (e.g. AIME via self-consistency over many samples).

It reframes capability as partly a runtime budget rather than a fixed property of the weights, complementing training-time [scaling laws](./scaling-laws.md).

## Related
- [Chain-of-thought prompting](./chain-of-thought.md)
- [Reinforcement learning for reasoning](./rl-for-reasoning.md)
- [LLM reasoning](./llm-reasoning.md)
## Sources
- [Chain-of-Thought Prompting](../sources/chain-of-thought-prompting.md)
- [DeepSeek-R1](../sources/deepseek-r1.md)
## Topics
- [LLM reasoning](../topics/llm-reasoning.md)
