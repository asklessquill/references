---
observed_at: 2026-09-10
source_type: chat-derived
source: model-routing design discussions
status: candidate
confidence: high
topic: routing episodes as learning records
applicability: adaptive model routing, evaluation, cost-quality optimization
---

# Preserve each routing decision as a training record

## Observation

Static routing rules age quickly because model capabilities, quotas, pricing, tools, and task types change. A routing system becomes more useful when it can learn from actual episodes instead of only following a hand-authored matrix.

## Interpretation

Each model-selection episode should be treated as an evaluation record containing both the decision and the outcome.

Useful fields include:

- task features and decomposition
- selected model, version, tier, and surface
- context and tool breadth
- concurrency and quota risk
- estimated versus actual time / usage / cost where known
- semantic outcome and review result
- scope discipline
- rework, rollback, or failure
- Human intervention required
- whether a cheaper or different route would likely have sufficed

## Decision relevance

Accumulating these episodes enables later answers to questions such as:

- Which model is best for this kind of task?
- When is a premium reasoning tier actually worth it?
- Which tasks fail because of model weakness versus context or process weakness?
- What routing patterns create unnecessary quota burn?

## Limits

Observed usage and cost data can be incomplete or vendor-specific. Records should preserve uncertainty rather than invent precise measurements.
