---
observed_at: 2026-09-10
source_type: chat-derived
source: autonomous command-return loop discussions
status: candidate
confidence: high
topic: durable return
applicability: multi-agent workflows, Git-based automation, handoffs
---

# An execution return should become durable before the next decision depends on it

## Observation

If an executor reports success only in a transient chat or process stream, the next actor may act on a result that cannot later be reconstructed or verified.

## Interpretation

The return path is part of durable system memory.

## Decision relevance

Persist the result identity, source command, produced artifact or commit, verification evidence, and outcome status before allowing downstream decisions to treat the execution as established.

## Limits

Low-value ephemeral tasks may not justify durable returns; persistence should match consequence and reuse value.
