# GitHub-first operating system design

## Intent

Create one reusable operating system for work across four computers and future projects. GitHub is the execution and delivery system, Notion is the control and context system, and Obsidian is deferred until the core workflow is stable.

The purpose of this phase is consolidation: sort existing work into clear homes, reduce duplicated tracking, and establish rules that make any computer replaceable without losing the source of truth.

## Why this design

The current recovery work proved that files, agents, repositories, archives, and external records can become difficult to reconcile when each tool becomes its own partial system. The new design separates authoritative responsibilities instead of mirroring everything everywhere.

## Chosen approach

### GitHub-first, Notion-indexed, Obsidian-later

- **GitHub is authoritative for execution:** source code, repository history, branches, Issues, Projects, Actions, Codespaces, Packages, Pages, releases, security configuration, and reusable technical assets.
- **Notion is authoritative for context:** project portfolio, GitHub Education benefit inventory, decisions, learning notes, asset links, expiration reminders, and high-level priorities.
- **Four computers are interchangeable workstations:** each computer works from a clone or Codespace. No computer is the master copy.
- **Obsidian is deferred:** it may later hold private notes and long-term thinking, but it does not duplicate GitHub tasks or Notion project status.
- **Recovery artifacts are frozen evidence:** manifests, archives, and reports are preserved in a private GitHub repository and indexed from Notion rather than treated as active work queues.

### Alternatives considered

1. **Notion-first:** easier to view, but task status would split between Notion and GitHub and drift over time.
2. **Full mirroring:** comprehensive but creates two detailed task systems and requires constant synchronization.
3. **Chosen approach:** keeps execution close to the code while preserving a human-readable control panel and leaving room for a future private knowledge layer.

The chosen approach includes a controlled two-way synchronization pilot for project records, Issues, and status. GitHub remains authoritative for implementation details; Notion remains authoritative for portfolio context and cross-project decisions. Synchronization must preserve those boundaries rather than mirror every field.

## Confirmed builder decisions

- **Ownership scope:** design for both the personal PakkByte account and organization/shared repositories from the start.
- **Workstations:** all four computers are interchangeable; none is the master or archive.
- **Information boundary:** GitHub, Notion, and future Obsidian content must remain project-safe. Secrets and sensitive personal data stay outside these systems.
- **Recovery evidence:** the frozen recovery package belongs in a private GitHub repository, with a Notion index and links to the canonical files.
- **Synchronization:** use two-way synchronization for projects, Issues, and status, but prove it on one repository before expanding to all repositories and organizations.
- **GitHub Projects:** use a hybrid model with one portfolio project and repository-level boards only where a distinct workflow is justified.
- **Rollout scope:** inventory and structure all current repositories and projects; use `github-edu-benefits` as the first active proof point.
- **First build outcome:** `github-edu-benefits` is complete when it has a polished dashboard and documentation explaining available benefits and concrete next actions.
- **Existing services:** inspect existing Notion databases and permissions before creating anything; preserve useful structures and avoid duplicate databases.
- **Benefits data:** verify current availability, activation state, and renewal dates during the inventory step rather than assuming an offer is usable.

## Goals

1. Make GitHub the dependable source of truth for all buildable work.
2. Make any of the four computers safe to use, replace, or rebuild.
3. Use GitHub Education benefits through real workflows rather than an inventory of unused offers.
4. Give Notion a useful role without copying every file or task.
5. Preserve recovery evidence without allowing it to dominate active planning.
6. Make it obvious where a new file, decision, task, note, or asset belongs.
7. Support public portfolio work and private project planning without mixing confidential material into public repositories.

## Non-goals

- Uploading every local file or recovery artifact into Notion.
- Making Notion a second GitHub issue tracker.
- Making one computer or local folder the canonical workspace.
- Designing the Obsidian system before the GitHub and Notion boundaries are stable.
- Automatically claiming that an activated benefit, prepared artifact, or passing test proves real-world acceptance.
- Reconstructing or recreating missing historical files from memory.

## Anti-goals

