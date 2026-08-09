---
name: delivery-brief
description: Produce a decision-ready brief after a repository change by reconciling actual scope, material requirement or architecture drift, review-driven rework, verification evidence, and acceptance gaps.
license: MIT
---

# Delivery Brief

Give the user the shortest brief that supports a decision to accept, request rework, or run a remaining real-environment check. Optimize decision value per unit of reading attention, not raw brevity.

## Recover the acceptance ledger

Reconstruct only acceptance-relevant facts from the request, confirmed decisions, implementation, review, and fresh checks:

- intended versus actual change boundary;
- requirement alignment, plus architecture alignment where the change touches or claims ownership, state, public contracts, concurrency, or another architectural boundary;
- pressure-review findings that changed the delivered work, resulting rework, and recheck evidence;
- verification, uncertainty, and remaining user-owned decisions.

When requirement or architecture alignment could change acceptance, compare against a discoverable baseline; report a missing baseline only when that absence prevents the decision. Mention a no-finding review only when proving the review occurred is itself an acceptance condition. Keep confirmed facts, inferences, and unknowns distinct.

## Compose around acceptance

Lead with the outcome and the fact most likely to change acceptance. Expand deviations, review-driven corrections, and evidence gaps; compress satisfied constraints and routine implementation detail. Keep each finding beside its consequence, response, and evidence.

Let the content choose the shape: use one compact paragraph for a linear result, bullets for independent facts, and headings only when they reduce scan cost. Use precise anchors for details the user can inspect cheaply.

## Prune for the reader

Delete a sentence unless removing it could change the user's judgment about scope, requirement or architecture drift, review rework, verification, or the next action. Prefer direct language over dense phrasing that the user must decode. Give exceptions and uncertainty more space than routine success.

## Completion

Finish when the user can decide in one pass whether to accept, request rework, or run another check; every acceptance-changing unknown is explicit; and each material claim is bounded by evidence.
