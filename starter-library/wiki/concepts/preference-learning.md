---
title: Preference learning
type: concept
tags: [alignment, preferences]
created: 2026-05-26
updated: 2026-05-26
---
# Preference learning
Learning desired behavior from **comparisons** ("output A is better than output B") rather than absolute labels or demonstrations. Pairwise preferences are typically modeled with the **Bradley-Terry** model, where the probability that one response is preferred is the logistic of the difference in an underlying scalar score: `p(y₁ ≻ y₂) = σ(r(y₁) − r(y₂))`. Preferences are cheaper and often more reliable for annotators than writing ideal outputs.

This is the shared foundation beneath the alignment papers: [RLHF](./rlhf.md) and [Constitutional AI](./constitutional-ai.md) fit a [reward/preference model](./reward-modeling.md) to comparisons and optimize it with RL; [DPO](./direct-preference-optimization.md) optimizes the same Bradley-Terry objective directly on the policy without a separate model.

## Related
- [RLHF (reinforcement learning from human feedback)](./rlhf.md)
- [Reward modeling](./reward-modeling.md)
- [Direct preference optimization (DPO)](./direct-preference-optimization.md)
- [RLAIF (RL from AI feedback)](./rlaif.md)
## Sources
- [InstructGPT](../sources/instructgpt.md)
- [Direct Preference Optimization](../sources/direct-preference-optimization.md)
- [Constitutional AI](../sources/constitutional-ai.md)
## Topics
- [Alignment and preference learning](../topics/alignment-and-preference-learning.md)
