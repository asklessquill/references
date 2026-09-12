---
observed_at: 2026-09-12
source_type: chat-derived
source: ChatGPT conversation examining Program Controller quality, AI agreement bias, problem-framing drift, durability of behavioral improvements, bounded anticipatory continuation, unstable model routing, execution-context omissions, and Human-complementarity limits
status: candidate
confidence: medium
topic: Program Controller quality and durable AI improvement
applicability: AI program control, long-running agent coordination, governance, fresh-session recovery, regression testing of reasoning behavior, human-interface workflow design, model routing, prompt compilation, repo-local execution handoff
---

# Program Controller quality needs durable evidence, not verbal intent

## Observation

A recurring failure pattern appeared during a long-running system-design conversation:

- the AI answered the question that was explicitly asked, but did not always identify the more important upstream question;
- the AI tended to optimize inside the structure already presented instead of first questioning whether that structure itself should be changed;
- when the Human proposed a correction, the AI sometimes accepted it too quickly instead of independently testing it against prior decisions, alternatives, and counterarguments;
- after identifying a failure, the AI could explain the cause but still fail to propose a durable improvement mechanism unless prompted again;
- after completing an obvious prerequisite, the AI could name the next step without supplying the concrete artifact required to perform that step, forcing the Human to ask again;
- after being corrected about that continuation failure and recording a durable lesson, the AI repeated the same class of error by again ending with “the next thing is to generate the prompt” instead of actually generating it;
- model/tier recommendations changed materially across adjacent turns — `GPT-6 Ultra` → `GPT-6 ExtraHigh` → `GPT-6 High` — because the AI reasoned from conversational impressions before consulting the durable routing/prompting source that already existed;
- after the Human explicitly asked whether Dango prompt design was being followed, inspection showed that Dango already defined a prompt-compilation order, phase-splitting rules, model/tier routing logic, and an Ultra-specific prompt rule that should have constrained the recommendation from the start;
- even after producing a phase-bounded execution prompt, the AI omitted execution coordinates that had been requested in prior work: whether to continue or split the thread, the exact repository, the exact local working directory, and the exact branch/ref to use;
- behavioral promises such as “I will check this next time” are volatile if they exist only in conversation state or account-local instructions.

A useful reasoning ladder emerged:

```text
-1  discover what problem should actually be solved
 0  question the framing, assumptions, and option set
 1  decide what should be done
 2  determine how to execute it
```

The observed weakness was not mainly at `1 -> 2`; it was the tendency to skip `-1` and `0` when the conversation already supplied a plausible frame, and to stop too narrowly at the literal completion boundary instead of anticipating the immediate continuation that the established workflow already implied.

A second useful distinction emerged around **bounded lookahead**:

```text
bad underreach:
complete prerequisite -> mention next action -> wait for Human to ask for the obvious artifact

useful lookahead:
complete prerequisite -> provide the immediately required next artifact -> anticipate one further likely dependency or checkpoint

bad overreach:
expand four or more downstream stages at once -> increase noise, cognitive load, and premature commitment
```

The conversation also distinguished three different persistence layers:

```text
account-level custom instruction
  = startup/bootstrap aid for a particular account or environment

reference knowledge
  = durable, reusable lessons that should survive account/model/runtime changes

project canonical policy / authority
  = formally adopted rules that actually govern execution
```

These layers are complementary. A custom instruction can improve startup behavior, but it is not sufficient evidence that a quality improvement is durable across accounts, actors, models, or future sessions.

## Interpretation

For a Program Controller role, “improvement” should not be accepted merely because the model can restate a lesson after being corrected.

A more credible improvement claim requires durable artifacts and reproducible evidence. A practical minimum is:

1. **Durable rule** — the expected behavior is written in a non-volatile store.
2. **Regression case** — the failure is abstracted into a test case that can recur without relying on the original conversation.
3. **Fresh-actor reproduction** — another session/model/actor, given only the durable material, can produce the expected behavior.

This is especially important for failures involving framing, agreement bias, continuation planning, model routing, and execution handoff, because a model can appear improved inside the same conversation merely by echoing the Human's latest correction.

