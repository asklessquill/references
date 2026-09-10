---
observed_at: 2026-09-10
source_type: chat-derived
source: local-versus-remote reconciliation discussions
status: candidate
confidence: high
topic: local state and authority
applicability: Git workflows, recovery, multi-agent development
---

# Mutable local state is evidence, not automatic authority

## Observation

Local worktrees can contain valid unpushed work, abandoned experiments, generated files, temporary state, and stale branches at the same time.

## Interpretation

Presence on disk does not make something canonical. Local state must be reconciled against branch lineage, fixed commits, accepted artifacts, and intended ownership.

## Decision relevance

Inventory before cleanup or promotion. Classify each difference as accepted work, candidate work, recoverable evidence, generated state, or disposable residue.

## Limits

In offline-first workflows local state may be the only surviving evidence; protect it before classification.
