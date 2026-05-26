---
title: Training Language Models to Follow Instructions with Human Feedback (InstructGPT)
type: source
tags: [alignment, rlhf, instruction-following]
created: 2026-05-26
updated: 2026-05-26
---
# Training Language Models to Follow Instructions with Human Feedback (InstructGPT)
- **Raw file:** [TrainingLangModelsFollowInstructtionsFeedback.pdf](../../raw/TrainingLangModelsFollowInstructtionsFeedback.pdf)
- **Original:** Ouyang, Wu, Jiang, Almeida et al. (OpenAI), 2022 ([arXiv:2203.02155](https://arxiv.org/abs/2203.02155))

## Summary
Scaling alone does not make language models follow user intent — they can be untruthful, toxic, or unhelpful. The authors fine-tune GPT-3 to align with intent using **RLHF** over a three-step pipeline (SFT → reward model → PPO), producing **InstructGPT**. Labelers prefer the 1.3B InstructGPT's outputs over the 175B GPT-3's, with gains in truthfulness and reduced toxicity and only minor regressions on public benchmarks.

## Key takeaways
- Three-step pipeline: (1) supervised fine-tuning on labeler demonstrations, (2) train a reward model on labeler rankings, (3) optimize the policy against the RM with PPO; steps 2–3 iterate.
- 1.3B InstructGPT outputs preferred over 175B GPT-3 (100× larger); 175B InstructGPT preferred ~85% over 175B GPT-3.
- Truthfulness roughly doubles on TruthfulQA; ~25% fewer toxic outputs when prompted to be respectful.
- "Alignment tax": RLHF regresses some benchmarks, mitigated by mixing pretraining gradients into PPO (PPO-ptx).
- Targets **helpful, honest, harmless** behavior; ~40 vetted contractors produced demonstrations and comparisons.
- Generalizes to held-out labelers and out-of-distribution instructions (code, other languages).

## Concepts extracted
- [RLHF (reinforcement learning from human feedback)](../concepts/rlhf.md)
- [Reward modeling](../concepts/reward-modeling.md)
- [PPO (proximal policy optimization)](../concepts/ppo.md)
- [Supervised fine-tuning](../concepts/supervised-fine-tuning.md)
- [Preference learning](../concepts/preference-learning.md)
- [Helpful, honest, harmless (HHH)](../concepts/helpful-honest-harmless.md)
