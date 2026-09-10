---
observed_at: 2026-09-10
source_type: chat-derived
source: independent review and frozen candidate discussions
status: candidate
confidence: high
topic: scope freeze
applicability: acceptance review, experiments, regulated change control
---

# Freeze scope before generating acceptance evidence

## Observation

If implementation continues while acceptance evidence is being generated, the reviewer and builder may be reasoning about different candidates.

## Interpretation

A frozen candidate gives evidence a stable referent.

## Decision relevance

Before independent review, stop mutation, record the exact candidate identity, define review scope, and prohibit implementation of findings until the review concludes.

## Limits

Continuous delivery systems can use equivalent immutable build artifacts instead of manually frozen branches.
