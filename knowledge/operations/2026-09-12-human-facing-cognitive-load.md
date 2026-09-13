---
observed_at: 2026-09-12
source_type: chat-derived
source: Human feedback during World SE prompt handoff design, with follow-up correction on 2026-09-13
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

A follow-up correction exposed a stricter requirement: a sentence can still be too internal even when it is short. If a first-time reader cannot tell what an internal term means, what is about to happen, and what is not about to happen, the communication has failed at the Human interface.

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

A second rule is:

> Human-facing wording should be understandable on first read without requiring prior knowledge of the project's internal vocabulary.

This means internal names may still be used when they are useful, but their meaning must be carried by the sentence itself. Prefer plain descriptions of the real-world meaning and action over unexplained phase names, architecture labels, abbreviations, repository jargon, or internal shorthand.

For Japanese Human-facing communication, prefer Japanese descriptions over English labels when precision is not lost. Preserve established proper nouns and technical terms only when they materially aid identification or decision-making.

For example, instead of enumerating several repository files in prose, prefer a semantic summary such as:

> 現在の入口文書3点だけを整理し、正本や受入済み設計そのものは変更しません。

Likewise, instead of saying only that the system will proceed to an internally named phase, explain the concrete meaning first, such as:

> 次は、開発の出発点として何をこのMacへ持ってくるべきかを確認します。まだダウンロードや開発は始めません。

The exact filenames and internal labels can remain inside the AI execution prompt or a drill-down section.

This is not merely stylistic. Excessive low-level detail or unexplained internal vocabulary increases:

- reading time;
- context switching;
- copy/paste burden;
- risk that the Human must reconstruct which details actually matter;
- probability that implementation mechanics distract from the real decision;
- risk that a status sentence is technically correct but incomprehensible to someone who did not follow the preceding project history.

## Human-facing compression rules

When reporting or handing off a bounded technical phase:

- lead with the current state, meaning, next action and genuine Human decision;
- write so that a first-time reader can understand the sentence without reconstructing project history;
- explain what an internal term means before relying on the term itself;
- prefer concrete action descriptions such as `確認する`, `持ってくる`, `変更しない`, `まだ開始しない` over unexplained internal phase names;
- use repository/file/branch/SHA details only when the Human must verify or manipulate them;
- keep detailed execution coordinates inside the AI-facing prompt or drill-down section;
- avoid mixing Japanese explanation with unnecessary English process terminology;
- translate implementation-level categories into semantic Human language where possible;
- do not repeat the same low-level facts both before and after an execution prompt;
- if no Human decision is required, say so directly rather than presenting implementation details as if they were choices;
- preserve exactness for the downstream AI without making the Human consume that exactness unnecessarily.

## Regression cases

> Given a technically dense repo-bound execution prompt, does the controller keep the prompt exact while summarizing the surrounding explanation in a few Human-scale sentences? Are filenames, paths, branch names, SHAs and English process labels omitted from Human-facing prose unless they materially affect a Human decision?

> Given a sentence containing an internal project term, could a person seeing that sentence for the first time understand what is happening next and what is not happening yet? If not, rewrite the sentence in plain language before presenting it.

A failure occurs when the Human must parse implementation coordinates, internal AI vocabulary, or prior project-specific terminology merely to understand what is happening next.

## Decision relevance

This knowledge is relevant when deciding:

- how much technical detail should appear outside an AI execution prompt;
- whether a controller is actually reducing Human relay and cognitive load;
- how Human-facing status reports should differ from machine-facing task contracts;
- how to design reusable prompt wrappers, dashboards and progress reports;
- whether a communication artifact is technically correct but operationally expensive for the Human;
- whether project-specific vocabulary is helping identification or merely shifting interpretation work onto the Human.

Useful acceptance rules are:

> Human-facing output is not complete merely because it is accurate. It should also minimize the amount of low-level project structure the Human must mentally reconstruct.

> A Human-facing sentence should remain understandable when read in isolation by someone who does not already know the project's internal terminology.

## Limits

This is a conversation-derived observation and remains `candidate`.

Some Humans may prefer direct exposure to filenames, branches or implementation detail, and some tasks require such detail for safety or verification. The rule is therefore not "hide technical detail"; it is "surface technical detail when it changes the Human's understanding, action or decision."

Established proper nouns and project names can remain useful navigation anchors. The requirement is not to remove them, but to avoid making comprehension depend on already knowing what they mean.

This entry does not change project authority or execution policy by itself.
