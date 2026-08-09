---
name: huan-dev
description: Orchestrate a scoped repository change through requirement calibration, goal-driven implementation, proportional verification, independent pressure review, ordinary rework, and an evidence-bounded handoff. Use when the user explicitly requests the complete Huan Dev workflow.
license: MIT
---

# Huan Dev

Carry one authorized repository change from goal to acceptance. This skill owns orchestration; the linked skills own their stages.

## Flow

1. **Ground.** Treat the user's request as the task. Inspect repository instructions, live state, relevant code, tests, plans, and history far enough to locate current behavior and its owner. Preserve unrelated user changes.
2. **Calibrate.** When a user-owned decision could change the outcome, scope, ownership, acceptance, or authority—or heavy work needs a review-intensity decision—read [Requirement Calibration](../requirement-calibration/SKILL.md). Continue when the current acceptance brief is settled.
3. **Execute.** Read [Execute from Goal](../execute-from-goal/SKILL.md) and use it as the implementation layer through fresh verification. The confirmed brief and this workflow are more specific; continue through review and handoff before finishing.
4. **Pressure-review.** A change is simple only when it is local, reversible, introduces no state or public contract, crosses no ownership or behavioral boundary, involves no concurrency or retry behavior, and leaves no material decision open. Otherwise read [Pressure Review](../pressure-review/SKILL.md) and complete its review-resolution loop.
5. **Hand off.** Read [Delivery Brief](../delivery-brief/SKILL.md) when the task was pressure-reviewed or any scope, requirement, architecture, rework, uncertainty, or evidence gap could change acceptance. For a simple aligned change, report only the outcome and fresh checks. Treat commit, push, and PR actions according to the current request.

## Completion

Finish when the confirmed change is implemented; required pressure review is resolved within the agent's authority; remaining user-owned decisions and evidence gaps are explicit; and the handoff supports an acceptance decision.
