---
observed_at: 2026-09-10
source_type: chat-derived
source: design acceptance and production promotion discussions
status: validated
confidence: high
topic: acceptance scope
applicability: reviews, governance, releases, agent systems
---

# Acceptance must state what it does not accept

## Observation

A PASS on architecture can be misread later as approval of implementation, deployment, production authority, or broader program state.

## Interpretation

Acceptance is scoped evidence, not a universal quality stamp.

## Decision relevance

Every acceptance record should identify the reviewed artifact, frozen version, dimensions reviewed, findings, and explicit non-claims such as no production promotion, no runtime proof, or no next-phase authorization.

## Limits

For tiny low-risk changes, the scope may be obvious; explicit non-claims become more important as autonomous systems and multiple reviewers are involved.
