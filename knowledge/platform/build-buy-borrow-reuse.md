---
observed_at: 2026-09-10
source_type: chat-derived
source: capability hub and platform selection discussions
status: candidate
confidence: high
topic: build buy borrow reuse
applicability: platform architecture, capability acquisition, AI systems
---

# Capability acquisition should be a routing decision

## Observation
Systems often default to building new integrations even when an existing product, API, connector, agent platform, or reusable internal component already provides enough capability.

## Interpretation
Capability acquisition is itself a routing problem: Build, Buy, Borrow, or Reuse.

## Decision relevance
Before implementing a new capability, compare:
- semantic fit
- authority and security fit
- portability and lock-in
- implementation time
- operating cost
- observability
- replaceability
- learning value

## Limits
The cheapest option is not always best. Strategic control, privacy, latency, or experimentation may justify building.
