# Repository conventions

These conventions make a PakkByte repository understandable, recoverable, and safe to copy into other projects. They apply to personal repositories and organization or shared repositories.

## Repository purpose

One repository should represent one coherent product, reusable package, or intentionally grouped body of work. The repository name, README, and issue history should make its purpose clear. Do not use a repository as a catch-all archive for unrelated local files.

## README requirements

Every active repository should explain:

1. What the project is for and who it helps.
2. How to install or start it.
3. How to develop locally.
4. How to run the smallest relevant verification checks.
5. How to deploy, publish, or use the resulting artifact when applicable.
6. Where project-specific contribution or security instructions live.

Keep the README focused on the current project. Link to shared operating-system guidance instead of copying a second, conflicting process.

## Branches and commits

- Keep the default branch in a releasable or reviewable state.
- Create a branch for meaningful work; use a short, descriptive name.
- Keep commits coherent and describe the outcome, not only the file names.
- Do not leave the only copy of meaningful work in an uncommitted working tree.
- Push a branch before switching computers or ending a work session when practical.
- Use pull requests for changes that need review, shared verification, or a durable discussion.

## Issues, discussions, projects, and pull requests

- Use an **Issue** for actionable work, a bug, a decision that requires implementation, or an evidence request.
- Use **Discussions** for open-ended ideas and community conversation that are not yet actionable.
- Use a **Project** for an active delivery queue or portfolio view, not as a second archive.
- Keep implementation detail, acceptance criteria, review, and test results with the GitHub Issue and pull request.
- Link related context from Notion when a decision spans repositories; do not create a second detailed task tracker there.

## Generated output and evidence

Keep generated output out of source control unless it is an intentional product or documentation deliverable. Prefer reproducible commands and GitHub Actions for reports, builds, and checks.

When recovery or coordination material must be preserved for auditability, put it in a clearly named private evidence location and identify its verification state. Do not turn frozen evidence into an active task queue.

## Public information boundary

GitHub issues, discussions, pull requests, Pages, and any public repository content must not contain passwords, tokens, credentials, private information, sensitive personal data, or confidential client material. Do not place those items in Notion either. Store credentials in a secret manager or GitHub Actions secrets, and share sensitive material only through an approved private channel.

Before opening an Issue or pull request, remove secrets from text, screenshots, logs, attachments, and copied configuration. If confidential information is needed to continue, describe the constraint without disclosing the value and use a private channel for the details.

## Related guides

- [Workstation recovery](./workstation-recovery.md)
- [Where does this belong?](./where-does-this-belong.md)
