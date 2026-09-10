---
observed_at: 2026-09-10
source_type: chat-derived
source: quota and model planning discussions
status: candidate
confidence: high
topic: quota-aware routing
applicability: model routing, workload scheduling, subscription planning
---

# Quota is part of model capability

## Observation

A model that is excellent but unavailable when needed may produce a worse system outcome than a slightly weaker model with sufficient capacity.

## Interpretation

Effective capability is model quality multiplied by availability within the workflow's timing constraints.

## Decision relevance

Routing records should include remaining quota, reset horizon, expected task volume, interruption cost, and fallback model or surface. Treat quota exhaustion as evidence for future routing, not merely an inconvenience.

## Limits

Quota information is often approximate or vendor-specific and may need empirical measurement.
