---
name: execute-from-goal
description: Execute non-trivial coding or repository work from a natural-language goal when the current agent must discover an implementation path and carry it through proportionate verification. Use for direct development work; prefer a more specific workflow skill when one clearly fits. Exclude prompt-writing and simple Q&A.
---

# Execute from Goal

Treat the user's request as the task prompt. Do the work; do not rewrite the request into a prompt and stop.

## Workflow

1. Explore the relevant code, docs, tools, and history. Prefer discoverable facts; ask when the answer depends on user-owned intent or a material choice.
2. Form a compact working brief: outcome, scope and authority, anchors, and acceptance checks. Keep it implicit unless surfacing it would resolve a decision or improve coordination.
3. Choose the lightest safe control based on risk, reversibility, and available authorization:
   - For a clear, small, reversible task, act directly and verify.
   - For a scoped non-trivial task, plan briefly when it materially helps, then proceed within the user's authorization.
   - When an unresolved choice materially changes the outcome, scope, permissions, or external impact, recommend a path and ask; otherwise use best judgment.
4. Prefer relevant project patterns. Diverge when the task or evidence justifies it, and explain consequential deviations.
5. Use the strongest proportionate feedback loop available—tests, build, lint, runtime checks, or screenshots. Iterate on failures attributable to the work until the acceptance criteria are met or a real blocker remains. Classify unavailable, flaky, or pre-existing checks and report them without silently expanding scope.
6. Report the outcome, verification evidence, and remaining gaps. Keep code completion, runtime wiring, and real smoke verification distinct.

## Boundaries

- Preserve explicit scope, authorization, user decisions, and unrelated user changes.
- Match the requested mode. A request to analyze, review, or diagnose does not by itself authorize changes; recommend a next action when useful.
- Normal reversible edits within the requested scope generally fit the request. When not already authorized, seek approval before commits, pushes, publication, broad or irreversible deletion, permission or scope expansion, or other external effects.
- Keep execution with the current agent by default; use delegation or parallel work when the user requests it and the environment permits it.
- Let more specific skills govern the workflows they cover; use this skill as the general execution layer.
