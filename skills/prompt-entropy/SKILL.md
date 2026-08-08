---
name: prompt-entropy
description: Create, rewrite, or compress prompts for another AI agent, coding agent, or delegated subthread. Use for delegation, prompt refinement, or context reduction while preserving constraints, authority, and verification. Exclude requests to complete only the underlying task.
---

# Prompt Entropy

Draft the handoff prompt first. Do not perform or delegate the underlying task unless the user also requests execution.

Maximize actionable information per token. Brevity is a budget, not the goal: each retained phrase should change a decision, search path, authority, output, or verification.

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

Identify the recipient's access. Assume fresh context unless sharing is explicit.

- Use pointers only when the recipient can access the same environment and will load the named material.
- For a remote agent, web model, isolated subthread, or different workspace, include the minimum payload that preserves invariants.
- Leave stable rules in project instructions only when the recipient will load them. Otherwise carry the necessary rule in the prompt.

Prefer precise pointers for shared access and minimal self-contained payloads otherwise.

## Workflow

1. Recover the recipient, outcome, artifact, authority, invariants, accessible context, and verification.
2. Separate facts from hypotheses and user decisions from agent discretion.
3. Ask only questions that would change the deliverable, authority, or acceptance criteria.
4. Keep details that reduce consequential uncertainty; cut those that merely sound thorough.
5. Compose the shortest prompt that preserves the ledger and enough accessible context to act.
6. Run the loss, access, and completion tests before returning it.

## Compress without over-specifying

Lead with the outcome. Add context, output shape, boundaries, and process only when they change the result or risk.

Use direct verbs, concrete nouns, exact anchors, and checkable predicates. Let the recipient choose; specify a solution only when decided or required for compatibility.

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

Return one copy-ready prompt in a fenced code block. Prefer a compact paragraph; use bullets when independent constraints would otherwise blur together.

If execution was also requested, separate the drafted prompt from subsequent execution. Add explanation only when requested or when one brief note prevents likely misuse.
