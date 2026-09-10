---
observed_at: 2026-09-10
source_type: chat-derived
source: adaptive routing and failure analysis discussions
status: candidate
confidence: high
topic: failure lessons in routing
applicability: adaptive agents, model routing, incident learning
---

# Failure lessons are routing data, not just postmortem text

## Observation

A failed route contains information about model fit, tool limitations, environment assumptions, quota risk, authority problems, and recovery cost.

## Interpretation

If failure evidence is stored only as narrative, future routing cannot reliably use it.

## Decision relevance

Capture failed episodes with task features, chosen route, failure mode, detected cause, rework, rollback, human intervention, and whether the lesson still applies. Let future selectors use negative evidence explicitly.

## Limits

Do not overfit to one failure; distinguish systemic limitations from transient outages or prompt defects.
