---
observed_at: 2026-09-10
source_type: chat-derived
source: workspace portability and contamination discussions
status: candidate
confidence: high
topic: vendor workspace lock-in
applicability: AI workspaces, portability, canonical knowledge
---

# A vendor workspace should not become the only canonical memory

## Observation

Workspace-specific knowledge, agents, chats, permissions, and analytics can be difficult or impossible to reproduce elsewhere.

## Interpretation

If critical system meaning exists only inside one vendor workspace, model replacement and platform migration become semantic recovery problems rather than ordinary infrastructure changes.

## Decision relevance

Keep durable canonical artifacts in a portable form when possible. Treat vendor workspace knowledge as a projection, execution surface, or cache unless its export and recovery path has been proven.

## Limits

Some organizations intentionally accept lock-in for operational simplicity. The risk should be explicit rather than accidental.
