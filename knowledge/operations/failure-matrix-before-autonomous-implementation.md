---
observed_at: 2026-09-10
source_type: chat-derived
source: autonomous transport and restart design discussions
status: candidate
confidence: high
topic: failure matrix
applicability: autonomous agents, workflow engines, distributed execution
---

# Write the failure matrix before making an autonomous path persistent

## Observation

A happy-path prototype can appear reliable until restarts, duplicate triggers, timeouts, nonzero exits, push failures, credential boundaries, or partial returns occur.

## Interpretation

Persistent autonomy changes failures from occasional developer inconveniences into repeated operational states.

## Decision relevance

Before productionizing, enumerate transport failure, executor failure, restart, duplicate, stale input, conflicting command, return failure, external write failure, and recovery behavior. Define whether each retries, resumes, rejects, rolls back, or escalates.

## Limits

The matrix should match actual system dependencies; exhaustive theoretical failure enumeration can become design paralysis.
