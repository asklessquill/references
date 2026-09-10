---
observed_at: 2026-09-10
source_type: chat-derived
source: scheduled watch and account portability discussions
status: candidate
confidence: medium
topic: scheduled job portability
applicability: AI tasks, workflow migration, operations
---

# Scheduled jobs need a portable definition separate from the scheduler account

## Observation

Recurring AI tasks may depend on one account's scheduler, connected apps, hidden context, and output conventions. Changing accounts or platforms can silently strand operational behavior.

## Interpretation

The schedule is only one part of the task contract.

## Decision relevance

Persist the task purpose, cadence, source dependencies, permissions, prompt or logic, output schema, destination, and last known state outside the scheduler when continuity matters.

## Limits

Credentials and platform-specific trigger details may still require manual or secure reconfiguration after migration.
