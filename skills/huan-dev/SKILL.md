---
name: huan-dev
description: Complete a scoped repository change with lightweight requirement alignment, proportional verification, and independent pressure review for non-simple changes. Use when carrying a development request through implementation, ordinary rework, and an evidence-bounded handoff.
---

# Huan Dev

Deliver one scoped repository change: implement the confirmed intent, verify it proportionately, pressure-review non-simple work, fix ordinary findings, and report only what the evidence supports.

## Flow

1. **Ground.** Treat the user's request as the task. Inspect repository instructions, live state, relevant code, tests, plans, and history far enough to locate existing behavior and its owner. Preserve unrelated user changes.
2. **Clarify when material.** Read [grilling.md](references/grilling.md) when an unresolved user decision could change the outcome, scope, ownership, acceptance, or authority. Also read it for a heavy task so the user can choose whether to add cross-validating reviewers. Let a clear local change proceed without ceremony.
3. **Implement and check.** Follow repository patterns and choose the smallest effective feedback loop. Implement within the confirmed boundary, then run fresh checks proportionate to the claim being made. A reversible candidate inside the authorized outcome may be implemented provisionally and sent to review; ask first when it expands authority, external effects, or irreversible scope.
4. **Pressure-review non-simple work.** A change is simple only when it is local, reversible, introduces no state or public contract, crosses no behavioral boundary, and leaves no material decision open. Otherwise read [review.md](references/review.md) and dispatch at least one independent reviewer after the initial implementation and checks.
5. **Resolve findings.** Verify reviewer claims against repository reality. Fix findings that fall within the confirmed intent, rerun affected checks, and re-review the affected scope. Keep new requirements, architecture choices, and conflicts with prior user decisions visible for the user to decide.
6. **Hand off.** Report the confirmed requirement's implementation, review findings and fixes, checks actually run, remaining evidence gaps, and user-owned decisions. Treat commit, push, and PR actions according to the current request. When real-environment smoke requires the user, prepare the check and leave capability signoff pending until its result is available.

## Completion

Finish when the confirmed change is implemented; every non-simple change has completed its required pressure review; substantiated findings within the agent's authority are resolved; and each completion claim is bounded by fresh evidence or an explicit gap.
