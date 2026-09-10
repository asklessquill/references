---
observed_at: 2026-09-10
source_type: chat-derived
source: actor responsibility discussion
status: validated
confidence: high
topic: actor responsibility versus capability access
applicability: agent architecture, role design, tool integration
---

# An actor is defined by the work it does, not by the service it connects to

## Observation

A recurring design error is to define an actor by its connector, API, or vendor surface. For example, an operations actor that uses a productivity suite should not be described as the actor that connects to that suite.

## Interpretation

Connections are capabilities. Actors own responsibilities. A connector may change without changing the actor's identity.

## Decision relevance

When assigning roles, ask:

- What real-world responsibility does the actor own?
- Which capabilities may it use to fulfill that responsibility?
- Which capabilities are replaceable implementation details?

This prevents vendor surfaces from becoming architecture.

## Limits

Some actors may exist primarily to mediate access, but that must be an explicit responsibility rather than an accidental naming convention.
