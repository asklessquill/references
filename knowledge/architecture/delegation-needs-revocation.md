---
observed_at: 2026-09-10
source_type: chat-derived
source: authority and recovery design discussions
status: candidate
confidence: high
topic: delegation and revocation
applicability: agent protocols, permissions, autonomous systems
---

# Delegation without revocation is incomplete authority design

## Observation

Autonomous systems often model how authority is granted but not how it expires, is withdrawn, or is invalidated after context changes.

## Interpretation

A delegation becomes dangerous when receivers cannot distinguish active authority from stale authority.

## Decision relevance

Every delegation model should define at least:

- grantor and grantee
- scope
- evidence of grant
- validity period or condition
- revocation path
- behavior when authority cannot be confirmed

Prefer fail-closed behavior for consequential actions.

## Limits

Low-risk advisory tasks may tolerate softer authority models.
