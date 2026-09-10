---
observed_at: 2026-09-10
source_type: chat-derived
source: local repository cleanup discussions
status: candidate
confidence: high
topic: semantic cleanup
applicability: developer workspaces, repository hygiene, recovery
---

# Cleanup should be semantic, not cosmetic

## Observation

Folders that look redundant or mysterious may be active worktrees, recovery copies, generated state, or branch-specific environments.

## Interpretation

Moving or deleting based on appearance can destroy lineage or make Git metadata inconsistent.

## Decision relevance

Before cleanup, map path -> repository -> branch -> worktree status -> authority -> retention reason. Use native removal mechanisms for managed structures such as worktrees rather than filesystem moves.

## Limits

Truly empty or disposable folders can still be archived or deleted once classification is complete.
