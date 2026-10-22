# Universal Owner-Approved Autonomous Delivery & Conditional Release Policy

**Version:** 1.0 — 22 October 2026  
**Scope:** Reusable operating standard for the Owner's engineering/automation projects.  
**Authority:** Owner explicitly approved adopting this as a general policy. This document is a workflow standard, **not** a blanket authorization for any particular merge, Production release, expense, live-data change, or paused project.

## 1. Goal

Reduce unproductive cycles of "implement → test → report → stop → seek another routine approval." Deliver one bounded unit from diagnosis to a verifiable end state, while preserving security and project-specific release authority.

**Preferred flow:** Scope and permissions → reuse existing evidence → minimal implementation → focused tests → final risk-based gates → independent review → build immutable artifacts → merge and deploy **only when the same explicitly approved scope includes those actions** → live verification → rollback if required → one concise receipt.

## 2. One authorization per bounded delivery package

A single **explicit project/task-specific Owner authorization** may prospectively cover implementation, PR merge, and conditional Production deployment **together**. If it does, do not ask for repetitive per-step approval, provided the stated scope and every normal gate continue to hold.

The authorization should identify: project and change, branch/PR or source selection method, target environment/services, whether merge is permitted, whether Production deployment/restart is permitted, affected data/providers, preflight/backup/rollback gates, and no-go conditions. Exact candidate SHA/digest may be finalized after testing as long as provenance and final review are verified and the approval expressly permits that controlled selection.

**Default when missing or ambiguous:** autonomous isolated development, test, review and PR preparation are allowed within the task; **merge and Production deployment are not inferred**. A green test run does not supply missing release authority.

This policy does not retroactively authorize older PRs, historical maintenance windows, unfinished phase transitions, or customer-data actions; obtain the applicable explicit authority for those. Existing task-specific restrictions continue to apply until the Owner expressly supersedes them.

## 3. Work autonomously, avoid repetition

- Read the latest Owner instructions and **current** project state first; inspect only code/evidence that matters to the task.
- Reuse verified successful tests, reviews, images and artifacts when their **exact source/configuration** is unchanged. Retest affected code and execute required final release gates, not unrelated suites by habit.
- Fix routine isolated implementation/test-harness problems without repeated approval; do not weaken assertions, forge evidence, or bypass security/tool denials.
- Use one coherent issue/work package, one well-scoped PR per independently releasable component when appropriate, and one final outcome report.
- Protect uncommitted WIP, backups and checkpoints. A usage cap or paused session is not permission to discard work or claim a future background completion.

## 4. Conditional release gates

Even when preauthorized, merge and release proceed **only if all applicable checks pass**:

1. Exact reviewed source, branch ancestry, peer review, normal branch protection and CI checks PASS.
2. Immutable deployable artifact/source provenance and target-architecture/runtime verification PASS.
3. Relevant security/privacy, role/tenant/isolation, compatibility, regression and integration checks PASS.
4. Fresh target-environment preflight; monitored maintenance/rollout window where needed; protected backup and **tested restore** for stateful changes.
5. Executable rollback proven for the exact service/data compatibility; retained safe prior image/source; no irreversible or unexplained state transition.
6. Post-deploy health, logs, smoke/end-to-end checks and agreed acceptance evidence PASS, with rollback on failed live gates.

**STOP / NO-GO** if review/security/CI fails; privileges are absent; scope expands; data, tenant, audit, queues or schema drift is unexplained; live state is uncertain; rollback is unavailable; an authorization/consent is missing; or a required provider/test account cannot be safely used. Preserve evidence and request **one consolidated decision** for a genuine blocker.

## 5. Protected/high-risk operations are not silently preauthorized

Require applicable explicit authority, and any additional consent or change control, for: real customer/personal/financial/health data writes, messaging or external provider sends and charges, database migrations or irreversible changes, authentication/entitlements/billing, security architecture, credential handling, production infrastructure/restarts, publication of legal terms, GPS surveillance/retention, or regulated/safety-critical actions.

Never collect or publish secrets, bypass a platform security gate, assume access to protected roles, fabricate end-to-end evidence, replay real queues, or turn on delivery flags merely because tests passed.

Project-specific **HOLD / freeze / no-release** orders prevail; adopting this general policy does not lift them. A higher-risk project may require stricter approval, independent validation and staged rollout.

## 6. Reporting and truthfulness

Label outcomes separately: **IMPLEMENTED**, **TESTED**, **RELEASE-READY**, **DEPLOYED**, **PRODUCTION-VERIFIED/ACCEPTED**, and (if relevant) **COMMERCIALLY READY**. A technical correction cannot guarantee Google or another third party's independent indexing/approval decisions.

Final receipt, compactly: exact change and evidence links, relevant test/CI results, reviewed source and immutable artifacts, whether merge/deploy actually occurred, observed Production result, rollback status, unresolved external blockers, and the smallest remaining Owner decisions.

**Policy precedence:** latest explicit Owner decision and regulatory/security constraints → project-specific holds, release controls and product rules → this cross-project default → historical guidance. Apply this policy in each repository's current instructions; a document in one repository does not automatically configure other tools, projects or installed agents.
