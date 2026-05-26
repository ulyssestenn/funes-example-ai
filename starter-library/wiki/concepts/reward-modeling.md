---
title: Reward modeling
type: concept
tags: [alignment, rlhf, preference-learning]
created: 2026-05-26
updated: 2026-05-26
---
# Reward modeling
Training a model to predict a scalar reward reflecting human preference, by fitting it to **pairwise comparisons** of outputs (usually via the Bradley-Terry model — see [preference learning](./preference-learning.md)). In [RLHF](./rlhf.md), this learned reward model then stands in for a human, providing the reward signal that [PPO](./ppo.md) optimizes the policy against — making preference data reusable across many RL updates.

The reward model is a key cost and failure point: it can be **reward-hacked** by the policy, and training it is part of what [DPO](./direct-preference-optimization.md) eliminates by showing the policy itself implicitly defines a reward. [Constitutional AI](./constitutional-ai.md) builds a preference/reward model from AI-generated labels for harmlessness.

## Related
- [RLHF (reinforcement learning from human feedback)](./rlhf.md)
- [Preference learning](./preference-learning.md)
- [PPO (proximal policy optimization)](./ppo.md)
- [Direct preference optimization (DPO)](./direct-preference-optimization.md)
## Sources
- [InstructGPT](../sources/instructgpt.md)
- [Direct Preference Optimization](../sources/direct-preference-optimization.md)
## Topics
- [Alignment and preference learning](../topics/alignment-and-preference-learning.md)
