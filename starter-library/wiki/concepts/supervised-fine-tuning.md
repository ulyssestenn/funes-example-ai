---
title: Supervised fine-tuning (SFT)
type: concept
tags: [alignment, fine-tuning]
created: 2026-05-26
updated: 2026-05-26
---
# Supervised fine-tuning (SFT)
Fine-tuning a pretrained language model on curated input–output **demonstrations** of the desired behavior, using the ordinary next-token loss. In the [RLHF](./rlhf.md) pipeline SFT is the first step: it produces the initial aligned policy (and the reference point the later RL stage stays close to) by training on labeler-written demonstrations of good responses.

SFT is also used to bootstrap reasoning: DeepSeek-R1's **cold-start** stage fine-tunes on a small set of human-aligned long chain-of-thought examples before RL, and [reasoning distillation](./reasoning-distillation.md) is SFT on a stronger model's generated traces. It is a form of [transfer learning](./transfer-learning.md) specialized to demonstration data.

## Related
- [RLHF (reinforcement learning from human feedback)](./rlhf.md)
- [Transfer learning (pre-train then fine-tune)](./transfer-learning.md)
- [Constitutional AI](./constitutional-ai.md)
- [Reasoning distillation](./reasoning-distillation.md)
## Sources
- [InstructGPT](../sources/instructgpt.md)
- [DeepSeek-R1](../sources/deepseek-r1.md)
## Topics
- [Alignment and preference learning](../topics/alignment-and-preference-learning.md)
- [Pre-training and transfer learning](../topics/pretraining-and-transfer-learning.md)
