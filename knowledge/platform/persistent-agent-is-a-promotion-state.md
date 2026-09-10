---
observed_at: 2026-09-10
source_type: chat-derived
source: workspace agent adoption discussions
status: candidate
confidence: high
topic: persistent agent promotion
applicability: agent platforms, workflow automation, governance
---

# Making a workflow persistent is a promotion decision

## Observation

A one-off agent run has bounded exposure. Turning the same workflow into a scheduled or triggerable persistent agent creates repeated execution, accumulated state, and a broader failure surface.

## Interpretation

Persistence is not merely a convenience setting; it promotes the workflow into operational infrastructure.

## Decision relevance

Before persistence, require a stable task contract, known knowledge sources, authority boundaries, idempotency where needed, observability, failure handling, and a disable path.

## Limits

Read-only low-risk recurring summaries can justify a lighter promotion bar.
