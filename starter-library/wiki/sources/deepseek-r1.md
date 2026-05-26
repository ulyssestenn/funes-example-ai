---
title: "DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning"
type: source
tags: [reasoning, reinforcement-learning, distillation]
created: 2026-05-26
updated: 2026-05-26
---
# DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning
- **Raw file:** [DeepSeek-R1.pdf](../../raw/DeepSeek-R1.pdf)
- **Original:** DeepSeek-AI, 2025 ([arXiv:2501.12948](https://arxiv.org/abs/2501.12948))

## Summary
Shows that LLM reasoning can be incentivized through **pure reinforcement learning** with only correctness-based rewards, eliminating the need for human-annotated reasoning traces. **DeepSeek-R1-Zero** is trained by RL directly on a base model (no SFT) and spontaneously develops self-reflection, verification, and longer "thinking." **DeepSeek-R1** then adds cold-start data and a multi-stage pipeline to fix readability and align with human preferences, and the reasoning is distilled into smaller models.

## Key takeaways
- R1-Zero = pure RL, no SFT: trained directly on the base model with rule-based rewards (accuracy + format).
- **GRPO** replaces PPO: samples a group of outputs per question and uses group-normalized rewards, dropping the critic.
- Emergent reasoning: response length grows, self-verification/reflection appear, including an "aha moment." AIME pass@1 rose 15.6% → 77.9% (86.7% with self-consistency).
- R1 multi-stage pipeline: cold-start long-CoT SFT → reasoning RL → rejection-sampling SFT → final RL for helpfulness/harmlessness.
- Rule-based rewards (answer-checking, compilers) for reasoning; neural reward models avoided there to prevent reward hacking.
- Reasoning distilled (SFT on ~800k samples) into smaller Qwen/Llama models that surpass their instruction-tuned counterparts.

## Concepts extracted
- [Reinforcement learning for reasoning](../concepts/rl-for-reasoning.md)
- [GRPO (Group Relative Policy Optimization)](../concepts/grpo.md)
- [Reasoning distillation](../concepts/reasoning-distillation.md)
- [LLM reasoning](../concepts/llm-reasoning.md)
- [Test-time compute](../concepts/test-time-compute.md)
- [Chain-of-thought prompting](../concepts/chain-of-thought.md)
