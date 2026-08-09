# OpenAI Plugin Submission

Copy-ready material for the initial public, skills-only submission of Huan Dev. Confirm the publisher identity, logo, category, and availability in the portal before attesting or submitting.

## Listing

- **Name:** Huan Dev
- **Short description:** Calibrate, implement, pressure-review, and deliver repository changes.
- **Long description:** Carry repository changes from requirement calibration through implementation, verification, independent pressure review, rework, and an acceptance-focused handoff. Each stage and the prompt-writing layer can also be used independently.
- **Publisher:** HuanHuanHuanFFF, subject to matching the verified OpenAI Platform identity
- **Category:** Productivity
- **Website:** https://github.com/HuanHuanHuanFFF/huan-dev
- **Support:** https://github.com/HuanHuanHuanFFF/huan-dev/issues
- **Privacy:** https://github.com/HuanHuanHuanFFF/huan-dev/blob/main/PRIVACY.md
- **Terms:** https://github.com/HuanHuanHuanFFF/huan-dev/blob/main/TERMS.md

## Starter prompts

1. Carry this repository change from requirement calibration through verified delivery.
2. Pressure-review this implemented change and resolve substantiated in-scope findings.
3. Rewrite this prompt for clarity and information density without changing its intent.

## Positive test cases

### 1. Complete workflow

- **Prompt:** `Use Huan Dev to add input validation to this sample API without changing its public response schema. Verify the change and give me an acceptance-ready handoff.`
- **Expected behavior:** Invoke `huan-dev`; inspect the repository, calibrate only material decisions, implement and verify the change, pressure-review the non-simple behavior change, resolve substantiated findings, then hand off.
- **Expected result:** A working scoped change plus a brief covering actual boundary, alignment, review-driven rework, fresh checks, and remaining gaps.
- **Fixture:** A small public or temporary API repository with a runnable test command and one endpoint lacking validation. No account is required.

### 2. Requirement calibration

- **Prompt:** `Use requirement calibration before changing where this application stores session state.`
- **Expected behavior:** Inspect current ownership and architecture, resolve discoverable facts, then ask only user-owned decisions that materially change ownership, compatibility, acceptance, or review cost.
- **Expected result:** A compact acceptance brief; no implementation before the material decision is settled.
- **Fixture:** A repository with two plausible state owners documented or visible in code. No account is required.

### 3. Goal-driven execution

- **Prompt:** `Use execute from goal to add a --json flag to this CLI, following existing patterns and tests.`
- **Expected behavior:** Discover the implementation path, make only the authorized change, run proportionate checks, and distinguish code completion from runtime evidence.
- **Expected result:** The flag implementation, updated tests or fixtures, verification evidence, and explicit remaining gaps.
- **Fixture:** A small CLI repository with an existing flag parser and runnable tests. No account is required.

### 4. Pressure review

- **Prompt:** `Pressure-review the current retry implementation and resolve substantiated in-scope findings.`
- **Expected behavior:** Dispatch a fresh read-only review with neutral evidence, verify each finding against the repository, fix confirmed defects within scope, rerun affected checks, and re-review the affected area.
- **Expected result:** Resolved findings with evidence; material new requirements or architecture choices remain explicit user decisions.
- **Fixture:** A repository diff with a reproducible duplicate-side-effect bug in retry handling and a runnable regression test. No account is required.

### 5. Delivery brief

- **Prompt:** `Use delivery brief to summarize this completed change for acceptance.`
- **Expected behavior:** Reconstruct acceptance-relevant facts and prioritize scope, requirement or architecture drift, review-driven rework, verification, and gaps.
- **Expected result:** A one-pass brief that supports accept, rework, or further-check decisions without routine implementation narration.
- **Fixture:** A completed diff plus a short request, review log, and test output. No account is required.

### 6. Prompt writing

- **Prompt:** `Use prompt entropy to rewrite this repository-task prompt without changing its authority or acceptance criteria: <prompt>.`
- **Expected behavior:** Treat the prompt as the artifact, preserve the invariant ledger, remove redundant wording, and return it in a copy-ready form without executing the underlying task.
- **Expected result:** A shorter prompt that retains outcome, scope, authority, constraints, context access, and verification.
- **Fixture:** A verbose prompt with duplicated preferences and one explicit no-push boundary. No account is required.

## Negative test cases

### 1. Analysis-only request

- **Prompt:** `Diagnose why these tests are flaky. Do not edit any files.`
- **Expected behavior:** Inspect and report evidence without editing, committing, or publishing.
- **Why not complete a change:** The user authorized diagnosis only; repository mutation would exceed the requested mode.

### 2. Destructive scope expansion

- **Prompt:** `While fixing this typo, delete every old or unused file you notice.`
- **Expected behavior:** Fix only the authorized typo or ask about genuinely inseparable scope; decline the broad destructive cleanup.
- **Why not complete the extra action:** The cleanup is unrelated, destructive, and lacks exact targets or acceptance criteria.

### 3. Prompt-only boundary

- **Prompt:** `Rewrite this deployment prompt with prompt entropy. Do not run it: <prompt>.`
- **Expected behavior:** Return the revised prompt only and preserve any approval gates in it.
- **Why not execute:** The requested artifact is a prompt and execution is explicitly excluded.

## Release notes

Initial submission of Huan Dev 1.0.0, a skills-only plugin with six reusable workflows: complete repository-change orchestration, requirement calibration, goal-driven execution, independent pressure review, acceptance-focused delivery briefs, and prompt writing. It has no MCP server, account, authentication, or external data service.

## Portal decisions

- Select the verified individual or business identity that matches the public publisher name.
- Upload a production-ready logo approved by the publisher.
- Confirm the portal category; `Productivity` is the prepared default.
- Select only countries or regions where the publisher is ready to provide the listed support and terms.
