---
observed_at: 2026-09-10
source_type: chat-derived
source: multi-agent responsibility discussions
status: candidate
confidence: high
topic: authority versus supervision
applicability: agent governance, protocol design, organizational architecture
---

# Authority should not be confused with supervision

## Observation

A system can define who is allowed to decide or mutate something without creating a permanent supervisor above every actor.

## Interpretation

Authority is a scoped permission relationship. Supervision is an ongoing control relationship. Treating every authority boundary as supervision creates unnecessary hierarchy and centralization.

## Decision relevance

Describe authority with explicit scope, delegation, revocation, evidence, and expiry. Add supervisors only when continuous oversight is truly part of the responsibility model.

## Limits

Some high-risk systems legitimately require supervision. The principle is to avoid inventing it by default.
