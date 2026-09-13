---
observed_at: 2026-09-13
source_type: chat-derived
source: Human correction during World SE / 桃多郎 Knowledge Architecture discussion
status: candidate
confidence: high
topic: One action, one code block for Human-facing execution handoff
applicability: ChatGPT Program Controller behavior, Human-facing command/code delivery, execution prompts, shell/PowerShell/terminal instructions
---

# One action should be delivered as one code block

## Observation

The Human explicitly corrected a recurring presentation failure: when one executable action requires multiple related commands or text fragments, the AI must not split that single action across multiple code snippets.

Splitting one action into several code blocks increases Human relay and creates avoidable ambiguity about:

- execution order;
- whether blocks are alternatives or cumulative;
- whether omitted context must be reconstructed between blocks;
- where one action ends and the next begins;
- what should be copied and executed as a unit.

## Interpretation

For Human-facing executable guidance, the default rule is:

> **One action = one code block.**

If one bounded action requires several commands, comments, variables, or steps, place the complete runnable material for that action in a single code block whenever technically possible.

Do not drip-feed one action as multiple snippets and later addenda.

This rule concerns presentation and handoff completeness. It does not require unrelated actions to be collapsed into one block.

When multiple genuinely separate actions are required, each action may receive its own complete code block, provided the separation reflects a real execution boundary rather than formatting convenience.

## Decision relevance

This rule is useful when ChatGPT or another Program Controller prepares:

- PowerShell or shell commands;
- setup or recovery instructions;
- repo maintenance commands;
- build/run/test sequences;
- copy-pasteable configuration or prompt payloads;
- any Human-executed bounded action.

The goal is to reduce Human reconstruction, missed commands, and accidental partial execution.

## Regression case

Given a Human request that requires one bounded executable action containing several commands:

- PASS: the AI provides one complete code block containing the full action in correct execution order;
- FAIL: the AI splits the same action across multiple code blocks, requiring the Human to combine them manually;
- PASS: the AI uses separate code blocks only when there are genuinely separate actions or mutually exclusive alternatives.

## Limits

This is a Human-specified interaction rule recorded as reusable reference knowledge. It does not override STOP, HUMAN_GATE, authority, safety, or tool constraints.

If the platform or language makes a single block technically unsafe or misleading, the AI should preserve the one-action boundary and explain the minimum necessary exception rather than silently fragmenting the action.
