---
observed_at: 2026-09-10
source_type: chat-derived
source: plan comparison and model capability discussions
status: candidate
confidence: high
topic: context versus memory
applicability: model evaluation, prompt design, subscription selection
---

# Context and memory are different resources

## Observation

AI products may market larger context and stronger memory together even though they solve different problems.

## Interpretation

Context is how much information can participate in one reasoning episode. Memory is how information persists or is recovered across episodes. More of one does not guarantee more of the other.

## Decision relevance

When evaluating a model or plan, ask separately:

- how much task context can be reasoned over at once?
- what persists across sessions?
- how is remembered information selected, corrected, and removed?
- what remains external and canonical?

## Limits

Exact implementations are vendor-specific and may change over time.
