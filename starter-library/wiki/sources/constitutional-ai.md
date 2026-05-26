---
title: "Constitutional AI: Harmlessness from AI Feedback"
type: source
tags: [alignment, rlaif, safety]
created: 2026-05-26
updated: 2026-05-26
---
# Constitutional AI: Harmlessness from AI Feedback
- **Raw file:** [ConstitutionalAlignment.pdf](../../raw/ConstitutionalAlignment.pdf)
- **Original:** Bai, Kadavath, Kundu, Askell ... Kaplan (Anthropic), 2022 ([arXiv:2212.08073](https://arxiv.org/abs/2212.08073))

## Summary
**Constitutional AI (CAI)** trains a harmless assistant through self-improvement using only a short list of natural-language principles (a "constitution") and **no human labels for harmfulness**. A supervised stage has the model critique and revise its own harmful responses, then fine-tunes on the revisions; an RL stage uses an AI model to produce harmlessness preference labels — **RL from AI Feedback (RLAIF)**. The result is a harmless but non-evasive assistant that explains its objections.

## Key takeaways
- Two phases: (SL) Critique → Revision → fine-tune on revisions (SL-CAI); (RL) AI preference labels → preference model → RL (RL-CAI / RLAIF).
- Eliminates human harmfulness labels; human oversight reduces to ~10–16 written principles plus a few prompt examples.
- Produces a **non-evasive** assistant that engages with harmful queries by explaining objections.
- Chain-of-thought reasoning in critiques/evaluations significantly improves harm identification at larger scale (>52B).
- Helpfulness labels remain human-provided; only harmlessness labels are AI-generated (a hybrid preference model).
- RL-CAI achieves a Pareto improvement on the harmlessness/helpfulness frontier over standard RLHF.

## Concepts extracted
- [Constitutional AI](../concepts/constitutional-ai.md)
- [RLAIF (RL from AI feedback)](../concepts/rlaif.md)
- [Preference learning](../concepts/preference-learning.md)
- [Helpful, honest, harmless (HHH)](../concepts/helpful-honest-harmless.md)
- [Chain-of-thought prompting](../concepts/chain-of-thought.md)
