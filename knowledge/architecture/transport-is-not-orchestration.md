---
observed_at: 2026-09-10
source_type: chat-derived
source: automation transport and runtime boundary discussions
status: candidate
confidence: high
topic: transport versus orchestration
applicability: automation, agents, local execution, workflow systems
---

# Transport should not accidentally become the system brain

## Observation
A trigger or workflow transport layer can gradually absorb routing, policy, recovery, and execution ownership until it becomes an implicit orchestrator.

## Interpretation
Keep transport responsible for delivery and invocation unless orchestration is explicitly intended. Policy and semantic decisions should remain in the layer that owns them.

## Decision relevance
Separate at least:
- trigger / transport
- semantic decision
- local execution seam
- executor
- durable return

## Limits
Some products intentionally combine these roles. The important point is explicit ownership, not mandatory physical separation.
