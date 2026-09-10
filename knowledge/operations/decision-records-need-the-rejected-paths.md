---
observed_at: 2026-09-10
source_type: chat-derived
source: repeated architecture option and plan selection discussions
status: candidate
confidence: high
topic: decision provenance
applicability: architecture decisions, AI handoff, recovery
---

# Decision records should preserve why alternatives were rejected

## Observation

A future actor can see what was chosen from a final artifact while missing the constraints that ruled out attractive alternatives. It may then reopen settled debates or reintroduce known failure modes.

## Interpretation

Durable decisions need enough negative context to prevent accidental regression.

## Decision relevance

For consequential choices, record the chosen path, key alternatives, decisive evidence, unresolved uncertainty, and conditions that would justify revisiting the decision.

## Limits

Do not turn every routine choice into a long ADR; preserve rejected paths when forgetting them would create meaningful rework or risk.
