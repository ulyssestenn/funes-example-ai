---
title: Chain-of-thought prompting
type: concept
tags: [reasoning, prompting]
created: 2026-05-26
updated: 2026-05-26
---
# Chain-of-thought prompting
A prompting technique in which few-shot exemplars include a **chain of thought** — a series of intermediate natural-language reasoning steps leading to the answer — so the model generates its own step-by-step reasoning before answering. It substantially improves performance on arithmetic, commonsense, and symbolic [reasoning](./llm-reasoning.md) tasks, requires no finetuning, and produces an interpretable reasoning trace.

Chain-of-thought is itself an [emergent ability](./emergent-abilities.md): it only helps above ~100B parameters, where smaller models produce fluent but illogical chains. It extends [in-context learning](./in-context-learning.md) by demonstrating reasoning rather than just input→output, and is the conceptual precursor to training models to reason via RL ([reinforcement learning for reasoning](./rl-for-reasoning.md)), which removes the dependence on hand-written rationales.

## Related
- [LLM reasoning](./llm-reasoning.md)
- [In-context learning](./in-context-learning.md)
- [Emergent abilities](./emergent-abilities.md)
- [Reinforcement learning for reasoning](./rl-for-reasoning.md)
- [Test-time compute](./test-time-compute.md)
## Sources
- [Chain-of-Thought Prompting](../sources/chain-of-thought-prompting.md)
- [DeepSeek-R1](../sources/deepseek-r1.md)
- [Constitutional AI](../sources/constitutional-ai.md)
## Topics
- [LLM reasoning](../topics/llm-reasoning.md)
