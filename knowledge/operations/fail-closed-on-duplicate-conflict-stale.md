---
observed_at: 2026-09-10
source_type: chat-derived
source: autonomous command transport design discussions
status: candidate
confidence: high
topic: fail-closed command handling
applicability: distributed agents, command queues, automation
---

# Duplicate, conflicting, and stale commands should fail closed

## Observation

Autonomous command pipelines can receive repeated, conflicting, or outdated instructions because of retries, restarts, network duplication, or delayed delivery.

## Interpretation

Retry safety requires stable command identity and explicit state transitions. Blindly executing whatever arrives last can convert transport faults into real-world side effects.

## Decision relevance

Track command identity, source version, execution state, and return version. Detect duplicate, conflict, and stale conditions before execution, and stop for ambiguity when consequences matter.

## Limits

Idempotent read-only operations may safely tolerate duplicates, but the policy should be intentional.
