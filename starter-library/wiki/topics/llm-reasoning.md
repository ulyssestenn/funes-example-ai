---
title: LLM reasoning
type: topic
tags: [reasoning, prompting, reinforcement-learning]
created: 2026-05-26
updated: 2026-05-26
---
# LLM reasoning
How large language models perform multi-step reasoning, and the two complementary ways to elicit it: prompting at inference time, and training with reinforcement learning. This topic also covers the algorithms and runtime ideas behind reasoning models.

## Concepts
- [LLM reasoning](../concepts/llm-reasoning.md) — the multi-step problem-solving capability itself.
- [Chain-of-thought prompting](../concepts/chain-of-thought.md) — eliciting step-by-step reasoning via exemplars.
- [Reinforcement learning for reasoning](../concepts/rl-for-reasoning.md) — training reasoning with correctness rewards (DeepSeek-R1).
- [GRPO (Group Relative Policy Optimization)](../concepts/grpo.md) — the critic-free RL algorithm behind R1.
- [Reasoning distillation](../concepts/reasoning-distillation.md) — copying a reasoning model into smaller ones.
- [Test-time compute](../concepts/test-time-compute.md) — spending more inference computation on harder problems.

## Related topics
- [Scaling and emergence](./scaling-and-emergence.md)
- [Alignment and preference learning](./alignment-and-preference-learning.md)
