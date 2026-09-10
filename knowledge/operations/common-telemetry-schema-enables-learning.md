---
observed_at: 2026-09-10
source_type: chat-derived
source: scheduled report normalization discussions
status: candidate
confidence: high
topic: common telemetry schema
applicability: scheduled agents, routing telemetry, observability
---

# Common telemetry turns repeated reports into learnable data

## Observation

Many independent scheduled tasks can produce useful prose while remaining difficult to compare, aggregate, or train future routing decisions from.

## Interpretation

A shared output schema creates compounding value across watches and agents.

## Decision relevance

Normalize at least time, source, task, route, model or executor when relevant, change detected, confidence, cost or quota evidence, outcome, and next-decision relevance. Keep narrative summaries as a view over the structured record.

## Limits

Do not force unrelated tasks into a schema so rigid that important domain evidence is lost.
