---
title: Direct preference optimization (DPO)
type: concept
tags: [alignment, preference-learning, rl-free]
created: 2026-05-26
updated: 2026-05-26
---
# Direct preference optimization (DPO)
An RL-free method for aligning a model to [preferences](./preference-learning.md). DPO uses a change of variables — the optimal KL-constrained policy is `π(y|x) ∝ π_ref(y|x)·exp(r(x,y)/β)` — to express the reward in terms of the policy itself. Substituting this into the Bradley-Terry preference objective cancels the intractable partition function, leaving a simple **binary cross-entropy loss over policies**: raise the log-probability ratio (relative to the reference model) of preferred over dispreferred responses.

This optimizes the *same* objective as [RLHF](./rlhf.md) — KL-constrained reward maximization — but with no separate [reward model](./reward-modeling.md), no [PPO](./ppo.md) loop, and no sampling during training, hence the slogan "your language model is secretly a reward model." A dynamic per-example weight upweights examples where the implicit reward is most wrong, preventing degeneration. It is more stable and lightweight while matching or beating PPO-based RLHF.

## Related
- [RLHF (reinforcement learning from human feedback)](./rlhf.md)
- [Preference learning](./preference-learning.md)
- [Reward modeling](./reward-modeling.md)
- [PPO (proximal policy optimization)](./ppo.md)
## Sources
- [Direct Preference Optimization](../sources/direct-preference-optimization.md)
## Topics
- [Alignment and preference learning](../topics/alignment-and-preference-learning.md)
