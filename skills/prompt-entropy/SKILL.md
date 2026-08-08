---
name: prompt-entropy
description: Write, rewrite, review, or compress prompts for direct model use, reusable templates, delegated tasks, or prompt-bearing parts of skills and agent workflows. Use when wording must preserve intent, constraints, authority, context access, and verification while improving clarity or information density. Exclude requests to execute only the underlying task.
---

# Prompt Entropy

Treat the prompt or prompt-bearing text as the primary artifact. Do not substitute execution of the underlying task for writing it unless the user requests both.

Maximize actionable information per token. Brevity is a budget, not the goal: each retained phrase should change a decision, search path, authority, output, or verification.

## Match the prompt surface

Treat standalone prompts, delegated handoffs, reusable templates, skill instructions, default prompts, and workflow steps as different prompt surfaces. Preserve each host artifact's packaging and invocation mechanics; optimize the language that controls model behavior.

## Preserve meaning first

Before rewriting or compressing an existing prompt, extract an invariant ledger:

- **Outcome**: the required result, decision, or artifact.
- **Scope and authority**: what the recipient may inspect, change, send, approve, or delegate.
- **Hard constraints**: conditions whose violation would make the result unacceptable, incompatible, unsafe, or unauthorized.
- **Epistemic state**: facts, hypotheses, uncertainty, and evidence sources.
- **Acceptance**: required checks, completion criteria, and output shape.
- **Corrective rules**: safeguards added after a real failure or review finding.

Preserve every invariant. Remove only preferences that do not change acceptability. Never cap the number of constraints.

Treat repeated corrective rules as evidence, not clutter. Merge equivalent wording, but retain the protection unless the failure no longer applies.

## Model the recipient

Identify the target model and the context it will actually receive. Assume fresh context unless shared state is explicit.

- Use pointers only when the recipient can access the same environment and will load the named material.
- For a remote agent, web model, isolated subthread, or different workspace, include the minimum payload that preserves invariants.
- Leave stable rules in project instructions only when the recipient will load them. Otherwise carry the necessary rule in the prompt.

Prefer precise pointers for shared access and minimal self-contained payloads otherwise.

## Workflow

1. Recover the target model, prompt surface, outcome, artifact, authority, invariants, accessible context, and verification.
2. Separate facts from hypotheses and user decisions from agent discretion.
3. Ask only questions that would change the deliverable, authority, or acceptance criteria.
4. Keep details that reduce consequential uncertainty; cut those that merely sound thorough.
5. Compose the shortest prompt or instruction that preserves the ledger and enough accessible context to act.
6. Run the loss, access, and completion tests before returning it.

## Compress without over-specifying

Lead with the outcome. Add context, output shape, boundaries, and process only when they change the result or risk.

Use direct verbs, concrete nouns, exact anchors, and checkable predicates. Let the recipient choose; specify a solution only when decided or required for compatibility.

Improve articulation, not ambition. Do not add goals, risk domains, deliverables, or authority that the source prompt does not support.

Consolidate duplicate meaning, but first decide whether repetition carries emphasis, a separate branch, or a failure-derived safeguard.

Use the smallest clear structure. A one-line edit may need only a change and check; consequential work may need staged control.

## Match control to risk

- For a small, obvious change, state the change and its check.
- For investigation, state the question, symptoms, evidence, and accessible anchors.
- For ambiguous or consequential work, request exploration and a reviewable plan before edits.
- For verifiable work, name the feedback tool and iterate to an observable success criterion.
- For externally visible, destructive, or permission-expanding action, preserve any explicit authorization. If authorization is absent or ambiguous, stop at a draft, plan, or approval gate.

Do not add planning ceremony to simple work or replace a feedback loop with a long implementation recipe.

## Loss, access, and completion tests

Delete each sentence in turn. Restore it if its absence could alter the outcome, scope, authority, search, output, corrective protection, or verification.

Then check:

- Can this recipient access every pointer and cheaply discover omitted details?
- Are facts, hypotheses, hard constraints, and discretionary preferences still distinguishable?
- Are required artifacts, approval boundaries, and acceptance criteria unambiguous?
- Is completion observable rather than merely asserted?
- Is the prompt compact enough that its priority is obvious?

If overloaded, split the work into a plan or stages instead of erasing invariants.

## Evaluate honestly

A lower token count proves only that the prompt is shorter. Do not claim better performance without comparative evaluation of correctness, constraint retention, task completion, and verification quality.

## Output

Return the prompt in the form where it will be used. For a standalone prompt, return one copy-ready prompt in a fenced code block. For a skill, template, or agent document, edit or return the prompt-bearing text in its native structure. Prefer a compact paragraph; use bullets when independent constraints would otherwise blur together.

If execution was also requested, separate the drafted prompt from subsequent execution. Add explanation only when requested or when one brief note prevents likely misuse.
