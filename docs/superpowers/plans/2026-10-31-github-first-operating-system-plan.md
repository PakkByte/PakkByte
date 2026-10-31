# GitHub-First Operating System Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Establish a reusable GitHub-first operating system across the user's personal and organization work, four interchangeable computers, Notion indexing, and a first polished `github-edu-benefits` deliverable.

**Architecture:** GitHub remains authoritative for source, implementation state, Issues, pull requests, Projects, Actions, and releases. Notion owns portfolio context, decisions, benefit inventory, reminders, and links. A controlled two-way synchronization pilot is proven on `github-edu-benefits` before it is expanded to all current repositories and organizations.

**Tech Stack:** Git, GitHub repositories/Issues/Projects/Actions/Pages, Markdown, YAML, GitHub CLI/API, Notion databases and linked pages, optional Codespaces/devcontainers, Obsidian deferred.

**Spec:** `docs/superpowers/specs/2026-10-31-github-first-operating-system-design.md`

## Global Constraints

- Design for both the personal PakkByte account and organization/shared repositories from the start.
- Treat all four computers as interchangeable workstations; none is the master or archive.
- Keep secrets and sensitive personal data out of GitHub, Notion, and future Obsidian content.
- Preserve frozen recovery evidence in a private GitHub repository and index it from Notion.
- Keep GitHub authoritative for implementation details and Notion authoritative for portfolio context and cross-project decisions.
- Do not expand two-way synchronization beyond the pilot until conflict handling, ownership boundaries, and failure recovery are demonstrated.
- Use a hybrid GitHub Projects model: one portfolio project plus repository-level boards only where justified.
- Inventory all current repositories and projects, using `github-edu-benefits` as the first active proof point.
- `github-edu-benefits` is complete when its dashboard and documentation explain available benefits and concrete next actions.
- Inspect existing Notion databases and permissions before creating anything; preserve useful structures and avoid duplicates.
- Verify benefit availability, activation state, and renewal dates instead of inferring them from an inventory.
- Do not claim external acceptance, uploads, backups, or benefit activation without direct evidence.

## Review Focus

- **Cross-account and organization scope:** repository and project records must not assume a single owner or personal-only access; validate personal and organization repositories separately in the inventory task.
- **Sync conflicts:** simultaneous GitHub and Notion edits must produce an explicit conflict or deterministic ownership result; test this before expanding the pilot.
- **Unavailable or expired benefits:** the benefits dashboard must distinguish current, unavailable, expired, and unverified offers; test with evidence states rather than optimistic defaults.
- **Public/private leakage:** public repository content, issue forms, and Pages output must not expose secrets or sensitive personal data; validate the privacy boundary during repository and dashboard review.
- **Computer replacement:** a fresh workstation must resume from GitHub without copied local folders; validate the documented recovery path from a clean clone or Codespace.

---

### Task 1: Freeze the recovery evidence package

**Files:**
- Create: private GitHub evidence repository selected during execution
- Create: `README.md` in the evidence repository
- Create: `manifests/antigravity-reconciliation.csv`
- Create: `manifests/antigravity-current-sha256.csv`
- Create: `manifests/menu-builder-baseline.json`
- Create: `reports/canonical-antigravity-status.md`
- Create: `reports/antigravity-reconciliation.md`
- Source: session artifacts under `C:\Users\tyler\.copilot\session-state\1ef93b31-64e5-4eda-b743-4a09e4e743ea\files`

**Interfaces:**
- Consumes: the already verified recovery artifacts and SHA-256 values.
- Produces: a private, versioned evidence repository URL, commit SHA, and Notion-ready evidence record.

- [ ] **Step 1: Confirm the destination repository and privacy**

  Use the GitHub account/org scope from the approved design. Confirm the repository is private before uploading any recovery evidence.

- [ ] **Step 2: Copy only the frozen evidence artifacts**

  Preserve filenames, hashes, classifications, and the final `113 Committed / 1 Preserved / 0 Missing` result. Do not copy secrets, raw credentials, or unrelated local output.

- [ ] **Step 3: Add the evidence README**

  Document the recovery scope, source dates, canonical commit references, archive SHA-256, and the rule that evidence is frozen and not an active task queue.

- [ ] **Step 4: Verify the repository**

  Run `gh repo view <owner>/<repo> --json name,isPrivate,defaultBranchRef` and `gh api repos/<owner>/<repo>/commits/<sha>`. Expected: the repository is private and the evidence commit is reachable.

- [ ] **Step 5: Commit**

  Commit the evidence package with message `docs: freeze recovery evidence`.

