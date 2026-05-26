---
title: LLM reasoning
type: concept
tags: [reasoning, capabilities]
created: 2026-05-26
updated: 2026-05-26
---
# LLM reasoning
The capacity of large language models to solve multi-step problems — arithmetic, logic, commonsense, code, mathematical proof — by producing and following intermediate steps rather than answering in one shot. Reasoning quality improves both with **scale** (it behaves like an [emergent ability](./emergent-abilities.md)) and with methods that elicit explicit step-by-step computation.

Two complementary routes appear in this library: eliciting reasoning at inference via [chain-of-thought prompting](./chain-of-thought.md), and *training* models to reason via [reinforcement learning](./rl-for-reasoning.md) on correctness rewards, which yields emergent self-verification. Both benefit from spending more [test-time compute](./test-time-compute.md) on harder problems.

## Related
- [Chain-of-thought prompting](./chain-of-thought.md)
- [Reinforcement learning for reasoning](./rl-for-reasoning.md)
- [Emergent abilities](./emergent-abilities.md)
- [Test-time compute](./test-time-compute.md)
## Sources
- [Chain-of-Thought Prompting](../sources/chain-of-thought-prompting.md)
- [DeepSeek-R1](../sources/deepseek-r1.md)
## Topics
- [LLM reasoning](../topics/llm-reasoning.md)
