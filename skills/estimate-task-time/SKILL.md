---
name: estimate-task-time
description: Estimate AI-agent development duration or remaining time in hours. Use for implementation time estimates, time budgets, or revised ETAs.
license: MIT
---

# Estimate Task Time

Estimate normal execution to the requested acceptance criteria, including likely iteration. Prioritize the right order of magnitude. Estimation uses read-only scoping and the bounded AA lookup; resume implementation after the report only when it is already authorized.

## 1. Scope the actual work

Map the requested change, reusable implementations, affected boundaries and required validation/review from the conversation and focused repository inspection. Stop when these are identified, or name the unresolved parts. Size adaptation of existing work separately from new exploration; keep optional roadmap work and extra polish outside the estimate.

For remaining-time requests, size only unfinished work; report elapsed time separately when relevant.

Set the target model to the user's specified development model, otherwise the current session's model and settings, without asking them to choose. Resolve its variant, reasoning effort and agent environment from supplied context or available session settings. Keep missing details unknown; neither an agent product name nor a family label such as “GPT-6” identifies a variant. Do not transfer current-session settings to a different requested model. If the target variant remains unknown, skip the unmatched lookup and use the provisional-estimate path below.

## 2. Look up AA runtime within 60 seconds

Use [AA Coding Agents](https://artificialanalysis.ai/agents/coding-agents), **Execution Time / Time per Task**, and its [methodology](https://artificialanalysis.ai/methodology/coding-agents-benchmarking). AA comparison pages can expose model variants more clearly than the overview.

- Start a 60-second elapsed-time deadline before the first lookup, covering searches, page reads and retries. Bound requests by the remaining time where supported. Stop at a useful reference or the deadline; cancel outstanding retrieval where supported and make no further requests after the deadline. Disclose any unavoidable tool overrun.
- Prefer a direct page; allow at most one targeted AA search. Reuse recently checked evidence from this task when its model, timing definition and provenance are clear.
- Find the **same model**, preferring matching effort and agent environment. Use a recent relevant result and disclose setting mismatches. A different model or fallback mixture does not establish the target model's runtime.
- Accept measured **agent wall time**. Some AA evaluation pages also call output-tokens divided by generation speed “Time per Task”; this decode-time estimate excludes waiting and overhead and is not an equivalent metric.
- Retain the duration/unit, model/settings, benchmark or mixed suite, published date when available, and URL. Release and retrieval dates are not run dates. Separate completed work from early exits/timeouts when possible; otherwise label the aggregate as attempt runtime.

If no usable same-model runtime is available within the budget, estimate provisionally from the scoped execution path and disclose the missing AA reference. Keep retrieval within AA and existing tools; do not install anything.

## 3. Adapt the reference to this task

Sketch the shortest ordinary path that meets the scope, without executing it: related code, tests, wiring and required documentation may form one batch, followed by necessary checks and likely feedback. Estimate coherent batches and serial feedback cycles, not a separate allowance for every named phase. Preserve required validation.

Compare reuse, scope and exploration with the reference workload. Keep normal progress in the central estimate and named setbacks in the range or conditional additions.

Prefer relevant benchmark/task runtime when available; a mixed-suite mean is only a scale check, not a similarly sized task measurement. Explain substantial adjustments through scope and execution evidence, rather than file counts, generic risk percentages or fixed minutes per round. Anchor to agent execution rather than human workdays.

Count concrete slow steps such as builds, tests and integration probes, adding only overhead absent from the reference. Separate user/external waits from execution. For authorized parallel work, use the dependency path and integration time, not total work divided by agent count. A user budget is not the predicted duration.

An hour-scale estimate needs a short time account identifying substantial serial work or actual waits, with observed durations distinguished from judgment. Phase labels alone are not timing evidence; familiar reusable changes may take minutes. Without AA or observed execution, label the duration provisional instead of inventing stage budgets. If investigation or unresolved design prevents bounding completion, estimate the next evidence-producing milestone and leave the whole-task duration uncertain.

## 4. Report and revise

Lead with **approximately X hours** and a plausible range, using coarse precision; short tasks may also include minutes. Add the main scope reason, largest uncertainty and the hour-scale time account when needed. Mark the task estimate as an inference, distinct from AA's measured runtime.

In a brief source note, link the AA evidence, disclose setting mismatches or mixed-suite scope, and state matched/reused/skipped/unavailable plus elapsed lookup seconds when queried. Keep the response to a few sentences focused on duration, without score, token, cost comparisons or uncalibrated probability labels.

Revise **remaining** time when observed speed, check results or scope changes the forecast; preserve the original estimate and explain the change. Treat “too slow” feedback as a reason to audit scope and timing evidence, not apply an arbitrary discount. An estimate-only request ends with the report.
