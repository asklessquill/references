---
observed_at: 2026-09-10
source_type: chat-derived
source: AI subscription strategy discussion
status: candidate
confidence: high
topic: baseline versus boost capacity
applicability: AI subscriptions, compute planning, R&D budgeting
---

# Separate baseline capacity from temporary boost capacity

## Observation

AI workloads are often bursty: ordinary planning and maintenance need moderate capacity, while architecture changes, reviews, migrations, or launch periods benefit from temporary high-end models and larger quotas.

## Interpretation

Buying peak capacity as a permanent baseline can waste money, while buying only baseline capacity can create expensive interruptions during bursts.

## Decision relevance

Design a normal operating tier and an explicit boost mode. Make escalation reversible and measure whether each boost produced enough accepted value to justify its premium.

## Limits

Some systems have consistently high utilization and should provision near peak rather than switch frequently.
