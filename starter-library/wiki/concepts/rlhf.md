---
title: RLHF (reinforcement learning from human feedback)
type: concept
tags: [alignment, rlhf]
created: 2026-05-26
updated: 2026-05-26
---
# RLHF (reinforcement learning from human feedback)
A pipeline for aligning a language model with human intent using human preference judgments as the reward signal. As formalized by [InstructGPT](../sources/instructgpt.md), it has three steps: (1) [supervised fine-tuning](./supervised-fine-tuning.md) on human-written demonstrations; (2) train a [reward model](./reward-modeling.md) on human rankings of model outputs; (3) optimize the policy against that reward with [PPO](./ppo.md), regularized by a KL penalty toward the SFT model. Steps 2–3 can iterate.

RLHF made a 1.3B model's outputs preferred over the 100× larger GPT-3, improving truthfulness and reducing toxicity. It can incur an **alignment tax** (regressions on some capabilities), partly mitigated by mixing in pretraining gradients. Variants replace pieces of the pipeline: [Constitutional AI / RLAIF](./rlaif.md) swaps human labels for AI labels, and [DPO](./direct-preference-optimization.md) removes the reward model and RL loop entirely.

## Related
- [Reward modeling](./reward-modeling.md)
- [PPO (proximal policy optimization)](./ppo.md)
- [Supervised fine-tuning](./supervised-fine-tuning.md)
- [Preference learning](./preference-learning.md)
- [Direct preference optimization (DPO)](./direct-preference-optimization.md)
- [RLAIF (RL from AI feedback)](./rlaif.md)
- [Helpful, honest, harmless (HHH)](./helpful-honest-harmless.md)
## Sources
- [InstructGPT](../sources/instructgpt.md)
- [Direct Preference Optimization](../sources/direct-preference-optimization.md)
- [Constitutional AI](../sources/constitutional-ai.md)
## Topics
- [Alignment and preference learning](../topics/alignment-and-preference-learning.md)
