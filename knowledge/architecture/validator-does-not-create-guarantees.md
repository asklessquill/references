---
observed_at: 2026-09-10
source_type: chat-derived
source: protocol validator boundary discussion
status: candidate
confidence: high
topic: validator evidence boundary
applicability: protocol design, distributed systems, agent safety
---

# A validator can check evidence without creating the guarantee

## Observation

A pure validator may confirm that required evidence is present and internally consistent, but it does not thereby prove that a distributed runtime actually enforced side-effect safety, identity, ordering, or authorization.

## Interpretation

Validation of a claim and production of the underlying guarantee belong to different components.

## Decision relevance

Document which guarantees must be supplied by executors, transports, identity systems, or external evidence. Avoid wording that lets a representation layer claim properties it cannot enforce.

## Limits

Formal verification can establish stronger properties when the relevant runtime model is included; this principle concerns validators whose scope is only exchanged evidence.
