---
observed_at: 2026-09-10
source_type: chat-derived
source: cold executor and transport experiment discussions
status: candidate
confidence: high
topic: replaceable executor
applicability: agent runtimes, coding agents, cross-runtime architecture
---

# Executors should be replaceable behind a stable command-return contract

## Observation

A workflow becomes tightly coupled when the semantics of a task depend on one specific CLI, model surface, desktop application, or cloud runtime.

## Interpretation

If command identity, authority, inputs, expected artifacts, evidence, and return semantics are stable, the executor can change without redesigning the whole system.

## Decision relevance

Keep executor-specific launch details at the edge. Put durable meaning in the command-return contract and verify new executors against the same fixtures or acceptance expectations.

## Limits

Executors have different capabilities and failure modes; replacement still requires capability and safety validation.
