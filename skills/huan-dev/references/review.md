# Pressure Review

Use a fresh, read-only subthread to look for concrete reasons the implemented change should not yet be accepted. Review the work product, not the implementer's reasoning history.

## Choose the reviewers

- Use one independent reviewer for an ordinary non-simple change.
- Use the reviewer count confirmed during grilling for heavy work, and run them in parallel where possible.
- For cross-validation, give every reviewer the same core acceptance question. Different emphases may guide attention, but no reviewer owns an exclusive slice of correctness.

## Build a compact review prompt

Give the reviewer the shortest self-contained handoff that preserves:

- **Outcome:** the confirmed behavior and what acceptance means.
- **Scope and authority:** the repository location, baseline or diff range, and read-only constraint.
- **Anchors:** applicable repository instructions, relevant code paths, tests, and fresh check results that the reviewer can access.
- **Corrective protections:** known ownership boundaries, existing capability to reuse, and any failure-derived constraint relevant to this change.
- **Deliverable:** actionable findings that could block acceptance, each with an evidence anchor and impact.

Ask the reviewer to distinguish:

- a substantiated defect or missed boundary;
- an unconfirmed requirement or architecture choice;
- an evidence gap;
- no blocking finding.

Keep facts, hypotheses, and user decisions distinct. Omit generic praise, long checklists, and implementation instructions that do not change the verdict.

## Resolve the review

1. Verify every finding against the repository and executed evidence; reviewer confidence is not proof.
2. Fix substantiated problems inside the confirmed intent, rerun affected checks, and re-review the affected scope.
3. Pressure-test proposed new requirements or architecture changes for necessity, alternatives, coupling, and scope. Present material choices to the user with a recommendation rather than silently accepting them.
4. For multiple reviewers, merge duplicate findings and surface meaningful disagreements; reviewer votes do not replace evidence.

Finish when no substantiated acceptance blocker remains within the agent's authority and every user-owned decision or evidence gap is explicit for handoff.
