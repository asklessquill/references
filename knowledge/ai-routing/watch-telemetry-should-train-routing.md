---
observed_at: 2026-09-10
source_type: chat-derived
source: scheduled watch and model-routing discussions
status: candidate
confidence: high
topic: operational telemetry for routing
applicability: model routing, scheduled tasks, agent evaluation
---

# Scheduled monitoring should produce routing evidence, not only reports

## Observation
Recurring watch tasks generate repeated measurements about freshness, tool reliability, latency, cost, model behavior, and intervention needs.

## Interpretation
If those observations are only rendered as reports, valuable routing data is lost.

## Decision relevance
For recurring agent runs, retain structured episode data such as:
- task features
- chosen model and tool path
- elapsed time
- quota or cost pressure
- tool failures
- semantic outcome
- rework
- human intervention
- whether a different route would likely have been better

## Limits
Operational telemetry can be noisy and biased by task mix. It should inform routing rather than automatically determine it.
