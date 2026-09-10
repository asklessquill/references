---
observed_at: 2026-09-10
source_type: chat-derived
source: authority and autonomous execution discussions
status: candidate
confidence: high
topic: instructions versus authority
applicability: agents, protocols, security, workflow design
---

# An instruction does not create authority by itself

## Observation

An agent can receive a syntactically valid instruction asking it to mutate external state even when the sender lacks the relevant authority or the current context no longer permits the action.

## Interpretation

Intent and authority must be represented separately. A prompt, queue message, or task description cannot be treated as sufficient authorization merely because it arrived through a trusted transport.

## Decision relevance

Validate sender context, scope, delegation, freshness, and required approvals before consequential execution.

## Limits

In simple single-user systems, the transport may implicitly encode authority, but that assumption should be explicit and revisited as the system expands.
