---
observed_at: 2026-09-10
source_type: chat-derived
source: capability hub and protocol discussions
status: candidate
confidence: medium
topic: semantic capability discovery
applicability: MCP, plugin ecosystems, autonomous capability selection
---

# Capability discovery needs more than a tool catalog

## Observation

A registry can tell an agent that a tool exists while leaving unanswered what authority it needs, what side effects it causes, what evidence it returns, how failures are represented, and whether its semantics fit the task.

## Interpretation

Autonomous Build / Buy / Borrow / Reuse decisions require semantic contracts, not only endpoint descriptions.

## Decision relevance

A useful capability record should expose purpose, inputs, outputs, authority requirements, side effects, cost, failure modes, provenance, freshness, and recovery behavior.

## Limits

Existing registries may provide only part of this metadata; adapters or learned evidence may be necessary.
