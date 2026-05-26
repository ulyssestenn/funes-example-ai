---
title: Reasoning distillation
type: concept
tags: [reasoning, distillation]
created: 2026-05-26
updated: 2026-05-26
---
# Reasoning distillation
Transferring a strong reasoning model's capability into smaller models by [supervised fine-tuning](./supervised-fine-tuning.md) them on reasoning traces the large model generates. [DeepSeek-R1](../sources/deepseek-r1.md) distilled ~800k of its samples into smaller Qwen and Llama models, which then **surpassed their original instruction-tuned counterparts** on reasoning benchmarks — and outperformed applying RL directly to the small models, indicating the large model's discovered reasoning patterns are easier to copy than to rediscover at small scale.

This makes expensive [RL-trained reasoning](./rl-for-reasoning.md) cheap to deploy, and is a reasoning-specific instance of model distillation.

## Related
- [Reinforcement learning for reasoning](./rl-for-reasoning.md)
- [Supervised fine-tuning](./supervised-fine-tuning.md)
- [LLM reasoning](./llm-reasoning.md)
## Sources
- [DeepSeek-R1](../sources/deepseek-r1.md)
## Topics
- [LLM reasoning](../topics/llm-reasoning.md)
