---
observed_at: 2026-09-10
source_type: chat-derived
source: account portability and contamination-recovery discussions
status: candidate
confidence: high
topic: fresh-brain recovery
applicability: AI-assisted development, account portability, recovery, contamination control
---

# Fresh-brain recovery should be evidence-based, not memory cloning

## Observation

When an AI workspace or conversational brain may contain stale, contradictory, or contaminated assumptions, copying all prior context into a new environment can reproduce the same failure state.

A safer recovery pattern is:

```text
possibly contaminated environment
        ↓
quarantine, do not destroy
        ↓
trusted checkpoints + evidence only
        ↓
fresh Actor
        ↓
independent reconstruction
        ↓
compare against canonical sources
        ↓
promote only verified state
```

## Interpretation

Portability is stronger when a fresh Actor can reconstruct the current system from durable evidence rather than inheriting an opaque conversational state.

This turns account migration into a recovery test rather than a data-copy exercise.

## Decision relevance

Useful controls include:

- keep the old environment available as reference but not authority;
- identify trusted commit SHAs and acceptance evidence;
- label uncertain or contaminated periods explicitly;
- prohibit redesign during recovery unless separately authorized;
- compare the fresh Actor's reconstruction with canonical sources;
- promote recovered knowledge only after discrepancy review.

## Limits

A fresh Actor is not automatically correct. It can still misread evidence. Recovery quality depends on the completeness and trustworthiness of durable checkpoints and the clarity of authority boundaries.
