---
observed_at: 2026-09-10
source_type: chat-derived
source: multi-repository actor architecture discussions
status: candidate
confidence: high
topic: repository boundaries versus system roles
applicability: multi-repo architecture, actor systems, repo governance
---

# Repository boundaries should not be mistaken for role boundaries

## Observation

As systems evolve, a named repository, actor, runtime, and conceptual responsibility can drift apart. A repository may host artifacts for a role without being identical to that role.

## Interpretation

Architecture becomes brittle when identity is inferred from folder or repository names alone. Responsibility should be defined semantically, then mapped to repositories and runtimes.

## Decision relevance

Maintain separate mappings for:

- conceptual role
- owned responsibility
- canonical artifacts
- implementation repository
- runtime executor
- external capabilities

This makes repository reorganizations survivable.

## Limits

For small systems one repository may legitimately equal one component. The warning matters when the system begins to recompose or reuse parts across runtimes.
