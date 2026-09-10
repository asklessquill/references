---
observed_at: 2026-09-10
source_type: chat-derived
source: quota and service-load failure discussions
status: candidate
confidence: high
topic: transient versus structural model failure
applicability: model routing, incident analysis, benchmarking
---

# Transient service failure should not be recorded as model incapability

## Observation

High load, quota exhaustion, tool outage, credential failure, or temporary service errors can cause a route to fail even when the model is capable of the task.

## Interpretation

Routing knowledge should distinguish semantic failure from availability failure.

## Decision relevance

Classify failures into model reasoning, prompt/task contract, tool/capability, environment, quota, service availability, authority, and unknown. Use different retry and learning behavior for each.

## Limits

Repeated availability failures can still make a route operationally unsuitable even if the underlying model is capable.
