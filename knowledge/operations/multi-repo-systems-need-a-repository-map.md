---
observed_at: 2026-09-10
source_type: chat-derived
source: multi-repository cleanup and portability discussions
status: candidate
confidence: high
topic: repository map
applicability: multi-repo development, AI handoff, workspace recovery
---

# Multi-repository systems need an explicit repository map

## Observation

As repositories, worktrees, branches, local clones, labs, and archived folders multiply, naming conventions alone stop being enough to identify authority and purpose.

## Interpretation

A repository map is operational infrastructure for humans and fresh agents.

## Decision relevance

Maintain a compact mapping of conceptual component, canonical repository, default branch, active candidate branches, local paths when relevant, visibility, and status. Keep it descriptive rather than turning the map itself into hidden authority.

## Limits

The map must stay current; stale maps can be worse than no map when automation trusts them blindly.
