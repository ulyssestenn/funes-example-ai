---
title: Constitutional AI
type: concept
tags: [alignment, safety, rlaif]
created: 2026-05-26
updated: 2026-05-26
---
# Constitutional AI
A method for training a harmless assistant from a short list of natural-language principles (a **constitution**) and no human labels for harmfulness. It has two phases: a **supervised** phase where the model repeatedly critiques and revises its own harmful responses against a sampled principle, then fine-tunes on the revisions (SL-CAI); and a **reinforcement** phase where an AI model generates harmlessness preference labels used to train a preference model and optimize the policy — [RLAIF](./rlaif.md).

Replacing human harm labels with a small written constitution scales oversight: human input shrinks to ~10–16 principles plus a few examples. The result is a **non-evasive** assistant that engages with harmful queries by explaining its objections rather than deflecting, easing the [helpfulness-vs-harmlessness](./helpful-honest-harmless.md) tension. [Chain-of-thought](./chain-of-thought.md) reasoning in the critiques and AI evaluations improves harm identification.

## Related
- [RLAIF (RL from AI feedback)](./rlaif.md)
- [RLHF (reinforcement learning from human feedback)](./rlhf.md)
- [Preference learning](./preference-learning.md)
- [Helpful, honest, harmless (HHH)](./helpful-honest-harmless.md)
- [Chain-of-thought prompting](./chain-of-thought.md)
## Sources
- [Constitutional AI](../sources/constitutional-ai.md)
## Topics
- [Alignment and preference learning](../topics/alignment-and-preference-learning.md)
