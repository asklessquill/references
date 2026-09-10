---
observed_at: 2026-09-10
source_type: chat-derived
source: organizational knowledge contamination discussion
status: candidate
confidence: high
topic: knowledge and state separation
applicability: agent platforms, company knowledge, autonomous systems
---

# Separate canon, reference, runtime state, instructions, and experiments

## Observation

AI systems often place durable truth, useful background, changing operational state, agent policy, and experimental hypotheses into one searchable knowledge surface.

## Interpretation

These classes have different authority, freshness, correction, and contamination behavior.

## Decision relevance

Maintain explicit boundaries between:

- canonical knowledge: accepted durable meaning
- reference knowledge: decision evidence without authority
- runtime/current state: time-sensitive operational facts
- agent instructions: role, authority, and prohibitions
- experimental knowledge: unaccepted hypotheses and observations

Define promotion and invalidation paths between them.

## Limits

Physical storage can be shared if semantic classes remain explicit and enforceable.
