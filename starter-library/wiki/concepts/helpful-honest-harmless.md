---
title: Helpful, honest, harmless (HHH)
type: concept
tags: [alignment, safety, goals]
created: 2026-05-26
updated: 2026-05-26
---
# Helpful, honest, harmless (HHH)
The three criteria commonly used to define aligned assistant behavior: be **helpful** (act on the user's explicit and implicit intent), **honest** (truthful, calibrated, non-deceptive), and **harmless** (avoid toxic, dangerous, or unethical outputs). They give RLHF-style training concrete targets and reveal real tensions — most notably helpfulness vs harmlessness, where a model trained only to avoid harm becomes uselessly evasive.

[InstructGPT](../sources/instructgpt.md) optimizes toward HHH via [RLHF](./rlhf.md) and measures truthfulness and toxicity directly; [Constitutional AI](./constitutional-ai.md) targets a **non-evasive** form of harmlessness so the assistant explains objections instead of deflecting.

## Related
- [RLHF (reinforcement learning from human feedback)](./rlhf.md)
- [Constitutional AI](./constitutional-ai.md)
## Sources
- [InstructGPT](../sources/instructgpt.md)
- [Constitutional AI](../sources/constitutional-ai.md)
## Topics
- [Alignment and preference learning](../topics/alignment-and-preference-learning.md)
