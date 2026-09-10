---
observed_at: 2026-09-10
source_type: chat-derived
source: human relay and durable memory discussions
status: candidate
confidence: high
topic: conversational reasoning versus durable memory
applicability: AI-assisted development, project continuity, recovery
---

# Chat is working memory; Git is durable memory

## Observation

Conversational threads are excellent for active reasoning but poor as the sole durable record of system state. Git provides versioned, inspectable, branchable evidence that survives thread changes and model replacement.

## Interpretation

Use chat for active cognition and Git for durable state. Important decisions should cross the boundary from conversation into explicit artifacts before they become dependencies for later work.

## Decision relevance

Ask of every consequential chat decision: does a future actor need this to continue correctly? If yes, persist it outside the thread.

## Limits

Git does not automatically capture intent, uncertainty, or human context. Durable artifacts must be written with enough semantics to support recovery.
