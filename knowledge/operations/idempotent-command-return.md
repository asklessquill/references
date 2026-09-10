---
observed_at: 2026-09-10
source_type: chat-derived
source: autonomous command transport experiments
status: candidate
confidence: high
topic: idempotent command-return loop
applicability: automation, remote execution, agent transport
---

# Durable command-return loops need idempotency and explicit failure states

## Observation
Automated command transport becomes fragile when duplicate delivery, stale commands, crashes, or failed return pushes can silently re-run work.

## Interpretation
A durable loop should identify commands and results explicitly and fail closed on ambiguity.

## Decision relevance
Useful fields and checks include:
- command identifier
- source revision
- execution status
- result revision
- duplicate detection
- stale/conflict rejection
- restart/resume behavior
- timeout and non-zero exit handling
- return-delivery failure handling

## Limits
This pattern does not itself guarantee exactly-once side effects. External systems may require their own idempotency mechanisms.
