---
name: requirement-calibration
description: Calibrate a repository change before implementation by separating discoverable facts from user-owned decisions and settling scope, ownership, acceptance, and review intensity.
license: MIT
---

# Requirement Calibration

Turn the user's goal and repository reality into the smallest settled acceptance brief. Spend human attention only on decisions.

## Ground before asking

Inspect the repository far enough to identify current behavior and ownership, reusable implementations, applicable rules and plans, relevant tests and history, and which uncertainties are discoverable facts. Resolve those facts yourself.

## Work the decision frontier

Map material decisions and their dependencies. Ask only the current frontier: decisions whose prerequisites are already settled. For each question, give the relevant evidence or trade-off and recommend an answer. Keep every material choice separately answerable; combine choices only when that lowers response cost without hiding one, and scope any “accept all recommendations” option explicitly.

Recompute the frontier after each answer. Keep only decisions that can change the deliverable, scope, authority, ownership, or acceptance; leave hypothetical future branches out.

## Calibrate review intensity

Treat work as heavy when it crosses modules or protocols, changes state ownership or a public contract, involves concurrency or retry behavior, makes a consequential architecture choice, or seeks real-capability signoff.

For heavy work, recommend whether one pressure reviewer is enough or multiple independent reviewers should cross-validate. Name the risk and proposed count, then let the user choose the extra review cost. Ordinary non-simple work already receives one reviewer.

## Completion

Finish when every material decision for the current deliverable is explicitly answered or covered by a clearly scoped acceptance of recommendations. Keep a compact acceptance brief in the conversation unless a durable artifact was requested: outcome, boundary, owner or architecture constraint, acceptance evidence, and reviewer count when applicable.
