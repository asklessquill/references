---
observed_at: 2026-09-10
source_type: chat-derived
source: repository cleanup and portability discussions
status: candidate
confidence: high
topic: git worktree safety
applicability: repository cleanup, portability, developer environments
---

# Inventory Git worktrees before cleaning folders

## Observation
Folders that look duplicated or mysterious can be active Git worktrees tied to branches or in-progress work.

## Interpretation
Filesystem cleanup without Git-aware inventory can destroy valid working state or confuse branch ownership.

## Decision relevance
Before moving or deleting repository-like folders:
- run `git worktree list`
- map path -> repository -> branch -> purpose
- inspect dirty state
- remove obsolete worktrees with Git-aware commands
- archive only directories proven to be ordinary folders

## Limits
Worktrees are only one source of hidden coupling. Submodules, symlinks, junctions, generated caches, and external tooling may also matter.
