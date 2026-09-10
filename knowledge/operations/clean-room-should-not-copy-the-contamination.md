---
observed_at: 2026-09-10
source_type: chat-derived
source: account and repository contamination recovery discussion
status: candidate
confidence: high
topic: clean-room recovery
applicability: AI memory migration, repository recovery, incident response
---

# A clean room should not ingest the entire contaminated context

## Observation

When an existing AI context or repository is suspected of contamination, copying every chat, memory, file, and inferred assumption into a fresh environment recreates the original uncertainty.

## Interpretation

Clean-room recovery requires selective evidence transfer rather than bulk migration.

## Decision relevance

Seed a fresh actor with trusted principles, fixed artifacts, acceptance evidence, known contamination boundaries, and explicitly uncertain state. Reconstruct from evidence before importing convenience context.

## Limits

Selective transfer can omit important information. Keep the old environment quarantined and available for reference until recovery is accepted.
