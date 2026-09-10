---
observed_at: 2026-09-10
source_type: chat-derived
source: protocol conformance implementation discussion
status: candidate
confidence: high
topic: conformance versus action readiness
applicability: protocols, validators, autonomous agents
---

# Protocol conformance and permission to proceed are different judgments

## Observation

A valid protocol exchange can still be unable to progress because authority, evidence, prerequisites, or side-effect guarantees are missing.

## Interpretation

A validator should not force one boolean to represent both semantic conformance and operational readiness.

## Decision relevance

Return separate results such as:

- conforms / does not conform
- may proceed / must hold / must reject
- reasons and missing evidence

A legitimate refusal or hold can be fully conformant behavior.

## Limits

Simple protocols may not need separate readiness semantics, but consequential autonomous systems usually benefit from the distinction.
