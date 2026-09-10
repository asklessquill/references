---
observed_at: 2026-09-10
source_type: chat-derived
source: autonomous execution reliability discussions
status: candidate
confidence: high
topic: restart and resume
applicability: workflow engines, autonomous agents, distributed systems
---

# Restart and resume behavior is part of the operational contract

## Observation

Persistent agents and workflow engines inevitably restart. If the system cannot determine what was detected, delivered, executed, and returned before the restart, it cannot safely resume.

## Interpretation

Crash recovery should be designed into durable state transitions rather than reconstructed from logs after failure.

## Decision relevance

Persist enough identity and state to answer: was the command seen, was execution started, did a side effect occur, was the result committed, and was the return acknowledged?

## Limits

Stateless read-only jobs may simply restart from the beginning when duplicate work is harmless.
