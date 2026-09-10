---
observed_at: 2026-09-10
source_type: chat-derived
source: loose-coupling protocol design discussions
status: candidate
confidence: high
topic: protocol ownership boundary
applicability: distributed systems, multi-agent architecture, integration protocols
---

# A connection protocol should not own application internals

## Observation
Protocols become brittle when they absorb the internal responsibilities of the applications they connect.

## Interpretation
A protocol should define the semantic contract for connection, exchange, authority, lifecycle, recovery, and evidence while leaving internal application behavior to each participant.

## Decision relevance
When a protocol starts specifying internal business logic, local state ownership, model choice, or application implementation details, treat that as a boundary warning.

## Limits
Some shared minimum representation is necessary for interoperability. Boundary discipline does not mean zero shared semantics.
