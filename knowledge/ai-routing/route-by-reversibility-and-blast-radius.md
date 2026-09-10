---
observed_at: 2026-09-10
source_type: chat-derived
source: model tier selection and architecture review discussions
status: candidate
confidence: high
topic: routing by consequence
applicability: model routing, agent governance, cost optimization
---

# Route expensive reasoning by reversibility and blast radius

## Observation

The strongest model is most valuable when an error would propagate widely or be expensive to undo: architecture boundaries, authority semantics, irreversible migration, acceptance, and recovery design.

## Interpretation

Task difficulty alone is an incomplete routing signal. Consequence and reversibility matter.

## Decision relevance

Escalate reasoning effort when one or more are high:

- irreversibility
- blast radius
- ambiguity of authority
- hidden coupling
- recovery cost
- semantic novelty

Use cheaper execution for deterministic transformations after the decision is fixed.

## Limits

High consequence does not guarantee a stronger model will be correct; independent evidence and review remain necessary.