### Task 2: Establish reusable repository and workstation conventions

**Files:**
- Modify: `README.md`
- Modify: `APPROACH.md`
- Modify: `.github/ISSUE_TEMPLATE/opportunity.yml`
- Create: `docs/operating-system/repository-conventions.md`
- Create: `docs/operating-system/workstation-recovery.md`
- Create: `docs/operating-system/where-does-this-belong.md`

**Interfaces:**
- Consumes: the approved GitHub/Notion boundary rules.
- Produces: contributor-facing rules that can be copied to current repositories without exposing private data.

- [ ] **Step 1: Document the repository operating rules**

  Define repository purpose, README requirements, branch and commit expectations, issue/PR usage, generated-output rules, and the rule that public issues must not contain confidential information.

- [ ] **Step 2: Document the four-computer recovery path**

  Specify clone-or-Codespace startup, pull-before-work, branch creation, push-before-switching, local-only configuration recovery, and clean-machine verification.

- [ ] **Step 3: Document canonical homes**

  Encode the approved “where does this belong?” table for source, tasks, decisions, benefits, evidence, credentials, private thinking, and public demos.

- [ ] **Step 4: Update public entry points**

  Keep the existing public tone and issue form, but link to the safe workflow documentation and preserve the explicit confidentiality warning.

- [ ] **Step 5: Verify the documentation**

  Check all links with a repository-local link scan or manual review. Expected: no public-facing document instructs users to place secrets or sensitive data in GitHub or Notion.

- [ ] **Step 6: Commit**

  Commit with message `docs: define github-first operating system`.

### Task 3: Audit and normalize the Notion control panel

**Files:**
- Create or update: existing Notion project portfolio database
- Create or update: existing Notion GitHub Education Benefits Matrix
- Create or update: existing Notion Decisions database
- Create or update: existing Notion Evidence and Assets index
- Create or update: existing Notion Tasks Tracker views
- Update: Notion recovery hub page

**Interfaces:**
- Consumes: the private evidence repository URL and the approved ownership/privacy boundaries.
- Produces: stable Notion page/database IDs, property definitions, views, and links to canonical GitHub records.

- [ ] **Step 1: Inspect existing databases and permissions**

  List the existing recovery hub, project, task, decision, benefits, and evidence structures before creating anything. Record which structures can be reused and which are missing.

- [ ] **Step 2: Normalize project properties**

  Ensure Projects has name, status, primary repository, GitHub Project URL, current outcome, next action, owner, and last reviewed.

- [ ] **Step 3: Normalize benefits properties**

  Ensure the Benefits Matrix distinguishes Active, Planned, Evaluate, Expired/unavailable, and Not applicable, with workflow, repository, activation/expiration, evidence, renewal, and limitations.

- [ ] **Step 4: Normalize decisions and evidence**

  Ensure Decisions records context, chosen option, rejected alternatives, revisit date, and links. Ensure Evidence records canonical location, verification state, hash/version, and last checked.

- [ ] **Step 5: Add the approved portfolio views**

  Create or preserve views for active projects, high priority, next seven days, external evidence blockers, benefits to evaluate, and recovery/archive items.

- [ ] **Step 6: Verify the control panel**

  Confirm each database has one canonical record for the evidence repository and current projects. Expected: no duplicate database is created when an existing structure is suitable.

### Task 4: Inventory benefits and build the `github-edu-benefits` proof point

**Files:**
- Repository: `PakkByte/github-edu-benefits`
- Modify or create: repository README and dashboard/documentation files identified by the repository's existing structure
- Create or update: repository-level issue for the dashboard outcome
- Create or update: linked Notion benefits and project records

**Interfaces:**
- Consumes: the Notion Benefits Matrix schema and the GitHub-first repository conventions.
- Produces: a polished dashboard/documentation experience, evidence-backed benefit statuses, and concrete next actions.

- [ ] **Step 1: Inventory the repository and current benefit evidence**

  Read the repository instructions, current dashboard structure, open Issues, Actions, and existing documentation. Record each benefit as Active, Planned, Evaluate, Expired/unavailable, or Not applicable only when evidence supports the state.

- [ ] **Step 2: Define the dashboard acceptance criteria**

  The dashboard must explain what each relevant benefit does, whether it is currently usable, which workflow it supports, what evidence exists, and the next action or limitation.

- [ ] **Step 3: Write failing content checks**

  Add the smallest repository-appropriate checks for required sections, benefit status labels, evidence links, and next-action presence. Use the existing test or validation framework; do not add a new framework solely for documentation checks.

