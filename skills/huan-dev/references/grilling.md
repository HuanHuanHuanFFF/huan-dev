# Requirement Grilling

Use this branch only when a material user decision remains or when a heavy task needs a review-intensity decision.

## Establish facts first

Inspect the repository before questioning the user. Search by behavior and domain concept, not only by names. Identify:

- the current behavior and the module or boundary that owns it;
- existing implementations that could be reused or extended;
- applicable repository rules, plans, tests, and relevant history;
- which uncertainties are discoverable facts and which are user-owned decisions.

Facts are the agent's job. Ask the user only about decisions that can change the deliverable, authority, or acceptance.

## Work the decision tree

Map the task as a design tree. The **frontier** is every decision whose prerequisites are already settled. Ask the current frontier in rounds; defer questions that depend on an unanswered decision.

For each question, state the decision, the relevant evidence or trade-off, and a recommended answer:

```text
❓ Q1 — <decision>: <question and compact options>

➡️ <recommended answer and why>
```

Recompute the frontier after each answer. Keep the tree bounded to decisions that can affect this change; leave hypothetical future branches out.

## Choose review intensity for heavy work

A task is heavy when it crosses modules or protocols, changes state ownership or a public contract, involves concurrency/retry behavior, makes a consequential architecture choice, or seeks a real capability signoff.

For heavy work, include this decision in the grilling frontier:

- recommend whether one reviewer is enough or multiple independent reviewers should cross-validate the change;
- name the risk that justifies the added reviewers and the proposed count;
- let the user choose the extra review cost.

One pressure reviewer is already required for ordinary non-simple work; ask only whether to add cross-validation.

## Exit

Finish when every material decision for the current deliverable is settled. Keep the resulting brief in the conversation unless a durable artifact was requested: outcome, boundary, owner, acceptance, and reviewer count when applicable.
