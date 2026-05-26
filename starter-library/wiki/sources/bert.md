---
title: "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding"
type: source
tags: [pretraining, transfer-learning, encoder, nlp]
created: 2026-05-26
updated: 2026-05-26
---
# BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding
- **Raw file:** [BERT.pdf](../../raw/BERT.pdf)
- **Original:** Devlin, Chang, Lee, Toutanova (Google AI Language), 2018 ([arXiv:1810.04805](https://arxiv.org/abs/1810.04805))

## Summary
BERT pre-trains a deep **bidirectional** Transformer encoder on unlabeled text using **masked language modeling** plus next-sentence prediction, then fine-tunes the single pre-trained model with one added output layer to reach state of the art across many NLP tasks — without task-specific architectures.

## Key takeaways
- New SOTA on 11 tasks: GLUE 80.5% (+7.7), MultiNLI 86.7% (+4.6), SQuAD v1.1 test F1 93.2, SQuAD v2.0 test F1 83.1.
- Two sizes: BERT-Base (110M, matched to OpenAI GPT) and BERT-Large (340M).
- MLM masks 15% of WordPiece tokens (80% `[MASK]`, 10% random, 10% unchanged) to reduce pretrain/fine-tune mismatch.
- Ablations show bidirectionality (MLM) is the key ingredient; a left-to-right variant degrades sharply.
- Pre-trained on BooksCorpus (800M words) + English Wikipedia (2.5B words); fine-tuning is cheap (~1 hour on a Cloud TPU).
- Next-sentence prediction (NSP) is a secondary objective for sentence-pair tasks; later work found it largely unnecessary.

## Concepts extracted
- [Masked language modeling](../concepts/masked-language-modeling.md)
- [Transfer learning (pre-train then fine-tune)](../concepts/transfer-learning.md)
- [Transformer](../concepts/transformer.md)
