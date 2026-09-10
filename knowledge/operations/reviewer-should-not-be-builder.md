---
observed_at: 2026-09-10
source_type: chat-derived
source: independent acceptance review discussions
status: validated
confidence: high
topic: reviewer independence
applicability: AI code review, acceptance, governance
---

# A reviewer should not silently become the builder

## Observation

When the same agent that evaluates a candidate also edits it, review evidence becomes entangled with implementation decisions.

## Interpretation

Independent acceptance is strongest when the reviewer has no authority to repair, redesign, promote, or expand the candidate during the review.

## Decision relevance

For high-value acceptance reviews, explicitly prohibit mutation and require findings against a fixed candidate. Implement findings in a separate authorized step.

## Limits

Exploratory review-and-fix loops can be efficient during development; they should simply not be mislabeled as independent acceptance.
