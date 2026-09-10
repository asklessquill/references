---
observed_at: 2026-09-10
source_type: chat-derived
source: lab evidence and routing knowledge discussions
status: candidate
confidence: high
topic: failed experiment retention
applicability: R&D repositories, model routing, knowledge systems
---

# Failed experiments should remain searchable without becoming guidance

## Observation

Deleting failed experiments loses negative evidence, while placing them beside successful patterns without status can make future agents repeat or accidentally promote them.

## Interpretation

Failure evidence needs durable retention and explicit non-authoritative status.

## Decision relevance

Record hypothesis, setup, outcome, failure mode, lesson, applicability, and whether the result was rejected, superseded, or remains uncertain. Let search surface it as a warning, not a recommendation.

## Limits

Failures caused solely by transient outages should be classified separately from invalid designs.
