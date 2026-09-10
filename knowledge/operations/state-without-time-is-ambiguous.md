---
observed_at: 2026-09-10
source_type: chat-derived
source: project observability discussions
status: candidate
confidence: high
topic: temporal state
applicability: current-state files, dashboards, monitoring
---

# State without time is ambiguous

## Observation

Statements such as complete, blocked, active, or unchanged lose operational meaning when the observer cannot tell when they were established or which evidence version they describe.

## Interpretation

Current state is inherently temporal.

## Decision relevance

Attach observation time, evidence version, and when relevant effective time to status claims. Preserve chronology so a fresh reader can distinguish stale truth from current truth.

## Limits

Immutable historical artifacts already carry time through version history, but projections still benefit from explicit observation context.