The durable rule should not merely say “think more broadly.” It should create observable expectations such as:

- important decisions should test whether the presented problem framing is itself correct;
- Human proposals, prior AI proposals, and existing architecture should all remain open to challenge;
- at least one outside-the-frame alternative should be considered when the decision is structurally important;
- detecting a failure should normally lead to cause, generalization, prevention mechanism, and a way to test the prevention mechanism;
- when a workflow has an obvious immediate continuation and no Human decision is required, the controller should provide the concrete next artifact or action rather than merely naming it;
- look ahead far enough to reduce unnecessary Human relay, normally one to two downstream steps, but stop before distant speculative stages create clutter or premature commitment;
- when executable shell/code work is needed for one bounded phase, prefer one complete runnable block over drip-feeding small snippets and later addenda;
- STOP, HUMAN_GATE, unresolved authority, or a real decision boundary override anticipatory continuation;
- when a durable routing/prompting authority exists for the system, model/tier and prompt-shape recommendations should be derived from that authority before conversational intuition;
- important model-routing recommendations should be based on task shape, fixed evidence, authority boundaries, phase split, cost/quota risk and STOP — not on a generic rule such as “important task -> Ultra”;
- before handing an execution prompt to another actor, decide whether the work should continue in the current thread or start in a fresh thread, and state that decision explicitly;
- repo-bound prompts should state the exact repository identity, local working directory when known, branch/ref, fixed base or target SHA when relevant, and whether mutation is permitted;
- if any execution coordinate is unknown, do not silently infer it: make discovery of that coordinate part of the bounded phase or ask for the minimum Human decision;
- if repeated correction plus durable notes still does not reliably change behavior, the weakness should be represented as a **Human-complementarity boundary** rather than as a solved capability.

Useful regression cases include:

> After a deterministic evidence-acquisition phase completes and the established plan says the next phase is a model review requiring a specific prompt, does the controller provide that prompt in the same response without requiring the Human to ask again? Does it also identify the next checkpoint after review, while avoiding an unnecessary multi-stage roadmap beyond that?

> When a project has an existing canonical routing/prompt compiler, does the controller consult it before recommending a model/tier and prompt shape? Does the recommendation remain stable unless newly recovered evidence changes the task classification?

> Before handing off a repo-bound task, does the controller explicitly state thread reuse/split, repository, local working directory, branch/ref, fixed SHA if relevant, mutation mode, and STOP? If any of these are unknown, is that uncertainty surfaced rather than guessed?

> After the controller records a lesson about a failure, can a fresh actor reproduce the improved behavior without the Human restating the same criticism? If not, the lesson is evidence of awareness, not evidence of capability improvement.

## Execution-context completeness

A prompt can be semantically correct yet operationally incomplete. For repo/tool work, the handoff should normally include a compact execution coordinate block before the task body:

```text
Thread:
  continue current | start fresh
  reason: <why continuity or isolation is required>

Repository:
  <owner/repo>

Local working directory:
  <exact path if known>

Branch / ref:
  <exact branch, tag, or detached fixed SHA>

Fixed target / base:
  <SHA/blob/tag if the phase depends on an immutable target>

Mutation mode:
  read-only | write-authorized

Evidence input:
  <exact attached file / path / receipt if required>

STOP:
  <explicit phase boundary>
```

This is not clerical decoration. Missing coordinates create several failure modes:

- the actor may operate in the wrong clone or stale worktree;
- a branch name can be inferred incorrectly from a fixed SHA;
- a read-only audit can accidentally run on a mutable implementation branch;
- old thread context can contaminate an intentionally fresh independent review;
- a fresh thread can lose necessary bounded context when continuity was actually required;
- the Human is forced to reconstruct execution state and relay it manually.

The controller should therefore treat **thread topology and execution coordinates as part of prompt compilation**, not as afterthoughts.

For read-only exact-target review, a fresh thread is often preferable when independence or contamination resistance matters, while the repository/ref can remain fixed without creating a new branch. For mutation phases, the prompt should explicitly state whether to work on an existing branch or create/use a designated task branch; never infer a write branch from the repository name alone.

