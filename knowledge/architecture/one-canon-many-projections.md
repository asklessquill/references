---
observed_at: 2026-09-10
source_type: chat-derived
source: dashboard and observatory design discussions
status: candidate
confidence: high
topic: one canon many projections
applicability: dashboards, AI observability, documentation architecture
---

# One canonical state can support multiple projections

## Observation

Humans and AI actors often need different views of the same system: concise narrative for humans, structured evidence and recovery metadata for machines.

## Interpretation

These views should be projections from shared canonical evidence rather than competing sources of truth.

## Decision relevance

Design human-readable dashboards and machine-readable observatories as replaceable views. Make correction and provenance paths point back to canonical artifacts.

## Limits

Some projection-specific annotations may not belong in canon; they should remain clearly identified as view metadata.
