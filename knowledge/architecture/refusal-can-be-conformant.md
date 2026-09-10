---
observed_at: 2026-09-10
source_type: chat-derived
source: protocol refusal and hold semantics discussion
status: candidate
confidence: high
topic: refusal semantics
applicability: agent protocols, authorization, safety
---

# A refusal can be the correct conformant result

## Observation

Protocol implementations sometimes treat any refusal, pause, or inability to proceed as failure.

## Interpretation

When authority, evidence, or safety prerequisites are absent, refusing or holding may be exactly what conformance requires.

## Decision relevance

Test valid refusal paths alongside success paths. A conformance suite should verify that unsafe progress is rejected for the right reason, not merely that happy-path work completes.

## Limits

Refusal must still be explainable and consistent with the protocol; arbitrary non-performance is not automatically conformant.
