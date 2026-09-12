---
observed_at: 2026-09-12
source_type: chat-derived
source: Human feedback during World SE prompt handoff design
status: candidate
confidence: medium
topic: Human-facing cognitive load in AI program control
applicability: AI program control, prompt handoff, technical project communication, Human-AI interface design
---

# Human-facing output should preserve abstraction level and minimize relay cost

## Observation

A technically correct AI-facing execution prompt was judged acceptable, while the surrounding Human-facing explanation was judged unnecessarily difficult to read.

The main causes were:

- excessive use of English terms in otherwise Japanese Human-facing prose;
- repeated use of repository paths, filenames, branch names and implementation labels when they were not needed for the Human decision;
- exposing internal classification and routing detail outside the execution prompt even though that detail was primarily useful to the next AI actor;
- restating low-level evidence names instead of summarizing their meaning at the Human's working abstraction level.

The result was higher cognitive cost even though the underlying technical content was correct.

This exposes an important interface distinction:

```text
AI-facing artifact
  -> exact, explicit, operational, low ambiguity

Human-facing explanation
  -> compressed, semantic, decision-oriented, low cognitive load
```

The two should not be written at the same granularity.

## Interpretation

Program Control quality includes not only correctness of the task plan, but also the cost imposed on the Human to understand and operate it.

A controller should normally translate low-level execution detail into higher-level Human meaning before presenting it. Exact paths, filenames, SHAs, branches and technical labels belong inside the execution artifact unless the Human must inspect, choose, verify or act on them directly.

A useful rule is:

> Keep AI-facing prompts operationally exact, but keep surrounding Human-facing prose at the Human's abstraction level.

For Japanese Human-facing communication, prefer Japanese descriptions over English labels when precision is not lost. Preserve established proper nouns and technical terms only when they materially aid identification or decision-making.

For example, instead of enumerating several repository files in prose, prefer a semantic summary such as:

> 現在の入口文書3点だけを整理し、正本や受入済み設計そのものは変更しません。

The exact filenames can remain inside the AI execution prompt.

This is not merely stylistic. Excessive low-level detail increases:

- reading time;
- context switching;
- copy/paste burden;
- risk that the Human must reconstruct which details actually matter;
- probability that implementation mechanics distract from the real decision.

## Human-facing compression rules

When reporting or handing off a bounded technical phase:

- lead with the current state, meaning, next action and genuine Human decision;
- use repository/file/branch/SHA details only when the Human must verify or manipulate them;
- keep detailed execution coordinates inside the AI-facing prompt or drill-down section;
- avoid mixing Japanese explanation with unnecessary English process terminology;
- translate implementation-level categories into semantic Human language where possible;
- do not repeat the same low-level facts both before and after an execution prompt;
- if no Human decision is required, say so directly rather than presenting implementation details as if they were choices;
- preserve exactness for the downstream AI without making the Human consume that exactness unnecessarily.

## Regression case

> Given a technically dense repo-bound execution prompt, does the controller keep the prompt exact while summarizing the surrounding explanation in a few Human-scale sentences? Are filenames, paths, branch names, SHAs and English process labels omitted from Human-facing prose unless they materially affect a Human decision?

A failure occurs when the Human must parse implementation coordinates or internal AI vocabulary merely to understand what is happening next.

## Decision relevance

This knowledge is relevant when deciding:

- how much technical detail should appear outside an AI execution prompt;
- whether a controller is actually reducing Human relay and cognitive load;
- how Human-facing status reports should differ from machine-facing task contracts;
- how to design reusable prompt wrappers, dashboards and progress reports;
- whether a communication artifact is technically correct but operationally expensive for the Human.

A useful acceptance rule is:

> Human-facing output is not complete merely because it is accurate. It should also minimize the amount of low-level project structure the Human must mentally reconstruct.

## Limits

This is a conversation-derived observation and remains `candidate`.

Some Humans may prefer direct exposure to filenames, branches or implementation detail, and some tasks require such detail for safety or verification. The rule is therefore not "hide technical detail"; it is "surface technical detail when it changes the Human's understanding, action or decision."

This entry does not change project authority or execution policy by itself.
