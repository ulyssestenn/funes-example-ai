---
title: "Direct Preference Optimization: Your Language Model is Secretly a Reward Model"
type: source
tags: [alignment, preference-learning, rl-free]
created: 2026-05-26
updated: 2026-05-26
---
# Direct Preference Optimization: Your Language Model is Secretly a Reward Model
- **Raw file:** [DirectPrefOptimization.pdf](../../raw/DirectPrefOptimization.pdf)
- **Original:** Rafailov, Sharma, Mitchell, Ermon, Manning, Finn (Stanford / CZ Biohub), NeurIPS 2023 ([arXiv:2305.18290](https://arxiv.org/abs/2305.18290))

## Summary
RLHF is complex and unstable — it fits a separate reward model, then optimizes the policy with RL (PPO). **DPO** reparameterizes the reward so the optimal policy is expressed in closed form, letting the same KL-constrained RLHF objective be solved with a simple binary cross-entropy loss directly on the policy — no explicit reward model, no RL loop, no sampling during training. DPO matches or beats PPO-based RLHF on sentiment control, summarization, and single-turn dialogue while being far simpler and more stable.

## Key takeaways
- Change of variables: the optimal KL-constrained policy is π_r(y|x) ∝ π_ref(y|x)·exp(r(x,y)/β), invertible to express reward via the policy.
- Substituting into the Bradley-Terry model cancels the intractable partition function, yielding a loss over policies alone.
- Objective: a binary cross-entropy loss raising the log-prob ratio of preferred over dispreferred responses (relative to π_ref).
- A dynamic per-example weight upweights examples where the implicit reward estimate is wrong, preventing degeneration.
- Optimizes the *same* objective as RLHF (KL-constrained reward maximization) but RL-free — the policy implicitly is its own reward model.
- Stable and lightweight; validated up to 6B parameters; generalizes to the Plackett-Luce ranking model.

## Concepts extracted
- [Direct preference optimization (DPO)](../concepts/direct-preference-optimization.md)
- [Preference learning](../concepts/preference-learning.md)
- [Reward modeling](../concepts/reward-modeling.md)
- [RLHF (reinforcement learning from human feedback)](../concepts/rlhf.md)
