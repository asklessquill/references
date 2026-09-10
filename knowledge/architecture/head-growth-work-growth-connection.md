---
observed_at: 2026-09-10
source_type: chat-derived
source: actor mapping and system decomposition discussions
status: candidate
confidence: medium
topic: separating whole-system cognition, growth mode, work mode, and connection
applicability: complex adaptive systems, multi-agent architecture
---

# Separate what the system is from how it grows, how it works, and how it connects

## Observation

Multi-agent systems become easier to reason about when four concerns are separated:

- whole-system cognition or identity
- growth direction such as vertical depth versus horizontal expansion
- work style such as research, implementation, and operations
- connection semantics between autonomous parts

## Interpretation

These are orthogonal axes, not peer actors with interchangeable responsibilities. Mixing them produces duplicated ownership and confusing control hierarchies.

## Decision relevance

When adding a new component, classify whether it changes system identity, growth strategy, work responsibility, or connection protocol before assigning ownership.

## Limits

The categories are conceptual aids, not mandatory product modules.
