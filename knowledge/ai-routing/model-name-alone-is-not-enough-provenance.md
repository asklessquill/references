---
observed_at: 2026-09-10
source_type: chat-derived
source: model routing knowledge-base discussions
status: candidate
confidence: high
topic: model provenance
applicability: model routing, benchmarks, reproducibility
---

# Model name alone is not enough routing provenance

## Observation

The same branded model can behave differently across versions, reasoning tiers, product surfaces, tools, context sizes, and quota regimes.

## Interpretation

Routing evidence that records only a model family name is difficult to reuse or compare later.

## Decision relevance

Capture model/version when known, reasoning effort or tier, product surface, context/tool breadth, date, task type, and relevant quota state alongside outcome.

## Limits

Some products do not expose exact versions. Record the best observable identity and uncertainty rather than inventing precision.
