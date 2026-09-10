---
observed_at: 2026-09-10
source_type: chat-derived
source: dashboard and observability architecture discussions
status: candidate
confidence: high
topic: projection versus canon
applicability: dashboards, observability, repositories, AI state recovery
---

# A dashboard is a projection, not authority

## Observation
Human-readable dashboards and AI-readable current-state views are useful for navigation, but they can become stale or incomplete.

## Interpretation
A projection should point back to durable evidence and canonical sources rather than silently becoming the source of truth itself.

## Decision relevance
For every derived current-state view, preserve:
- source references
- generation or observation time
- confidence or completeness limits
- correction path

## Limits
Some systems intentionally designate a generated artifact as canonical. If so, that authority should be explicit rather than accidental.
