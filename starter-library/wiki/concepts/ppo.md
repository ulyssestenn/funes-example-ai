---
title: PPO (proximal policy optimization)
type: concept
tags: [reinforcement-learning, rlhf]
created: 2026-05-26
updated: 2026-05-26
---
# PPO (proximal policy optimization)
A policy-gradient reinforcement-learning algorithm that improves a policy while constraining each update to stay close to the previous one (via a clipped objective), trading some optimality for stability. It is the RL optimizer in the standard [RLHF](./rlhf.md) pipeline: the language-model policy generates outputs, the [reward model](./reward-modeling.md) scores them, and PPO updates the policy to raise expected reward, with a KL penalty toward the supervised model to prevent drift.

PPO requires a separate value/critic network and online sampling, which makes RLHF complex and sometimes unstable — motivating both RL-free alternatives like [DPO](./direct-preference-optimization.md) and critic-free variants like [GRPO](./grpo.md), which estimates advantages from groups of sampled outputs instead.

## Related
- [RLHF (reinforcement learning from human feedback)](./rlhf.md)
- [Reward modeling](./reward-modeling.md)
- [GRPO (Group Relative Policy Optimization)](./grpo.md)
- [Reinforcement learning for reasoning](./rl-for-reasoning.md)
## Sources
- [InstructGPT](../sources/instructgpt.md)
- [DeepSeek-R1](../sources/deepseek-r1.md)
## Topics
- [Alignment and preference learning](../topics/alignment-and-preference-learning.md)
