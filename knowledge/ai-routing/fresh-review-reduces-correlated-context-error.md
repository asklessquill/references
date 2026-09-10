---
observed_at: 2026-09-10
source_type: chat-derived
source: fresh independent reviewer and contamination discussions
status: candidate
confidence: high
topic: fresh review and correlated error
applicability: AI review, architecture acceptance, model ensembles
---

# Fresh review reduces correlated context error

## Observation

A reviewer that shares the builder's long conversation, memory, and assumptions may reproduce the same interpretation even when using a strong model.

## Interpretation

Independence is partly about context separation, not merely a different prompt or model label.

## Decision relevance

For high-leverage acceptance, give a fresh reviewer the fixed artifact, explicit review contract, and necessary canonical evidence without unnecessary builder reasoning history. Compare findings before promotion.

## Limits

Freshness can remove useful context too; the review package must still contain the semantics required to judge the candidate fairly.
