---
title: "Concept-Centrality Map: a reader's start-here guide"
type: analysis
tags: [navigation, graph, meta, guide]
created: 2026-05-26
updated: 2026-05-26
---
# Concept-Centrality Map: a reader's start-here guide

Which articles are the **hubs** of this wiki, and in what order should a newcomer
read them? This maps the concept link graph by counting inbound links, then turns
the structure into a reading path.

## Method

For each of the 26 [concepts](../wiki/INDEX.md), measured from the actual files:
- **Cin** — inbound links from *other concept* articles (the concept-to-concept
  graph; a concept's "authority" among its peers).
- **Src** — how many of the 12 source notes cite it (breadth across papers — a
  recurring idea).
- **Topic** — how many topic maps list it (1, or 2 for cross-topic concepts).
- **TOT = Cin + Src + Topic** — overall inbound centrality.

Higher TOT = more of the wiki points at it = better starting point.

## The hubs (ranked by total inbound centrality)

| Rank | Concept | Cin | Src | Topic | TOT | Role |
|------|---------|----:|----:|------:|----:|------|
| 1 | [chain-of-thought](../wiki/concepts/chain-of-thought.md) | 7 | 4 | 1 | **12** | cross-topic bridge |
| 2 | [RLHF](../wiki/concepts/rlhf.md) | 8 | 2 | 1 | **11** | alignment cluster hub |
| 3 | [transformer](../wiki/concepts/transformer.md) | 5 | 4 | 1 | **10** | architectural root |
| 4 | [preference-learning](../wiki/concepts/preference-learning.md) | 5 | 3 | 1 | **9** | alignment substrate |
| 4 | [emergent-abilities](../wiki/concepts/emergent-abilities.md) | 5 | 3 | 1 | **9** | scaling↔reasoning bridge |
| 6 | [scaling-laws](../wiki/concepts/scaling-laws.md) | 4 | 3 | 1 | **8** | scaling root |
| 6 | [reward-modeling](../wiki/concepts/reward-modeling.md) | 5 | 2 | 1 | **8** | alignment cluster |
| 6 | [in-context-learning](../wiki/concepts/in-context-learning.md) | 4 | 3 | 1 | **8** | scaling↔reasoning bridge |
| 6 | [rl-for-reasoning](../wiki/concepts/rl-for-reasoning.md) | 6 | 1 | 1 | **8** | reasoning cluster hub |
| 10 | [supervised-fine-tuning](../wiki/concepts/supervised-fine-tuning.md) | 4 | 1 | **2** | **7** | pretraining↔alignment bridge |

(Full ordering tapers down to specialist leaves at TOT 4: `grpo`,
`multi-head-attention`, `positional-encoding`, `reasoning-distillation`.)

## Three kinds of hub

**1. Roots — where ideas originate.** High source-breadth (Src), cited across many
papers:
- [transformer](../wiki/concepts/transformer.md) (Src 4) — the architectural
  substrate every later model inherits; start the whole wiki here.
- [scaling-laws](../wiki/concepts/scaling-laws.md) (Src 3) — the root of the
  scaling story.
- [chain-of-thought](../wiki/concepts/chain-of-thought.md) (Src 4) — referenced by
  the reasoning, emergence, *and* alignment papers (CoT shows up in Constitutional
  AI's critiques).

**2. Cluster hubs — the center of one topic.** High concept-to-concept in-degree
(Cin) within their area:
- [RLHF](../wiki/concepts/rlhf.md) (Cin 8) — everything in
  [alignment](../wiki/topics/alignment-and-preference-learning.md) defines itself
  relative to it.
- [rl-for-reasoning](../wiki/concepts/rl-for-reasoning.md) (Cin 6) — the hub of
  the reasoning cluster (pulls in GRPO, distillation, test-time compute, PPO).

**3. Bridges — the connectors between topics.** These are the high-value reads
because they explain how the clusters relate:
- [chain-of-thought](../wiki/concepts/chain-of-thought.md) — links reasoning ↔
  emergence ↔ in-context learning ↔ alignment. The single most connected node.
- [emergent-abilities](../wiki/concepts/emergent-abilities.md) and
  [in-context-learning](../wiki/concepts/in-context-learning.md) — stitch
  [scaling](../wiki/topics/scaling-and-emergence.md) to
  [reasoning](../wiki/topics/llm-reasoning.md).
- [supervised-fine-tuning](../wiki/concepts/supervised-fine-tuning.md) — the only
  concept living in **two** topics (pretraining *and* alignment); it's the seam
  between "how models learn" and "how models are aligned."

## Start-here reading path

A four-tier path that follows the graph outward from the roots:

**Tier 0 — Foundation (read first)**
1. [transformer](../wiki/concepts/transformer.md) →
   [self-attention](../wiki/concepts/self-attention.md)

**Tier 1 — The three storylines' roots**
2. Scaling: [scaling-laws](../wiki/concepts/scaling-laws.md) →
   [emergent-abilities](../wiki/concepts/emergent-abilities.md) →
   [in-context-learning](../wiki/concepts/in-context-learning.md)
3. Alignment: [preference-learning](../wiki/concepts/preference-learning.md) →
   [RLHF](../wiki/concepts/rlhf.md)
4. Reasoning: [chain-of-thought](../wiki/concepts/chain-of-thought.md) →
   [rl-for-reasoning](../wiki/concepts/rl-for-reasoning.md)

**Tier 2 — Fill in each cluster**
- Alignment: [reward-modeling](../wiki/concepts/reward-modeling.md),
  [PPO](../wiki/concepts/ppo.md),
  [DPO](../wiki/concepts/direct-preference-optimization.md),
  [constitutional-ai](../wiki/concepts/constitutional-ai.md) /
  [RLAIF](../wiki/concepts/rlaif.md)
- Pretraining: [transfer-learning](../wiki/concepts/transfer-learning.md),
  [masked-language-modeling](../wiki/concepts/masked-language-modeling.md),
  [text-to-text-framework](../wiki/concepts/text-to-text-framework.md)
- Scaling: [compute-optimal-training](../wiki/concepts/compute-optimal-training.md)

**Tier 3 — Specialist leaves (read on demand)**
- [multi-head-attention](../wiki/concepts/multi-head-attention.md),
  [positional-encoding](../wiki/concepts/positional-encoding.md),
  [GRPO](../wiki/concepts/grpo.md),
  [reasoning-distillation](../wiki/concepts/reasoning-distillation.md),
  [test-time-compute](../wiki/concepts/test-time-compute.md)

## Observations

- The graph has **no dominant single center** — three comparably-sized hubs
  (chain-of-thought, RLHF, transformer) anchor three clusters, exactly mirroring
  the topic structure. That's a sign of healthy, balanced organization.
- The most-connected node is a **bridge** (chain-of-thought), not a root. The
  wiki's value concentrates where topics meet — reasoning borrowing from emergence
  and alignment.
- [supervised-fine-tuning](../wiki/concepts/supervised-fine-tuning.md) is worth
  highlighting structurally: as the lone two-topic concept it is the load-bearing
  seam between pretraining and alignment; if it were weak the two halves of the
  wiki would barely connect.

## Filing back

- Durable enough to promote: fold the **Tier 0–3 reading path** into
  [`wiki/INDEX.md`](../wiki/INDEX.md) as a short "Start here" section, so the
  navigational insight lives in the index rather than only in this report.
- Optional: add a one-line "role" (root / hub / bridge / leaf) to each concept's
  frontmatter tags if you want centrality queryable later.
