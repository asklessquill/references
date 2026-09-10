---
observed_at: 2026-09-10
source_type: chat-derived
source: external capability hub exploration discussions
status: candidate
confidence: high
topic: capability discovery before implementation
applicability: agent architecture, build-buy-borrow-reuse, platform engineering
---

# Discover available capabilities before deciding to build

## Observation

AI systems can waste effort reimplementing connectors, extraction, automation, or hosted capabilities that already exist through APIs, plugins, MCP servers, marketplaces, or managed services.

## Interpretation

Capability discovery should be an explicit step before implementation, not an informal afterthought.

## Decision relevance

For each need, search for reusable capabilities and compare Build / Buy / Borrow / Reuse on semantics, authority, reliability, cost, lock-in, observability, and recovery.

## Limits

Available third-party capability does not imply acceptable trust or fit; discovery precedes evaluation rather than replacing it.