- Do not keep important source code only on one computer.
- Do not use cloud sync folders as the primary Git repository location.
- Do not track the same task in a GitHub Issue and a separate Notion task unless the Notion entry is only a link/index.
- Do not create duplicate copies of source files merely to make them visible in multiple tools.
- Do not treat generated coordination logs as product deliverables without an explicit reason.
- Do not expand two-way synchronization beyond the pilot until conflict handling, ownership boundaries, and failure recovery are demonstrated.

## System boundaries

### GitHub

GitHub owns:

- Repository source and documentation.
- Git history, branches, tags, releases, and pull requests.
- Issues for actionable work, bugs, decisions requiring implementation, and evidence requests.
- GitHub Projects for active work queues and delivery views.
- Actions for tests, linting, scheduled jobs, reports, releases, and controlled automation.
- Codespaces and devcontainers for reproducible cloud development.
- Packages for versioned libraries, containers, and reusable technical outputs.
- Pages for public documentation, dashboards, and demos.
- Dependabot, secret scanning, security advisories, environments, branch rules, and deployment controls.
- GitHub Education benefits used directly in project workflows.

### Notion

Notion owns:

- The project portfolio and project-level status.
- A GitHub Education Benefits Matrix.
- Decisions and rationale that span multiple repositories.
- Learning notes, research summaries, and operating procedures.
- Links to repositories, Issues, Projects, Actions, Pages, Packages, archives, and external evidence.
- Renewal, expiration, and review reminders.
- A small set of next actions that point back to the authoritative GitHub Issue.

Notion does not own:

- The canonical source code.
- The detailed state of implementation tasks.
- The definitive test result or release history.
- Private credentials, tokens, or sensitive exports.

### Each computer

Each computer is a workstation, not an archive:

- Clone repositories into a deliberate local workspace.
- Pull before starting work when practical.
- Create a branch for non-trivial changes.
- Commit coherent work with descriptive messages.
- Push or open a pull request before changing computers.
- Avoid leaving the only copy of work in an uncommitted working tree.
- Use Codespaces when the local environment is missing, inconsistent, or expensive to reproduce.

### Future Obsidian

Obsidian may later own:

- Private thinking and journaling.
- Long-form notes and personal knowledge graphs.
- Local-only material that should not be placed in GitHub or Notion.

Obsidian should link to GitHub and Notion rather than become a third detailed task tracker.

## Reusable workflow

### Starting work

1. Find or create the GitHub repository.
2. Read the repository README and contribution/development instructions.
3. Check GitHub Issues, Project views, and open pull requests.
4. Select or create one Issue describing the outcome.
5. Work from a clone or Codespace.
6. Create a branch for meaningful changes.
7. Keep supporting decisions in the linked Notion project page when they affect multiple repositories.

### During work

1. Keep implementation state in the GitHub Issue and pull request.
2. Use Actions for repeatable checks instead of relying only on local runs.
3. Store reusable scripts and configuration in the repository when they are part of the product workflow.
4. Link evidence from Notion; do not copy source files into Notion.
5. Update the Issue when scope, blockers, or acceptance criteria change.

### Finishing work

1. Run the smallest relevant local checks.
2. Push the branch.
3. Let GitHub Actions provide the shared verification record.
4. Open or update the pull request.
5. Merge only after the repository's checks and review requirements pass.
6. Update the Notion project summary with the resulting GitHub link and decision.
7. Record external acceptance separately if it exists; do not infer it from a merge.

### Switching computers

1. Push or commit the current work before switching whenever possible.
2. On the next computer, pull the repository and check out the same branch.
3. Recreate local-only configuration from documented instructions or environment secrets.
4. Continue from GitHub state, not from an untracked folder copied between computers.

## Repository and project rules

