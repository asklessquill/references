---
observed_at: 2026-09-10
source_type: chat-derived
source: multi-model and actor architecture discussions
status: candidate
confidence: high
topic: model provider versus system role
applicability: multi-model systems, agent architecture, portability
---

# A model provider should not define the system role

## Observation

Roles such as research, implementation, operations, review, or reality testing may be fulfilled by different models and product surfaces over time.

## Interpretation

Naming system responsibilities after a current vendor or model couples architecture to a fast-changing implementation choice.

## Decision relevance

Define the role semantically, then route it to the best available model, executor, or surface using evidence. Preserve interfaces so provider changes do not require redefining the system.

## Limits

Provider-specific capabilities can justify specialized adapters or roles at the implementation edge.
