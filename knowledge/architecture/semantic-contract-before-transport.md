---
observed_at: 2026-09-10
source_type: chat-derived
source: cross-runtime protocol design discussions
status: candidate
confidence: high
topic: semantic contract
applicability: protocols, agent interoperability, distributed applications
---

# Define the semantic contract before choosing the transport

## Observation

Systems often begin integration design with queues, webhooks, APIs, or workflow engines before clarifying what the participants mean by requests, offers, authority, evidence, completion, and refusal.

## Interpretation

Transport can move bytes without preserving responsibility or meaning. Interoperability requires a semantic contract that survives transport substitution.

## Decision relevance

Define participants, responsibilities, exchanged artifacts, authority context, evidence, lifecycle, refusal, and recovery semantics first. Then map them onto HTTP, Git, queues, MCP, or other transports.

## Limits

Transport characteristics can impose important constraints and should feed back into implementation design after semantics are clear.