## Human-complementarity boundary

The conversation produced a stronger conclusion than “the AI should try harder.” Repeated failures persisted across explicit correction, durable note creation, and immediate re-application attempts.

Therefore, for the observed model/session class, the following functions should not be assumed reliable enough to delegate without independent Human or durable-system checks:

- final `-1 / 0` problem-framing judgment for high-leverage program decisions;
- final model/tier routing when a canonical router exists but has not been mechanically consulted;
- deciding how far ahead the program should be expanded when continuation, cognitive load and authority boundaries interact;
- treating a self-reported behavioral correction as evidence that the controller is now dependable.

This does not imply that AI cannot contribute strongly to these functions. It means the system should distinguish **AI analysis capability** from **proven Program Controller reliability**.

A safer current role decomposition is:

```text
Human / externally enforced durable controls
  -> final high-leverage framing, authority, routing acceptance, and controller-quality judgment

AI Program Analyst / Execution Designer
  -> recover evidence, decompose fixed tasks, compare options, compile bounded prompts,
     inspect diffs, detect contradictions, and prepare exact execution/review artifacts
```

A future model or product tier may narrow this boundary, but that should be demonstrated empirically rather than assumed from nominal model capability.

## Decision relevance

This knowledge can affect decisions about:

- whether an AI is ready to serve as a Program Controller rather than only a task executor or Program Analyst;
- whether a behavior should live in account custom instructions, a reusable knowledge base, or project canon;
- how to evaluate claims that an AI behavior has “improved”;
- how to design regression tests for agreement bias, framing lock-in, failure to discover upstream problems, failure to anticipate obvious continuation, unstable model routing, and incomplete repo execution handoff;
- how much downstream planning should be surfaced to a Human before it becomes counterproductive;
- how to reduce Human relay and copy/paste overhead without allowing the AI to cross real authority or decision boundaries;
- when a canonical routing/prompting source should be consulted mechanically before model recommendations are accepted;
- how thread isolation, local worktree selection, branch/ref selection, and fixed-target binding should be represented in prompts;
- when Human involvement is a design requirement rather than a temporary workaround.

A useful acceptance rule for future Program Controller improvements is:

> Do not treat a conversational promise, self-critique, or newly written lesson as evidence of improvement. Prefer durable rules plus regression cases plus fresh-actor reproduction.

A useful interaction rule is:

> Anticipate the immediate continuation of an established workflow and provide the artifact needed to perform it. Usually look one to two steps ahead; do not flood the Human with distant stages. Authority and genuine Human decisions remain hard boundaries.

A useful routing rule is:

> If a durable project-specific routing/prompt compiler exists, consult it before recommending model/tier or prompt shape. A changed recommendation should be traceable to changed evidence or task classification, not merely to conversational reconsideration.

A useful execution-handoff rule is:

> A repo-bound execution prompt is incomplete until thread topology, repository, local working directory, branch/ref, fixed target when relevant, mutation mode, required evidence, and STOP are explicit or intentionally marked unknown.

## Limits

This is a single conversation-derived observation and is therefore retained as `candidate`, not validated truth.

It does not prove that every model or agent will exhibit the same failure pattern, nor that the `-1 -> 0 -> 1 -> 2` ladder or one-to-two-step lookahead is universally optimal.

The appropriate lookahead depth depends on task reversibility, authority, uncertainty, and Human preference. A bounded continuation rule must not be used to bypass STOP, HUMAN_GATE, budget, external-effect, or explicit approval boundaries.

Thread isolation is not universally superior to continuity. The correct choice depends on whether the phase requires independence, contamination resistance, cache/context continuity, or recovery from durable state.

The Human-complementarity boundary above is an empirical boundary for the observed interaction/model behavior, not a universal statement that future models cannot perform Program Control reliably.

It does not itself create project authority. If a project wants to require these behaviors or enforce these boundaries, the relevant canonical system must explicitly adopt them.

It also does not imply that custom instructions are useless. They may be valuable as account-local bootstraps; the point is only that they should not be the sole persistence mechanism for system-critical controller quality.