- [ ] **Step 4: Implement the dashboard and documentation**

  Update the existing repository structure rather than introducing a parallel product. Keep claims tied to evidence and distinguish verified availability from planned or unverified work.

- [ ] **Step 5: Run the repository checks**

  Run the repository's documented test, lint, build, and link checks, selecting the smallest command that covers the changed surfaces. Expected: all targeted checks pass and the dashboard renders or builds as documented.

- [ ] **Step 6: Commit and link**

  Commit the dashboard/documentation change, push it, and link the commit or pull request from the Notion project and Benefits Matrix records.

### Task 5: Pilot two-way GitHub-to-Notion synchronization

**Files:**
- Create: synchronization design/configuration in the selected automation location
- Create: conflict and failure-handling runbook under `docs/operating-system/synchronization.md`
- Create or update: GitHub Issue tracking the synchronization pilot
- Create or update: Notion project and issue index records

**Interfaces:**
- Consumes: the stable Notion property IDs from Task 3 and the `github-edu-benefits` records from Task 4.
- Produces: a bounded synchronization pilot for projects, Issues, and status with explicit ownership and failure behavior.

- [ ] **Step 1: Define the synchronized field set**

  Specify the exact fields that may flow both ways: repository/project identity, Issue URL/number, high-level status, owner, current outcome, next action, and last reviewed. Keep implementation details, test results, and release history GitHub-owned.

- [ ] **Step 2: Define conflict behavior**

  Write the deterministic rule for simultaneous edits, stale updates, missing records, deleted Issues, permission failures, and rate-limit failures. The system must surface a conflict rather than silently overwrite evidence.

- [ ] **Step 3: Implement the smallest pilot**

  Synchronize only `github-edu-benefits` and only the approved field set. Store credentials in GitHub secrets or the selected secret manager; never place tokens in Notion, source files, or logs.

- [ ] **Step 4: Test normal and failure paths**

  Verify create/update in each direction, a simultaneous edit, a deleted or inaccessible record, an expired credential, and a transient API failure. Expected: successful changes converge; failures are visible and recoverable.

- [ ] **Step 5: Verify auditability**

  Confirm every synchronized record links back to its GitHub Issue or repository and that a human can identify the last successful synchronization and any conflict.

- [ ] **Step 6: Commit the runbook and pilot configuration**

  Commit only non-secret configuration and documentation with message `feat: pilot github notion synchronization`.

### Task 6: Apply the operating system across all current repositories

**Files:**
- Modify: each current repository's README, contribution instructions, issue/project configuration, and workflow documentation where needed
- Create or update: one portfolio GitHub Project
- Create or update: repository-level GitHub Projects only where justified
- Create or update: Notion project records for every current repository
- Create or update: migration/archival records for repositories that should not remain active

**Interfaces:**
- Consumes: the conventions from Task 2, normalized Notion structures from Task 3, and the successful pilot from Task 5.
- Produces: an inventory-backed operating model covering all current repositories without duplicating detailed task systems.

- [ ] **Step 1: Inventory every current repository and project**

  Record owner/org, visibility, default branch, current commit, working-tree state where available, purpose, status, and intended destination in the portfolio.

- [ ] **Step 2: Classify each repository**

  Mark each as active, planned, paused, complete, archived, or needing migration. Do not rename, move, delete, or archive a repository without explicit evidence and approval.

- [ ] **Step 3: Apply repository conventions**

  Add only the documentation, issue, project, or workflow configuration each repository needs. Preserve existing project-specific patterns and avoid unrelated refactors.

- [ ] **Step 4: Populate the portfolio project**

  Add one item per current project with links to the canonical repository, relevant Issues, status, current outcome, and next action.

- [ ] **Step 5: Verify clean-machine recovery**

  Select representative repositories and resume them from a fresh clone or Codespace using only GitHub and the documented local setup. Expected: no copied Antigravity folder or undocumented local archive is required.

- [ ] **Step 6: Record completion and unresolved gaps**

  Mark each repository and project in Notion with Verified, Partially verified, Blocked, or Missing evidence. Keep unresolved external acceptance, upload, backup, or benefits claims explicitly blocked.

## Execution Order

Complete Tasks 1-3 before changing product repositories. Complete Task 4 before Task 5. Complete Task 5 before broad synchronization or Task 6 expansion.

## Out of Scope for This Plan

- Obsidian setup or vault design.
- Automatic migration, renaming, deletion, or archival of repositories without separate approval.
- Uploading sensitive material or credentials.
- Claiming external acceptance, cloud backup, or benefit activation without direct evidence.
