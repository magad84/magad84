# Cross-Project Codex Operating Policy

Use [Universal Autonomous Delivery & Conditional Release Policy v1.0](docs/GLOBAL_AUTONOMOUS_DELIVERY_POLICY.md) as the baseline for all work in this repository and as the reusable template for other Owner projects.

## Core default

- One bounded Owner-approved work package; autonomous routine implementation, troubleshooting, tests, review and evidence capture.
- A **single explicitly scoped** prior authorization may include PR merge and conditional Production deployment; never require duplicate approval per routine stage once that authority and all gates are satisfied.
- If merge or Production deployment is **not explicitly** in scope, stop at reviewed release-ready PR/artifacts. Green CI is not permission to deploy.
- Respect existing project-specific HOLD, privacy/security rules, data-protection gates and branch protection.
- Final check: reviewed source and immutable artifacts, security/CI, backup/restore and rollback for stateful changes, actual Production verification where applicable. Stop safely on failure.
- One concise receipt with evidence and genuinely necessary next decisions; no invented PASS, no repeated completed tests without material change.
