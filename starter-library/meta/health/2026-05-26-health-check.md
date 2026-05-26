# Health check — 2026-05-26

First health check after compiling the initial 12 sources. Scope: the whole
`starter-library` wiki (12 sources, 26 concepts, 5 topics).

## Summary

**Healthy.** All automated checks pass; no fixes were required.

| Check | Result |
|-------|--------|
| Broken relative links (wiki + raw) | 0 |
| Orphan concepts (no inbound link) | 0 |
| Source ↔ concept backlinks reciprocal | clean (both directions) |
| Concept ↔ topic backlinks reciprocal | clean (both directions) |
| Every concept mapped to ≥1 topic | yes (26/26) |
| `wiki/INDEX.md` coverage | 43/43 articles linked; no dangling links |
| Frontmatter (`title`/`type`/`created`/`updated`) | present on all 43 |
| Raw sources still marked `raw` | 0 (all 12 `compiled`) |

## Detail

- **Link integrity:** every `[...](...)` relative target in `wiki/` and
  `raw/INDEX.md` resolves to an existing file.
- **Backlinks:** for every source, each concept it lists cites the source back,
  and vice versa; same for the concept↔topic relation.
- **Indexes:** `wiki/INDEX.md` and `raw/INDEX.md` are current and consistent with
  the files on disk.

## No contradictions, with one reconciliation to note

- **Kaplan vs. Chinchilla scaling.** The two scaling papers give different
  compute-optimal recommendations (model-heavy vs. equal N/D scaling). This is a
  genuine revision in the literature, not a wiki inconsistency: it is handled
  explicitly in
  [`compute-optimal-training.md`](../../wiki/concepts/compute-optimal-training.md)
  and [`scaling-laws.md`](../../wiki/concepts/scaling-laws.md), which cross-link
  and state that Chinchilla corrects Kaplan. No action needed.

## Advisory — not defects, optional improvements

1. **Promotion candidates (currently folded into parent articles).** These are
   mentioned but lack their own atomic article; promote if more depth is wanted:
   - next-sentence prediction (NSP) — in `masked-language-modeling.md`
   - span-corruption objective — in `text-to-text-framework.md`
   - Bradley-Terry model — in `preference-learning.md`
   - C4 corpus — in the T5 source note
   - alignment tax — in `rlhf.md`
   - cold-start data / multi-stage pipeline — in `rl-for-reasoning.md`
2. **Coverage gaps relative to the field (would need new sources).** No source in
   the library yet covers tokenization, retrieval-augmented generation,
   mixture-of-experts, or evaluation/benchmarks. These are not gaps against the
   current 12 sources — flagged only as natural next ingest targets.
3. **Tag vocabulary** is lightly ad hoc (e.g. `rl-free`, `objective`,
   `scalable-oversight`). Fine at this size; consider a controlled tag list if the
   library grows.

## Recommended actions

- None required. The wiki is internally consistent and fully linked.
- If desired, promote one or more folded concepts (item 1) and/or ingest sources
  to close coverage gaps (item 2).
