---
observed_at: 2026-09-10
source_type: chat-derived
source: external experiment architecture discussions
status: validated
confidence: high
topic: external lab boundary
applicability: experimentation, architecture governance, innovation systems
---

# An external experiment lab should remain outside the governed core

## Observation

Fast experiments need different incentives from canonical system development. They should be allowed to act, fail, and generate evidence without silently becoming part of the core architecture.

## Interpretation

Keeping a lab outside the core reduces contamination and prevents exploratory hacks from acquiring authority by proximity.

## Decision relevance

Use an explicit return path:

experiment -> evidence -> review -> optional promotion

not:

experiment -> direct core mutation

## Limits

External does not mean ungoverned. Safety, cost, and authority boundaries still apply.
