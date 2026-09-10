---
observed_at: 2026-09-10
source_type: chat-derived
source: workspace agent and contamination risk discussion
status: candidate
confidence: high
topic: progressive agent authority
applicability: workspace agents, autonomous operations, safety
---

# Agent permissions should grow only after evidence

## Observation

A newly configured agent may have strong reasoning and broad tool access before its assumptions, prompts, and knowledge sources have been validated in operation.

## Interpretation

Capability should be staged independently from authority. Start with observation, then narrow read-only work, then reviewed proposals, and only later consequential writes.

## Decision relevance

Promote agent authority based on demonstrated behavior, provenance quality, failure handling, and rollback evidence rather than model reputation alone.

## Limits

Low-consequence sandboxes can use broader permissions earlier when effects are contained.
