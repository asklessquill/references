---
observed_at: 2026-09-10
source_type: chat-derived
source: model and subscription routing discussions
status: candidate
confidence: high
topic: model selection by system outcome
applicability: AI routing, cost control, model benchmarking
---

# Model choice should be judged by system outcome, not benchmark rank

## Observation

A stronger model may improve architecture or review quality while a more diverse model surface may improve routing knowledge. Neither advantage is visible from benchmark scores alone.

## Interpretation

Model selection is a systems problem. The relevant outcome includes decision quality, rework, latency, human intervention, quota pressure, tool breadth, and durable state produced.

## Decision relevance

Record model episodes with both task-level and system-level outcomes. Prefer the model or surface that changes the total loop for the better, not simply the one with the highest isolated capability score.

## Limits

System-level comparisons require repeated episodes and comparable tasks; one impressive run is not enough.
