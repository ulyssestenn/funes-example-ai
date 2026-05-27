---
title: "The Scaling Narrative: from loss curves to test-time compute"
type: analysis
tags: [scaling, emergence, reasoning, synthesis]
created: 2026-05-26
updated: 2026-05-26
---
# The Scaling Narrative: from loss curves to test-time compute

A synthesis across the library's scaling-related sources, tracing one through-line:
how the field's idea of "scaling" shifted from a single smooth loss curve to a
multi-axis story that now includes capability *phase transitions* and compute
spent at *inference* time.

Sources drawn on: [Scaling Laws](../wiki/sources/scaling-laws.md) (Kaplan 2020),
[GPT-3](../wiki/sources/gpt-3-few-shot-learners.md) (Brown 2020),
[Emergent Abilities](../wiki/sources/emergent-abilities.md) (Wei 2022),
[Chinchilla](../wiki/sources/chinchilla-compute-optimal.md) (Hoffmann 2022),
[Chain-of-Thought](../wiki/sources/chain-of-thought-prompting.md) (Wei 2022),
[DeepSeek-R1](../wiki/sources/deepseek-r1.md) (DeepSeek-AI 2025).

## TL;DR

1. **Loss scales smoothly; capabilities often don't.** Power laws predict the
   pretraining *loss* of a model from its size, data, and compute — but specific
   *task* abilities can appear abruptly past a scale threshold.
2. **The compute-allocation question keeps getting re-answered.** First across
   model size vs. data (Kaplan → Chinchilla), and now across *training-time* vs.
   *test-time* compute (Chain-of-Thought → R1).
3. **Data became the binding constraint, which pushed effort toward inference.**
   Once Chinchilla showed models were undertrained and high-quality tokens were
   scarce, getting more capability *per inference* (longer reasoning) became an
   attractive new axis.

## The five moves

### 1. Loss is predictable — [scaling laws](../wiki/concepts/scaling-laws.md)
Kaplan et al. (2020) showed test cross-entropy falls as a **power law** in model
size N, dataset size D, and compute C, over >7 orders of magnitude, with
architectural shape mattering little. Two consequences set up everything that
follows: (a) you can *extrapolate* — predict a big model's loss before training
it; (b) there is an optimal way to spend a compute budget. Kaplan's answer to (b)
was to grow model size faster than data and stop before convergence.

### 2. Scale pays off — [in-context learning](../wiki/concepts/in-context-learning.md)
[GPT-3](../wiki/sources/gpt-3-few-shot-learners.md) (175B, co-authored by Kaplan)
is the bet that scaling laws justify cashed in. Its headline result isn't lower
loss but a *qualitatively* new behavior: **in-context learning** — solving tasks
from a few examples in the prompt, with no gradient updates. Bigger models use
in-context information more efficiently, so the *value* of scale exceeded what a
loss curve alone would suggest.

### 3. But capabilities jump — [emergent abilities](../wiki/concepts/emergent-abilities.md)
[Emergent Abilities](../wiki/sources/emergent-abilities.md) (Wei 2022) names the
gap between (1) and (2): some abilities are **absent in small models and present
in large ones**, appearing as a near-discontinuous jump at a critical scale.
Smooth loss-scaling laws therefore *do not* forecast when a given capability
arrives. This is the library's central productive tension — scaling laws and
emergence are complementary, not contradictory: one is about loss, the other
about tasks. (Note: whether emergence is a true phase transition or partly a
metric artifact is debated in later literature **not yet in this library** — see
gaps below.)

### 4. We were scaling wrong — [compute-optimal training](../wiki/concepts/compute-optimal-training.md)
[Chinchilla](../wiki/sources/chinchilla-compute-optimal.md) (Hoffmann 2022)
re-answers Kaplan's allocation question with more careful experiments: model size
and tokens should scale **equally** (~20 tokens/param), so the era's giant models
(Gopher, GPT-3, MT-NLG) were badly **undertrained**. Reallocating the *same*
compute toward more data yields a smaller, cheaper, better model. The sting in the
tail: high-quality **data volume** now becomes the scaling bottleneck.

### 5. Scale the *thinking*, not just the model — [test-time compute](../wiki/concepts/test-time-compute.md)
If train-time data is scarce, another lever is compute spent at **inference**.
[Chain-of-thought prompting](../wiki/concepts/chain-of-thought.md) (Wei 2022) is
the early form — letting the model emit intermediate reasoning lets it allocate
more steps to harder problems — and, tellingly, CoT is *itself* an emergent
ability (it only helps past ~100B params, linking move 5 back to move 3).
[DeepSeek-R1](../wiki/sources/deepseek-r1.md) (2025) makes this a *trained,
first-class axis*: via [RL for reasoning](../wiki/concepts/rl-for-reasoning.md)
the model learns to think longer, and accuracy rises with response length. The
scaling frontier moves from "bigger model" to "more reasoning per query."

## The synthesis: two scaling regimes

| | Train-time scaling | Test-time scaling |
|---|---|---|
| Axis | model size N, data D, compute C | reasoning length / samples at inference |
| Predictability | smooth power law (loss) | empirical; tied to reasoning quality |
| Capability behavior | emergent jumps at thresholds | smoother gains as "thinking" grows |
| Binding constraint | high-quality data (post-Chinchilla) | inference cost / latency |
| Library anchors | Scaling Laws, GPT-3, Chinchilla | Chain-of-Thought, DeepSeek-R1 |

The connective tissue is **emergence**: scale unlocks in-context learning (GPT-3)
and unlocks the *usefulness of CoT*, which is what test-time scaling exploits. So
the move from regime 1 to regime 2 isn't a break — it's emergence handing off the
baton from "what the weights know" to "how long the model reasons."

## Open tensions & caveats (honest reading)

- **Emergence may be partly a measurement choice.** The library asserts phase
  transitions (Wei 2022); subsequent work arguing these can be artifacts of
  discontinuous metrics is **not in the library**. Treat "phase transition" as the
  2022 framing, not a settled fact.
- **Chinchilla-optimal ≠ deployment-optimal.** ~20 tokens/param minimizes
  *training* loss for a compute budget; if you'll serve a model to many users,
  it's often worth "over-training" a smaller model to cut inference cost. The
  library states the training-optimal result; the inference-optimal refinement is
  a coverage gap.
- **Test-time scaling has no clean power law here.** R1 shows accuracy improving
  with longer reasoning, but the library has no analogue of Kaplan's clean
  exponents for inference compute — an open quantitative question.

## What this implies for a practitioner

- Use scaling laws to *plan* (extrapolate loss, size a run) but don't expect them
  to predict *which capabilities* you'll get — budget for evaluation.
- Post-Chinchilla, treat **data quality/quantity** as the first-order constraint,
  not parameter count.
- If a task is reasoning-heavy and data is scarce, **buy capability with inference
  compute** (CoT, sampling, RL-trained reasoning) rather than only a bigger model.

## Suggested follow-ups / filing back

- Durable enough to file into the wiki: a short concept,
  **"train-time vs. test-time scaling"**, capturing the two-regime table and the
  emergence hand-off, linked from both
  [scaling-and-emergence](../wiki/topics/scaling-and-emergence.md) and
  [llm-reasoning](../wiki/topics/llm-reasoning.md).
- Coverage gaps this analysis exposed (candidates to ingest): the "emergence as
  metric artifact" critique; inference-optimal / over-training scaling; and a
  quantitative treatment of test-time-compute scaling.
