---
observed_at: 2026-09-10
source_type: chat-derived
source: observatory and canonical-state discussions
status: candidate
confidence: high
topic: contradiction visibility
applicability: dashboards, AI memory, project governance
---

# Contradictions between a projection and canon should be surfaced, not silently resolved

## Observation

Dashboards, memory summaries, generated current-state pages, and human notes can disagree with canonical artifacts.

## Interpretation

Silently choosing one source hides a potentially important state-management defect.

## Decision relevance

When a projection conflicts with canon, mark the contradiction, identify both sources and their times, stop downstream promotion when consequential, and record the correction path.

## Limits

Some differences are expected due to update lag; distinguish stale projection from true semantic contradiction.
