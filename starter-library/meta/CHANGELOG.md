# Changelog

Append-only log of changes the Librarian makes to the knowledge base. Newest
first.

## 2026-05-26 — Analysis: coverage gap analysis
- Wrote [`outputs/2026-05-26-coverage-gap-analysis.md`](../outputs/2026-05-26-coverage-gap-analysis.md),
  consolidating gaps from the health check and prior analyses into a prioritized
  ingest roadmap: in-scope gaps (P0–P2, e.g. emergence critique, RLHF precursors,
  inference-optimal scaling, tokenization), scope-expansion threads (RAG, agents,
  multimodality, evaluation), internal gaps, and a recommended next 3–5 ingests.

## 2026-05-26 — Analysis: concept-centrality map
- Wrote [`outputs/2026-05-26-concept-centrality-map.md`](../outputs/2026-05-26-concept-centrality-map.md),
  measuring the concept link graph (inbound links per article) to identify hubs —
  chain-of-thought, RLHF, and transformer anchor the three clusters — and turning
  the structure into a tiered "start here" reading path. Proposes adding that path
  to `wiki/INDEX.md`.

## 2026-05-26 — Analysis: alignment comparison matrix
- Wrote [`outputs/2026-05-26-alignment-comparison-matrix.md`](../outputs/2026-05-26-alignment-comparison-matrix.md),
  comparing RLHF (InstructGPT), Constitutional AI/RLAIF, and DPO as deltas on a
  shared skeleton (SFT + preferences + KL-to-reference): feedback source vs.
  optimizer as two orthogonal axes, a full comparison table, tradeoffs, and
  "which to reach for." Proposes filing the framing back under the alignment topic.

## 2026-05-26 — Analysis: the scaling narrative
- Wrote [`outputs/2026-05-26-scaling-narrative.md`](../outputs/2026-05-26-scaling-narrative.md),
  a synthesis across the scaling/emergence/reasoning sources (Kaplan → GPT-3 →
  Emergent Abilities → Chinchilla → CoT → DeepSeek-R1): smooth loss vs. emergent
  capabilities, the recurring compute-allocation question, and the shift toward
  test-time compute. Notes open tensions and proposes a "train-time vs. test-time
  scaling" concept to file back into the wiki.

## 2026-05-26 — Health check (clean)
- Audited the full wiki; wrote
  [`meta/health/2026-05-26-health-check.md`](./health/2026-05-26-health-check.md).
- All checks pass: 0 broken links, 0 orphans, reciprocal source/concept/topic
  backlinks, full `INDEX.md` coverage, complete frontmatter, all sources
  `compiled`. No fixes required; logged optional promotion/coverage suggestions.

## 2026-05-26 — Compiled all 12 sources into the wiki
- Wrote 12 source notes in [`wiki/sources/`](../wiki/sources/) (summary, key
  takeaways, extracted concepts) and marked sources 001–012 `compiled` in
  [`raw/INDEX.md`](../raw/INDEX.md).
- Created 26 atomic concept articles in [`wiki/concepts/`](../wiki/concepts/),
  bidirectionally backlinked to sources and related concepts.
- Created 5 topic maps in [`wiki/topics/`](../wiki/topics/): transformer
  architecture, pre-training & transfer learning, scaling & emergence, alignment
  & preference learning, and LLM reasoning.
- Rebuilt [`wiki/INDEX.md`](../wiki/INDEX.md) as master navigation and set the
  library scope in [`AGENTS.md`](../AGENTS.md).

## 2026-05-26 — Ingested 12 foundational LLM/ML papers
- Registered 12 source PDFs already present in `raw/` into
  [`raw/INDEX.md`](../raw/INDEX.md) as IDs 001–012, status `raw`: Attention Is
  All You Need, BERT, Chain-of-Thought Prompting, Constitutional AI, DeepSeek-R1,
  Direct Preference Optimization, Emergent Abilities, GPT-3 (Few-Shot Learners),
  T5 (Limits of Transfer Learning), Scaling Laws, Chinchilla (Compute-Optimal),
  and InstructGPT (Instructions with Human Feedback).
- Confirmed each title/arXiv id from the PDF first page. Not yet compiled into the
  wiki.

## <date> — Initialized the library
- Created the scaffolding (`raw/`, `wiki/{sources,concepts,topics}/`, `outputs/`,
  `meta/`), index files, and the library `AGENTS.md` pointing at the shared
  [Librarian Protocol](../../protocol.md).
