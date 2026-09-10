---
observed_at: 2026-09-10
source_type: chat-derived
source: distributed command and retry design discussions
status: candidate
confidence: high
topic: retry semantics
applicability: agent transport, workflow engines, distributed systems
---

# Retrying delivery is not the same as retrying execution

## Observation

A transport layer may safely resend a command while an execution layer may not safely repeat the side effect triggered by that command.

## Interpretation

Delivery attempts and execution attempts are different state machines. Conflating them hides duplicate-side-effect risk.

## Decision relevance

Record delivery attempt identity separately from execution attempt identity. Require execution-side idempotency or explicit evidence before repeating consequential work.

## Limits

Purely deterministic and side-effect-free computations can often be retried without this distinction becoming operationally important.
