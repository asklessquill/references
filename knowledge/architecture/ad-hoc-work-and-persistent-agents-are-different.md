---
observed_at: 2026-09-10
source_type: chat-derived
source: chat, work agent, coding agent, and workspace agent discussion
status: candidate
confidence: high
topic: ad-hoc versus persistent agents
applicability: agent platforms, workflow architecture, governance
---

# Ad-hoc work agents and persistent configured agents are different primitives

## Observation

A system may support both one-off delegated jobs and persistent agents with stable instructions, tools, knowledge sources, triggers, and organizational visibility.

## Interpretation

The latter creates a larger governance surface because errors in configuration can repeat and spread across runs.

## Decision relevance

Use ad-hoc agents for exploratory or irregular jobs. Promote a workflow to a persistent agent only after its task contract, knowledge boundary, authority, observability, and failure handling are stable.

## Limits

Some platforms blur these categories; classify by persistence and repeated authority rather than product naming.
