---
name: pressure-review
description: Independently pressure-test an implemented repository change, resolve substantiated in-scope findings, and expose remaining decisions or evidence gaps before acceptance.
---

# Pressure Review

Try to falsify acceptance with fresh, read-only reviewers. Review the work product and evidence, not the implementer's reasoning history.

## Dispatch

Use one independent reviewer for an ordinary non-simple change. For heavy work, use the reviewer count confirmed during requirement calibration; if none was confirmed, recommend a count and ask before incurring extra reviewer cost. Run multiple reviewers in parallel where possible. Give every reviewer the same core acceptance question; different emphases may guide attention, but no reviewer owns an exclusive slice of correctness.

Read [Prompt Entropy](../prompt-entropy/SKILL.md) once before drafting the reviewer handoffs, then dispatch them. Preserve the confirmed outcome and boundary, repository or diff anchors, relevant corrective protections, fresh checks, read-only authority, and the requested deliverable: acceptance-changing findings with evidence and impact. Give reviewers raw artifacts; omit the intended verdict, suspected findings, and implementation reasoning.

Ask reviewers to distinguish substantiated defects or boundary misses, unresolved requirement or architecture choices, evidence gaps, and no blocking finding. Keep facts, hypotheses, and user decisions distinct.

## Resolve

Treat every finding as a claim to verify against repository reality and executed evidence.

1. Fix substantiated problems inside the confirmed intent, rerun affected checks, and re-review the affected scope.
2. Test proposed new requirements or architecture changes for necessity, alternatives, coupling, and scope. Present material choices to the user with a recommendation.
3. With multiple reviewers, merge duplicate findings and surface meaningful disagreements; evidence, not votes, decides.

## Completion

Finish when no substantiated acceptance blocker remains within the agent's authority and every user-owned decision or evidence gap is explicit for handoff.
