---
observed_at: 2026-09-10
source_type: chat-derived
source: repeated builder and reviewer prompt design discussions
status: candidate
confidence: high
topic: prompt as handoff contract
applicability: coding agents, reviews, multi-agent workflows
---

# A high-stakes prompt is a handoff contract

## Observation

For autonomous work, prompts do more than describe the task. They define authority, target evidence, prohibited actions, stop conditions, and expected return artifacts.

## Interpretation

Prompt quality affects governance as well as model performance.

## Decision relevance

For consequential tasks, include purpose, fixed target, authority, explicit prohibitions, evidence requirements, acceptance criteria, and STOP conditions. Avoid language that silently grants broader mutation rights than intended.

## Limits

Prompts are not security boundaries. External permissions and runtime controls must enforce consequential restrictions where necessary.
