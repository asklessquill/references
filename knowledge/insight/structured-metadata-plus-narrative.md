---
observed_at: 2026-09-10
source_type: chat-derived
source: reference knowledge-base design discussion
status: candidate
confidence: high
topic: knowledge representation
applicability: AI-readable repositories, research evidence, routing data
---

# Durable knowledge benefits from structured metadata plus narrative meaning

## Observation

Pure prose preserves nuance but is hard to filter or route over. Pure structured records are easy to query but often lose reasoning, caveats, and context.

## Interpretation

A lightweight combination supports both machine selection and human understanding.

## Decision relevance

Store stable metadata such as date, source type, status, confidence, topic, and applicability, then preserve observation, interpretation, decision relevance, and limits in prose.

## Limits

Schemas should remain lightweight enough that contributors continue using them.
