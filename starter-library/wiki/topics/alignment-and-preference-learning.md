---
title: Alignment and preference learning
type: topic
tags: [alignment, rlhf, safety, preferences]
created: 2026-05-26
updated: 2026-05-26
---
# Alignment and preference learning
How pretrained models are steered to follow human intent and behave safely. This topic covers the RLHF pipeline and its building blocks, the goals alignment optimizes for, and alternative recipes that replace human labels with AI feedback or remove the RL loop entirely.

## Concepts
- [RLHF (reinforcement learning from human feedback)](../concepts/rlhf.md) — the SFT → reward model → PPO pipeline (InstructGPT).
- [Supervised fine-tuning](../concepts/supervised-fine-tuning.md) — demonstration fine-tuning; the pipeline's first step.
- [Reward modeling](../concepts/reward-modeling.md) — fitting a scalar reward to human comparisons.
- [PPO (proximal policy optimization)](../concepts/ppo.md) — the RL optimizer used in RLHF.
- [Preference learning](../concepts/preference-learning.md) — learning from comparisons via the Bradley-Terry model.
- [Direct preference optimization (DPO)](../concepts/direct-preference-optimization.md) — RL-free preference optimization on the policy.
- [Constitutional AI](../concepts/constitutional-ai.md) — self-critique + AI feedback guided by written principles.
- [RLAIF (RL from AI feedback)](../concepts/rlaif.md) — AI-generated preference labels for scalable oversight.
- [Helpful, honest, harmless (HHH)](../concepts/helpful-honest-harmless.md) — the criteria defining aligned behavior.

## Related topics
- [Pre-training and transfer learning](./pretraining-and-transfer-learning.md)
- [LLM reasoning](./llm-reasoning.md)
