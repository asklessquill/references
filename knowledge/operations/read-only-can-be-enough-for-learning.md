---
observed_at: 2026-09-10
source_type: chat-derived
source: lab and operations boundary discussions
status: candidate
confidence: high
topic: read-only learning
applicability: safe experiments, agents, platform demos
---

# Read-only access can be enough to learn before write authority exists

## Observation

Many unknowns concern data shape, workflow frequency, permission boundaries, decision context, or failure conditions rather than the ability to mutate external state.

## Interpretation

A read-only experiment can create real evidence while containing risk.

## Decision relevance

Start with observation when it can answer the next design question. Grant write authority only when the experiment specifically needs to prove activation or side-effect behavior.

## Limits

Read-only testing cannot prove write-path authorization, idempotency, rollback, or real-world effect.
