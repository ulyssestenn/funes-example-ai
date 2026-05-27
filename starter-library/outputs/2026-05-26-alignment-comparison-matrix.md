---
title: "Alignment Comparison Matrix: RLHF vs. Constitutional AI vs. DPO"
type: analysis
tags: [alignment, rlhf, rlaif, dpo, preference-learning, synthesis]
created: 2026-05-26
updated: 2026-05-26
---
# Alignment Comparison Matrix: RLHF vs. Constitutional AI vs. DPO

A side-by-side comparison of the library's three alignment recipes, framed as
**deltas on a shared skeleton**. All three turn human/AI *preferences* into a
better-behaved policy; they differ in who supplies the feedback and how much
machinery sits between the preferences and the final weights.

Sources: [InstructGPT](../wiki/sources/instructgpt.md) (Ouyang 2022),
[Constitutional AI](../wiki/sources/constitutional-ai.md) (Bai 2022),
[Direct Preference Optimization](../wiki/sources/direct-preference-optimization.md)
(Rafailov 2023).

## TL;DR

- **[RLHF](../wiki/concepts/rlhf.md) (InstructGPT)** is the reference pipeline:
  SFT → reward model → PPO. Human feedback, explicit reward model, RL loop.
- **[Constitutional AI](../wiki/concepts/constitutional-ai.md)** keeps the RL
  machinery but swaps *human harm labels* for *AI labels* generated from a written
  constitution — i.e. [RLAIF](../wiki/concepts/rlaif.md). It changes the *feedback
  source*.
- **[DPO](../wiki/concepts/direct-preference-optimization.md)** keeps human
  feedback but deletes the reward model and the RL loop, solving the *same*
  objective with one classification loss. It changes the *optimizer*.

These two changes are **orthogonal**: CAI changes where preferences come from; DPO
changes how they're consumed.

## The shared skeleton

Every recipe here:
1. starts from a [supervised fine-tuned](../wiki/concepts/supervised-fine-tuning.md)
   (SFT) policy;
2. expresses goals as [preferences](../wiki/concepts/preference-learning.md) over
   response pairs (Bradley-Terry model);
3. regularizes the result toward the SFT/reference model with a KL penalty;
4. aims at [helpful, honest, harmless](../wiki/concepts/helpful-honest-harmless.md)
   behavior.

The matrix below is really about which parts of steps 2–3 each method keeps,
replaces, or removes.

## Main comparison

| Dimension | RLHF / InstructGPT | Constitutional AI / RLAIF | DPO |
|---|---|---|---|
| **Core move** | Align to human intent via preference-trained reward + RL | Train harmlessness from a written constitution, no human harm labels | Optimize preferences directly, no RL |
| **Feedback source** | Humans (demonstrations + rankings; ~40 contractors) | **AI** for harmlessness (guided by constitution); humans for helpfulness | Humans (or any) preference pairs — same data as RLHF |
| **Pipeline** | SFT → reward model → PPO (steps 2–3 iterate) | SL stage: critique → revision → SFT (SL-CAI); RL stage: AI comparisons → preference model → RL (RL-CAI) | SFT → DPO (single preference-classification phase) |
| **Explicit reward/preference model?** | Yes (human-labeled) | Yes (**hybrid**: human helpfulness + AI harmlessness) | **No** — the policy *implicitly* is its own reward model |
| **RL loop (PPO)?** | Yes | Yes | **No** — no PPO, no on-policy sampling in the loop |
| **What's optimized** | Expected reward under KL constraint to SFT | Same RL objective, harm reward from AI preferences | *Same* KL-constrained objective, solved in closed form as binary cross-entropy |
| **Human-label cost** | High (demonstrations + many comparisons) | Low for harm (~10–16 principles + few examples); human helpfulness retained | Moderate (preference pairs; no RM/RL infra) |
| **Key advantage** | Strong intent-following; 1.3B preferred over 175B GPT-3 | Scalable oversight; non-evasive assistant; Pareto gain on HH frontier | Simple, stable, lightweight; matches/beats PPO-RLHF up to ~6B |
| **Key cost / failure mode** | Expensive labels; [alignment tax](../wiki/concepts/rlhf.md); reward hacking; RL instability | Depends on base model's harm-judgment ability; constitution design; RL complexity remains | Offline (no fresh samples); reference-model dependence; needs its dynamic weighting to avoid degeneration |
| **Delta vs. RLHF baseline** | (is the baseline) | Replaces human harm labels with AI labels; adds self-critique/revision SL stage | Removes the reward model **and** the RL loop |

## Tradeoff axes (where each sits)

- **Human-labeling burden:** RLHF (high) → DPO (moderate) → CAI (low for harm).
- **Infrastructure complexity:** RLHF ≈ CAI (reward/preference model + PPO) ≫ DPO
  (one supervised-style loss).
- **On-policy freshness:** RLHF/CAI sample from the current policy during RL; DPO
  is offline on a fixed preference set.
- **Transparency of the target:** CAI's constitution makes the harm objective
  explicit and editable; RLHF/DPO bury it in the preference data.

## How they relate (not mutually exclusive)

- CAI **builds on** RLHF — it is RLHF with an AI-feedback front-end for harm, plus
  a self-improvement SFT stage. [Chain-of-thought](../wiki/concepts/chain-of-thought.md)
  reasoning in the AI critiques materially improves harm judgments.
- DPO is an **alternative optimizer** for the RM+PPO stages, not an alternative
  goal — it optimizes the same KL-constrained reward objective.
- The two axes compose: in principle one could run **DPO on AI-labeled
  preferences** (DPO + RLAIF), combining cheap supervision with a simple
  optimizer. The library doesn't cover that combination — flagged as an extension.

## Tensions & caveats (honest reading)

- **Helpfulness vs. harmlessness.** Training only against harm yields an evasive
  model; CAI's *non-evasiveness* (explain objections rather than deflect) is its
  answer to the tension InstructGPT surfaced. This is a design choice, not a
  solved problem.
- **AI feedback inherits the labeler's blind spots.** RLAIF's quality is bounded
  by the base model's ability to judge harm — strong at scale (>52B in CAI),
  weaker for small models.
- **DPO's "no reward model" is a reparameterization, not magic.** A reward is
  still implicit in the policy; DPO's stability depends on the per-example dynamic
  weighting and a good reference model, and being offline it can be more sensitive
  to preference-data coverage than on-policy RLHF.

## Which to reach for

- **Need maximal control / on-policy refinement, have labeling budget →** RLHF.
- **Want to cut human harm-labeling and make the safety target explicit →** CAI /
  RLAIF.
- **Want the simplest stable pipeline and already have preference pairs →** DPO.

## Filing back

- Durable enough to promote into the wiki: a small comparison note or table under
  [alignment-and-preference-learning](../wiki/topics/alignment-and-preference-learning.md)
  capturing the "shared skeleton + two orthogonal deltas (feedback source vs.
  optimizer)" framing.
- Coverage gaps this exposed (ingest candidates): online/iterated DPO and DPO-vs-PPO
  follow-ups; combining RLAIF with DPO; reward-hacking / over-optimization
  literature.
