---
title: "Coverage Gap Analysis: what to ingest next"
type: analysis
tags: [meta, coverage, gaps, roadmap]
created: 2026-05-26
updated: 2026-05-26
---
# Coverage Gap Analysis: what to ingest next

What's missing from this library, given its stated scope — *foundational
large-language-model research papers (2017–2025): the Transformer and its
descendants, scaling and emergence, alignment, and reasoning*. This consolidates
the gaps already surfaced by the [health check](../meta/health/2026-05-26-health-check.md)
and the prior analyses ([scaling narrative](./2026-05-26-scaling-narrative.md),
[alignment matrix](./2026-05-26-alignment-comparison-matrix.md)) and prioritizes
them.

Two kinds of gap, kept separate:
- **In-scope gaps** — missing pieces of stories the library already tells. These
  are the priority.
- **Scope-expansion threads** — adjacent areas the library deliberately doesn't
  cover yet; ingesting them is a *scope decision* for the owner, not an omission.

## In-scope gaps (prioritized)

### P0 — directly strengthen an existing story, small lift

| Gap | Why it matters | Candidate source(s) |
|---|---|---|
| **The emergence critique** | The wiki states emergence as a phase transition ([emergent-abilities](../wiki/concepts/emergent-abilities.md)); the major counterargument is absent. Flagged in the scaling narrative. | Schaeffer et al., "Are Emergent Abilities of LLMs a Mirage?" (2023) |
| **RLHF precursors** | [RLHF](../wiki/concepts/rlhf.md) is presented starting at InstructGPT, but the technique predates it; the lineage is missing. | Christiano et al., "Deep RL from Human Preferences" (2017); Stiennon et al., "Learning to Summarize from Human Feedback" (2020) |
| **Inference-optimal scaling** | [compute-optimal-training](../wiki/concepts/compute-optimal-training.md) gives the *training*-optimal rule; deployment often over-trains smaller models. Flagged in the scaling narrative. | Touvron et al., "LLaMA" (2023) |
| **Self-consistency** | [test-time-compute](../wiki/concepts/test-time-compute.md) cites self-consistency by name but has no source for it. | Wang et al., "Self-Consistency Improves Chain-of-Thought Reasoning" (2022) |

### P1 — fill a recognized structural hole

| Gap | Why it matters | Candidate source(s) |
|---|---|---|
| **Tokenization** | Referenced (WordPiece in [BERT](../wiki/sources/bert.md)) but no concept; it's a true foundation. | Sennrich et al., "Neural MT of Rare Words with Subword Units" (BPE, 2016); SentencePiece (Kudo & Richardson, 2018) |
| **Decoder-only pretraining origin** | The library jumps to [GPT-3](../wiki/sources/gpt-3-few-shot-learners.md); the autoregressive-LM-as-multitask-learner idea originates earlier. | Radford et al., "Language Models are Unsupervised Multitask Learners" (GPT-2, 2019) |
| **Modern positional encoding** | [positional-encoding](../wiki/concepts/positional-encoding.md) covers sinusoidal/learned/relative but not the now-standard rotary embeddings. | Su et al., "RoFormer / RoPE" (2021) |
| **Reward over-optimization** | [reward-modeling](../wiki/concepts/reward-modeling.md) mentions reward hacking; no source quantifies it. Flagged in the alignment matrix. | Gao et al., "Scaling Laws for Reward Model Overoptimization" (2023) |
| **Sparse scaling (MoE)** | [scaling-laws](../wiki/concepts/scaling-laws.md)/Chinchilla assume dense models; mixture-of-experts is the major alternative scaling axis. | Fedus et al., "Switch Transformer" (2021); Shazeer et al., "Outrageously Large Neural Networks" (2017) |

### P2 — rounds out a cluster

- **Data quality/curation** (the post-Chinchilla bottleneck): The Pile, RefinedWeb,
  or data-constrained scaling (Muennighoff et al., 2023).
- **DPO follow-ups**: KTO (Ethayarajh et al., 2024), IPO (Azar et al., 2023),
  online/iterated DPO — flagged in the alignment matrix.
- **Process supervision / verifiers**: Lightman et al., "Let's Verify Step by
  Step" (2023) — connects [rl-for-reasoning](../wiki/concepts/rl-for-reasoning.md)
  to step-level rewards.
- **Efficient attention / long context**: Dao et al., "FlashAttention" (2022).
- **RoBERTa** (Liu et al., 2019) — would substantiate the wiki's claim that
  [NSP](../wiki/concepts/masked-language-modeling.md) is "largely unnecessary."

## Scope-expansion threads (decide explicitly)

These are coherent, important areas the library currently has **zero** coverage
of. Each is a "should this library grow to include X?" decision:

- **Retrieval-augmented generation (RAG)** — Lewis et al. (2020). Major paradigm,
  entirely absent.
- **Tool use / agents** — Toolformer (Schick et al., 2023), ReAct (Yao et al.,
  2022); the natural successor to the reasoning cluster.
- **Multimodality** — CLIP (Radford et al., 2021), Flamingo (Alayrac et al.,
  2022). The library is text-only.
- **Code models** — Codex (Chen et al., 2021).
- **Evaluation & benchmarks** — MMLU (Hendrycks et al., 2020), HELM (Liang et al.,
  2022). The wiki *cites* benchmark scores (GLUE, MMLU, GSM8K) but has no source on
  evaluation methodology.

## Internal gaps (no new sources needed)

These are improvements to existing material, not ingest targets:

- **Promote folded concepts** (from the health check): next-sentence prediction,
  span-corruption, Bradley-Terry, C4, alignment tax, cold-start data.
- **Add the proposed concept** "train-time vs. test-time scaling" from the scaling
  narrative — it currently lives only in an output, not the wiki.
- **No `tokenization` concept** even before a new source — could be written from
  the existing BERT/T5 material.

## Recommendation: the next 3–5 ingests

If the goal is maximum coverage-per-paper *within current scope*:

1. **Schaeffer et al. (emergence mirage)** — closes the most conspicuous one-sided
   claim in the wiki.
2. **Christiano (2017) + Stiennon (2020)** — give RLHF its real lineage (count as
   one ingest of two short papers).
3. **LLaMA (2023)** — adds the inference-optimal counterpoint to Chinchilla and a
   canonical open model.
4. **GPT-2 (2019)** — completes the decoder-only pretraining origin story.
5. **Self-consistency (2022)** — cheap, and removes a dangling reference.

If instead the goal is to *broaden* the library, the highest-impact scope
expansion is **RAG** or **tool use/agents**, each of which would justify a new
topic map.

## Filing back

- This report is itself the roadmap; no wiki changes are implied until sources are
  ingested.
- Suggest revisiting the [concept-centrality map](./2026-05-26-concept-centrality-map.md)
  after the next ingest batch, since new sources will shift the hubs and the
  "start here" path.
