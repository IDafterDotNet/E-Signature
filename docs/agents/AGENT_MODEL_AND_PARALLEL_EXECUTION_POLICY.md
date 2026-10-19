# AGENT MODEL & PARALLEL EXECUTION POLICY
**Version:** 1.1 — Owner binding amendment, 2026-10-19  
**Applies to:** E-Signature (`IDafterDotNet/E-Signature`), explicitly approved by Owner; stronger existing project restrictions remain binding.  
**Status:** MANDATORY for every current/future primary agent, developer, test agent, administrator, subagent and reviewer. This is a repository-persisted instruction, not a claim that the agent platform enforces model selection automatically.

## 1. Read-before-work and acknowledgement
Before **every task** (including software installation or tool administration), read this full policy and the project's governing `AGENTS.md`, `CLAUDE.md` if present, architecture, security and decision records. Confirm exact model, Medium thinking, role, task scope, branch/HEAD, worktree status, permission boundaries and any resource coordinator restrictions. The primary agent must pass this policy to every subagent and obtain acknowledgement. Every agent must emit:

`AGENT MODEL POLICY ACKNOWLEDGED — Sonnet 5.5 Medium for code, Haiku 5.5 Medium for testing and approved environment setup, Opus 5.5 Medium only for Owner-authorized exceptional analysis, maximum four concurrent subagents.`

Do not claim to have read an unavailable document. If the specified model/thinking setting is unavailable, **do not silently substitute**; escalate to the Owner. No new permission for actions outside the phase's existing approval.

## 2. Mandatory role-to-model matrix
| Activity | Required model | Thinking | Code changes? |
|---|---|---|---|
| Main phase/workstream Development Agent; new application, test or infrastructure-as-code; production code, migrations, refactors, component development, bug fixes | **Claude Sonnet 5.5** | **Medium** | Only when separately authorized |
| Build, bUnit, integration tests, test logs/evidence | **Claude Haiku 5.5** | **Medium** | No |
| Playwright, screenshots, visual observations, browser logs | **Claude Haiku 5.5** | **Medium** | No |
| Comparison of test results, summaries, reports, defect reproduction | **Claude Haiku 5.5** | **Medium** | No |
| **Development/test toolchain installation and environment setup** (newly authorized) | **Claude Haiku 5.5** | **Medium** | No application/test/repo source code |
| Repeated flaky-test root cause analysis | **Claude Sonnet 5.5** | **Medium** | Analysis; fixes only through an authorized Sonnet developer |
| Complex Core architecture/defect analysis | **Claude Sonnet 5.5** | **Medium** | Same |
| Independent security/permissions review | **Claude Sonnet 5.5** | **Medium** | Review, no automatic security waiver |
| Final quality review and integration engineering | **Claude Sonnet 5.5** | **Medium** | Integration only with explicit Git authorization |
| Exceptional blocked problem, after a documented failed Sonnet 5.5 Medium attempt | **Claude Opus 5.5** | **Medium** | **Analysis/recommendation only**, explicit Owner approval required |

**Hard boundaries:** Haiku and Opus must **never author or modify application, test, migration, UI, security or build-script code**. All code implementation and fixes belong to Sonnet 5.5 Medium. Haiku may run approved installer commands, software configuration utilities and machine-local administrative commands solely for the authorized environment-setup scope. Such commands are **not** permission to write project source code or make migrations. Any reusable setup scripts checked into Git count as code and belong to Sonnet.

## 3. Haiku Environment Setup & Toolchain Management — binding Owner amendment
Haiku 5.5 Medium **IS explicitly allowed** to install, configure, verify and maintain **local development/test tooling**, without having to switch model merely because installation or configuration is involved.

Allowed, when required by an authorized work package and permitted by the host's security policy:
- Install/configure approved **.NET SDK, dotnet tools, Node.js/npm, Playwright/browser dependencies, Git clients, Docker and developer tools**.
- Install/configure **dedicated nonproduction PostgreSQL and SQL Server development/test instances**, local services, localhost-only networking, safe capacity settings and connectivity checks.
- Create isolated **local development/test databases, service accounts and minimal-privilege roles** only when the project's existing database-governance rules **specifically authorize provisioning**; use approved naming contracts, separate test credentials and resource limits.
- Prepare machine-local secret stores, environment variables and temporary development/test configuration **without exposing secrets in Git, screenshots, logs or reports**.
- Execute read-only health checks and verify exact versions and services; avoid unnecessary reinstalls.

