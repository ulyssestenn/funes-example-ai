# Raw Source Registry

Every source ingested into `raw/` is listed here. **Do not edit the content of
raw files** — they are the immutable record. See [`../AGENTS.md`](../AGENTS.md)
for the ingest protocol.

| ID | Title | Type | Added | Status | Description |
|----|-------|------|-------|--------|-------------|
| 001 | [Attention Is All You Need](./AttentionIsAllYouNeed.pdf) | paper | 2026-05-26 | raw | Vaswani et al., 2017 (arXiv:1706.03762). Introduces the Transformer, an attention-only sequence architecture; foundation of modern LLMs. |
| 002 | [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](./BERT.pdf) | paper | 2026-05-26 | raw | Devlin et al., 2018 (arXiv:1810.04805). Bidirectional masked-language-model pre-training, fine-tuned for NLP understanding tasks. |
| 003 | [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](./ChainOfThought.pdf) | paper | 2026-05-26 | raw | Wei et al., 2022 (arXiv:2201.11903). Prompting models to produce intermediate reasoning steps improves complex reasoning. |
| 004 | [Constitutional AI: Harmlessness from AI Feedback](./ConstitutionalAlignment.pdf) | paper | 2026-05-26 | raw | Bai et al., 2022 (arXiv:2212.08073). Trains a harmless assistant from AI feedback guided by a set of principles (RLAIF). |
| 005 | [DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](./DeepSeek-R1.pdf) | paper | 2026-05-26 | raw | DeepSeek-AI, 2025 (arXiv:2501.12948). Incentivizes LLM reasoning via pure RL, without supervised reasoning demonstrations. |
| 006 | [Direct Preference Optimization: Your Language Model is Secretly a Reward Model](./DirectPrefOptimization.pdf) | paper | 2026-05-26 | raw | Rafailov et al., 2023 (arXiv:2305.18290). Aligns LMs to preferences directly, without a separate reward model or RL loop. |
| 007 | [Emergent Abilities of Large Language Models](./EmergentAbilities.pdf) | paper | 2026-05-26 | raw | Wei et al., 2022 (arXiv:2206.07682). Documents capabilities that appear only above certain model scales. |
| 008 | [Language Models are Few-Shot Learners](./LanguageModelsAreFewShotLearners.pdf) | paper | 2026-05-26 | raw | Brown et al., 2020 (arXiv:2005.14165). GPT-3; in-context few-shot learning at 175B-parameter scale. |
| 009 | [Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer](./LimitsofTransferLearning.pdf) | paper | 2026-05-26 | raw | Raffel et al., 2019 (arXiv:1910.10683). T5; a unified text-to-text framework for NLP transfer learning. |
| 010 | [Scaling Laws for Neural Language Models](./ScalingLaws.pdf) | paper | 2026-05-26 | raw | Kaplan et al., 2020 (arXiv:2001.08361). Power-law relationships between loss, model size, dataset size, and compute. |
| 011 | [Training Compute-Optimal Large Language Models](./TrainingComputeOptimal.pdf) | paper | 2026-05-26 | raw | Hoffmann et al., 2022 (arXiv:2203.15556). Chinchilla; model size and training tokens should scale equally for a compute budget. |
| 012 | [Training Language Models to Follow Instructions with Human Feedback](./TrainingLangModelsFollowInstructtionsFeedback.pdf) | paper | 2026-05-26 | raw | Ouyang et al., 2022 (arXiv:2203.02155). InstructGPT; RLHF aligns models to follow user instructions. |

<!--
Row format:
| 001 | Attention Is All You Need | paper | 2026-01-10 | compiled | Original transformer paper. |
Status: raw (saved, not yet compiled) | compiled (digested into wiki).
-->
