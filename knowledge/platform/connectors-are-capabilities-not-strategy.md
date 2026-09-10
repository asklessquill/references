---
observed_at: 2026-09-10
source_type: chat-derived
source: productivity-suite connector discussion
status: validated
confidence: high
topic: connectors versus strategy
applicability: AI platforms, enterprise integrations, agent architecture
---

# Connectors are capabilities, not strategy

## Observation

A platform may advertise connections to mail, calendars, documents, code hosts, and chat systems. Those connections do not by themselves define what an actor should do with them.

## Interpretation

Connector availability answers "can the system access this surface?" Responsibility answers "why should it access it and what outcome should follow?"

## Decision relevance

Evaluate connectors by whether they reduce implementation cost for an already-defined responsibility. Do not redesign actor identity around whatever connector a vendor happens to offer.

## Limits

A connector can still be strategically important when it unlocks a previously impossible capability or materially changes build-versus-borrow economics.
