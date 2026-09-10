---
observed_at: 2026-09-10
source_type: chat-derived
source: protocol architecture discussions
status: candidate
confidence: high
topic: capability versus knowledge
applicability: agent architecture, protocol design, tool systems
---

# Knowledge and capability are different resources

## Observation
Knowing that something can be done is not the same as possessing authority, credentials, tooling, runtime access, or permission to do it.

## Interpretation
Agent systems should model knowledge and capability separately. A planner may know a route exists while still being unable or unauthorized to execute it.

## Decision relevance
Represent at least:
- what is known
- what can be done
- by whom
- under which authority
- with which evidence
- in which runtime

## Limits
The exact schema depends on the system. The principle is separation of semantics, not a required data model.