- One repository should represent one coherent product, reusable package, or intentionally grouped body of work.
- Use a clear README with purpose, setup, development, verification, and deployment instructions.
- Keep generated output out of source control unless it is an intentional deliverable.
- Keep recovery or coordination material in a clearly named archive/evidence location when it is needed for auditability.
- Use Issues for work that needs action; use Discussions for open-ended ideas and community conversation.
- Use a GitHub Project for active delivery, not as a second archive.
- Use releases and tags for meaningful public or reusable versions.
- Use Pages for public-facing artifacts that benefit from a stable URL.

## GitHub Education benefits strategy

Each benefit is classified in Notion as one of:

- **Active:** used in a real workflow with a linked repository or service.
- **Planned:** selected for a specific upcoming workflow.
- **Evaluate:** requires a small trial before adoption.
- **Expired/unavailable:** no longer usable or no longer relevant.
- **Not applicable:** intentionally not used, with a reason.

The flagship demonstration should use benefits where they materially improve the workflow, such as Codespaces/devcontainers, Copilot, Actions, Pages, Packages, security tooling, and selected partner services. The goal is not to maximize activation count; it is to maximize useful, repeatable capability.

## Notion control panel

The initial Notion structure should contain:

### Projects

Fields:

- Project name.
- Status: active, planned, paused, complete, archived.
- Primary GitHub repository.
- GitHub Project URL.
- Current milestone or outcome.
- Next action.
- Owner.
- Last reviewed.

### GitHub Education Benefits Matrix

Fields:

- Benefit name.
- GitHub surface or partner.
- Category.
- Status.
- Intended workflow.
- Linked project/repository.
- Activation or expiration date.
- Evidence link.
- Renewal/review date.
- Notes and limitations.

### Decisions

Fields:

- Decision.
- Date.
- Project or repository.
- Context.
- Chosen option.
- Alternatives rejected.
- Revisit date.
- Links.

### Evidence and assets index

Fields:

- Asset name.
- Type: repository, release, dashboard, archive, report, manifest, external proof.
- Canonical location.
- Project.
- Verification status: Verified, Partially verified, Blocked, Missing.
- Hash or version when relevant.
- Last checked.
- Notes.

### Next actions

Reuse the existing Tasks Tracker for human-level priorities, but each actionable item should link to a GitHub Issue when implementation is involved. Create views for:

- Active projects.
- High priority.
- Next seven days.
- Waiting on external evidence.
- Benefits to evaluate.
- Recovery/archive items, kept separate from build work.

## “Where does this belong?” rules

| Item | Canonical home | Notion treatment |
|---|---|---|
| Source code | GitHub repository | Link only |
| Bug or implementation task | GitHub Issue | Link/index if important |
| Pull request or review | GitHub | Link only |
| Test and CI result | GitHub Actions | Link/result summary |
| Public demo or docs | GitHub Pages/repository | Link |
| Reusable package/container | GitHub Packages | Link/version |
| Cross-project decision | Notion Decisions | Link affected repositories |
| Benefit activation/renewal | Notion Benefits Matrix | Link actual workflow |
| Private thinking | Future Obsidian | Link only when useful |
| Recovery archive | Private GitHub evidence repository | Canonical link, hash, and verification state |
| Credentials and tokens | Secret manager/GitHub secrets | Never copy into Notion |

## Rollout order

1. Keep the recovered evidence package frozen.
2. Create the reusable GitHub workflow and repository conventions.
3. Create the Notion control-panel databases and views.
4. Inventory GitHub Education benefits and map each to a real workflow.
5. Apply the system to `github-edu-benefits` as the first active repository.
6. Pilot two-way synchronization on `github-edu-benefits`, including conflict and failure handling.
7. Apply the same structure to `menu_builder` and all remaining current projects.
8. Revisit Obsidian only after the GitHub/Notion workflow has been used long enough to reveal a real need.

## Success criteria

The system is working when:

- Any computer can resume project work from GitHub without searching old local folders.
- Active implementation status is visible in GitHub.
- Notion can answer what projects exist, which benefits are in use, what decisions were made, and what happens next.
- No important task requires manually reconciling two detailed trackers.
- Recovery evidence is preserved but no longer blocks project progress.
- A new project can be added using the same structure without redesigning the system.
