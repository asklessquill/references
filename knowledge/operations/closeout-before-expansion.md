---
observed_at: 2026-09-10
source_type: chat-derived
source: interrupted implementation / closeout discussions
status: candidate
confidence: high
topic: closeout discipline
applicability: AI coding agents, repository operations, milestone management
---

# Closeout is part of the implementation, not paperwork after it

## Observation

Long-running AI implementation tasks can finish the substantive work — code, tests, candidate publication — and still fail operationally if the final checkpoint is not recorded before a quota, crash, or handoff boundary.

Typical stranded state:

```text
implementation complete
        ↓
verification complete
        ↓
candidate pushed
        ↓
final state / receipt not yet committed
        ↓
agent stops
```

## Interpretation

The final state update, remote SHA confirmation, acceptance receipt, and explicit STOP condition should be treated as part of the task's required output, not as optional bookkeeping.

For quota-constrained agents, closeout work should begin before the final few percent of available execution budget.

## Decision relevance

Useful patterns:

- reserve quota/time for closeout;
- publish intermediate trusted checkpoints;
- keep closeout mutations minimal;
- make restart prompts prohibit new implementation when only closeout remains;
- separate `candidate published` from `accepted / canonical`;
- record what was **not** started after STOP.

## Limits

A clean closeout does not replace independent review. It only ensures that completed work can be safely recovered and evaluated later.
