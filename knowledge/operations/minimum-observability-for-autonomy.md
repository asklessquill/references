---
observed_at: 2026-09-10
source_type: chat-derived
source: autonomous execution and recovery discussions
status: candidate
confidence: high
topic: minimum autonomous observability
applicability: agents, workflow engines, unattended execution
---

# Autonomous execution needs enough observability to reconstruct what happened

## Observation

An unattended system can appear successful while losing the evidence needed to distinguish detection, execution, side effect, commit, return, or failure after the fact.

## Interpretation

Observability is part of recoverability, not only debugging convenience.

## Decision relevance

At minimum, retain stable operation identity, relevant input version, state transitions, executor result, produced durable artifact, error category, and timestamps. Add more detail when side effects or authority are consequential.

## Limits

Logging everything can create cost, privacy, and noise problems; capture evidence needed for decisions and recovery.
