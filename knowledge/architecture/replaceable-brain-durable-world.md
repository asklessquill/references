---
observed_at: 2026-09-10
source_type: chat-derived
source: account portability and AI recovery discussions
status: candidate
confidence: high
topic: replaceable AI brain and durable external state
applicability: AI system architecture, portability, recovery, vendor independence
---

# The brain should be replaceable; the world should be durable

## Observation

Conversational AI state is useful but fragile: accounts, memory, model availability, subscriptions, context windows, and product surfaces can change. A system that depends on one chat history or one model instance cannot be reliably recovered.

## Interpretation

Durable meaning should live outside the transient reasoning surface. The AI brain may change; canonical state, evidence, accepted decisions, and recovery instructions should survive that change.

A robust pattern is:

```text
transient brain
    ↓ reads
canonical state + evidence + recovery contract
    ↓ produces
candidate change
    ↓ review / acceptance
updated durable state
```

The external store is not merely backup storage. It is the boundary that allows a fresh model or account to reconstruct the system without inheriting hidden conversational assumptions.

## Decision relevance

This pattern supports:

- account migration
- model replacement
- multi-model operation
- disaster recovery
- independent review
- reduced vendor lock-in
- clearer authority boundaries

A useful recovery test is whether a fresh actor can explain the current state and next permitted action using durable evidence alone.

## Limits

Externalizing state does not guarantee semantic recovery. Canonical documents can themselves be stale or contaminated, so provenance and acceptance status remain necessary.