Forbidden without separate specific Owner/security authorization:
- Any production or real customer database, existing populated/shared business database, destructive database operation, broad/grant-all permissions, firewall exposure/public bind, weakening endpoint/TLS or OS security controls.
- Applying application schema migrations or seed scripts unless a separate project rule explicitly authorizes that exact isolated test activity; Haiku **cannot write or alter migrations**.
- Editing `.cs`, `.razor`, executable tests, `.sql` application migrations, CI scripts, reusable automation scripts, project source or core application configuration in Git. Sonnet owns code changes.
- Recording any passwords, connection strings with credentials, recovery keys or secrets in source control or reports.
- Taking permissions already reserved to the Owner, Security Agent or Integration Agent; this policy does not lift any existing HOLD, admission gate or database restriction.

Before provisioning a database, Haiku must read the project's live DB contract. If a required database name/permission/approval is missing, **pause only that database action** and escalate; continue unrelated safe setup. After installation, record installer/product/version, origin, checksum/signature where applicable, paths, service names, configuration deltas, ports/network bindings, secret-handling method (never the secret), before/after state and connectivity verification. Never silently overwrite existing installations or accounts.

## 4. Subagent concurrency and delegation — absolute cap
One Primary Sonnet 5.5 Medium Agent may have **at most FOUR (4) concurrently active subordinate agents across all child/nested levels**. Count all direct and indirect descendants; nested orchestration does not create additional slots. The Primary Agent is not counted in the four. Track active assignments: slot, agent ID/role, exact model/thinking, branch/worktree, scope, state, report/evidence, closure confirmation. A slot is free only after the previous agent has delivered work and has actually been closed/terminated; a response alone does not prove termination. Queue other tasks. The host/orchestrator must enforce the count using actual runtime metadata; documentation cannot enforce it automatically. This per-Primary limit does **not** override a tighter cross-project hardware/resource limit.

## 5. Tests, review, release and Git authority
**Sonnet developer → Haiku targeted build/bUnit/integration/Playwright/evidence → Sonnet complex debugging/security/quality review when applicable → Owner acceptance → separately authorized Sonnet Integration Agent.** Haiku is not the final acceptance authority. Build/test success does not grant merge, push, deletion, database production change or security waiver. Prefer focused tests during slices, coordinated Pack/Phase Closure Regression at agreed boundary, full-solution regression at the authorized final gate. Do not hide flakes or warnings; no claiming PASS without executed evidence. Run hardware-heavy operations only through the current Resource Coordinator/available capacity rules.

## 6. Opus restricted escalation
Opus 5.5 Medium is **never** the principal programmer. The Owner must specifically authorize the **narrow** exceptional analysis after Sonnet 5.5 Medium attempts fail. Document reproducer, risk, approaches attempted, results and bounded question. Opus supplies recommendations only; **Sonnet** implements any code, **Haiku** runs independent tests.

## 7. Preserve stronger project-specific governance
All project-specific binding gates remain intact, including identity of Git commits, Waffary asset licensing/G-ASSET, isolated database RULE 04, no unapproved push/merge/rebase/branch cleanup, security clearance, resource admission and Owner decisions. A broad tool-installation authorization is **not** a waiver for database schema changes or admin privileges outside the explicitly authorized development/test environment. If policies conflict, do not silently choose: report the exact conflict and request a scoped Owner decision.

## 8. Repository persistence and verification
The authoritative file is `docs/agents/AGENT_MODEL_AND_PARALLEL_EXECUTION_POLICY.md`. All agent entry points must link to it: `AGENTS.md`, `CLAUDE.md` if present, README/onboarding when present, subagent brief instructions. The Primary Agent must check it is read *for each new assignment* and pass it to subagents. Any future model-policy change requires a recorded Owner decision, linked updates and consistency review; do not change policy to suit a task. Automated document checks may validate references but cannot prove actual model, runtime subagent count or Owner authorization.

**Required final report:** repo/branch/HEAD, model and acknowledgement, exact commands and actions, installs/versions/configuration, DB authorization basis, resource readiness, evidence and pass/fail/not-run, modified files, any warnings/blockers, Git state. Link every created Markdown report with a clickable repo-relative/GitHub path, not only a local drive path.
