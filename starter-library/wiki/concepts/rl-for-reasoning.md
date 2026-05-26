---
title: Reinforcement learning for reasoning
type: concept
tags: [reasoning, reinforcement-learning]
created: 2026-05-26
updated: 2026-05-26
---
# Reinforcement learning for reasoning
Training a model to [reason](./llm-reasoning.md) by rewarding **correct final answers** rather than imitating human-written reasoning traces. [DeepSeek-R1](../sources/deepseek-r1.md) showed that applying RL with simple [rule-based rewards](./grpo.md) (answer-checkers, code compilers) directly to a base model — R1-Zero, with no [supervised fine-tuning](./supervised-fine-tuning.md) — causes advanced reasoning to **emerge**: response length grows and the model develops self-verification, reflection, and alternative-strategy exploration (the "aha moment").

This removes [chain-of-thought](./chain-of-thought.md)'s dependence on hand-written rationales. Pure RL hurts readability and mixes languages, so the full R1 wraps it in a [multi-stage pipeline](./supervised-fine-tuning.md) (cold-start SFT → reasoning RL → rejection-sampling SFT → final alignment RL), using the critic-free [GRPO](./grpo.md) algorithm and reserving rule-based rewards to avoid reward hacking.

## Related
- [LLM reasoning](./llm-reasoning.md)
- [Chain-of-thought prompting](./chain-of-thought.md)
- [GRPO (Group Relative Policy Optimization)](./grpo.md)
- [PPO (proximal policy optimization)](./ppo.md)
- [Reasoning distillation](./reasoning-distillation.md)
- [Test-time compute](./test-time-compute.md)
## Sources
- [DeepSeek-R1](../sources/deepseek-r1.md)
## Topics
- [LLM reasoning](../topics/llm-reasoning.md)
