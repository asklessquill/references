---
observed_at: 2026-09-10
source_type: chat-derived
source: autonomous execution and credential separation discussions
status: candidate
confidence: high
topic: credential separation
applicability: agents, security architecture, capability access
---

# Credentials should authorize capabilities, not define actor identity

## Observation

An execution path can accidentally equate possession of a token, service account, or logged-in session with the semantic identity and authority of the actor using it.

## Interpretation

Credentials are implementation evidence for access. Actor identity and delegated responsibility belong to the semantic layer.

## Decision relevance

Separate who the actor is, what responsibility it holds, which authority it has, and which credential implements access to a capability. Rotate or replace credentials without changing role semantics.

## Limits

Authentication systems may legitimately carry identity claims; the principle is to avoid making credential possession the whole authorization model.
