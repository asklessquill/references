---
observed_at: 2026-09-10
source_type: chat-derived
source: contamination and correction discussions
status: candidate
confidence: medium
topic: correction propagation
applicability: knowledge systems, architecture recovery, incident response
---

# Correcting a source is not enough when downstream artifacts inherited it

## Observation

An incorrect assumption can be copied into prompts, designs, tests, summaries, routing rules, and agent instructions before the original source is corrected.

## Interpretation

A semantic correction has a blast radius just like a code defect.

## Decision relevance

When correcting consequential knowledge, identify likely consumers, versions, derived artifacts, and persistent agent configurations. Revalidate or supersede affected outputs instead of assuming source correction propagates automatically.

## Limits

Full dependency tracking may be impractical; prioritize downstream artifacts that carry authority or repeated execution.
