---
title: GRPO (Group Relative Policy Optimization)
type: concept
tags: [reinforcement-learning, reasoning]
created: 2026-05-26
updated: 2026-05-26
---
# GRPO (Group Relative Policy Optimization)
The reinforcement-learning algorithm used to train DeepSeek-R1. For each question it samples a **group** of candidate outputs, scores them, and computes each output's advantage as its reward **normalized within the group** (relative to the group mean and spread). This removes the need for the separate value/critic network that [PPO](./ppo.md) requires, cutting memory and complexity while keeping the clipped, KL-regularized policy update.

DeepSeek-R1 pairs GRPO with **rule-based rewards** — deterministic answer-checking and compiler tests — rather than a neural [reward model](./reward-modeling.md), which avoids reward hacking on reasoning tasks. It is the engine behind [reinforcement learning for reasoning](./rl-for-reasoning.md).

## Related
- [PPO (proximal policy optimization)](./ppo.md)
- [Reinforcement learning for reasoning](./rl-for-reasoning.md)
## Sources
- [DeepSeek-R1](../sources/deepseek-r1.md)
## Topics
- [LLM reasoning](../topics/llm-reasoning.md)
