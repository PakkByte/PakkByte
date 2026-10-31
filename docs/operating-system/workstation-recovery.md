# Workstation recovery

The four computers are interchangeable workstations. None is the master copy, archive, or required source of truth. GitHub is the place to resume work.

## Start from a clone or Codespace

1. Find the canonical GitHub repository and read its README and contribution or development instructions.
2. Use a fresh local clone in a deliberate workspace, or open a Codespace when the local environment is missing, inconsistent, or expensive to reproduce.
3. Confirm the expected default branch and inspect open Issues, Project views, and pull requests.
4. Pull the latest remote state before making changes.

Example local startup:

```text
git clone <repository-url>
cd <repository>
git switch <default-branch>
git pull --ff-only
```

Do not copy an old workstation folder as the recovery method. A copied folder can be useful for forensic comparison, but it is not the canonical project state.

## Begin a work session

- Select an existing Issue or create one that describes the outcome.
- Create a branch for meaningful changes.
- Recreate local-only configuration from the repository instructions, environment secrets, or an approved secret manager.
- Confirm that local configuration files containing secrets are ignored and are not staged.

## Switch computers safely

Before switching:

1. Save work in coherent commits.
2. Run the smallest relevant local checks.
3. Push the branch to GitHub.
4. Open or update the pull request when review or shared verification is needed.
5. Record blockers or the next action in the linked GitHub Issue.

On the next computer:

1. Clone the repository if it is not present, or fetch and pull the existing clone.
2. Check out the same branch.
3. Recreate local-only configuration from documented instructions or environment secrets.
4. Continue from the GitHub branch, Issue, and pull request state.

Never leave meaningful work only in an uncommitted working tree when another computer may need to continue it.

## Local-only configuration recovery

Local-only configuration includes items such as ignored environment files, developer-specific settings, local caches, credentials, and machine-specific paths. Do not commit or paste their values into GitHub, Notion, Issues, pull requests, logs, or documentation.

Document the **shape** of required configuration: variable names, safe example values, permissions, and setup commands. Keep real values in environment secrets or an approved secret manager. If a clean machine cannot be configured without a private value, retrieve it through that approved channel rather than recovering it from an old folder.

## Clean-machine verification

A repository is recoverable when a clean clone or Codespace can:

- identify its purpose from the README;
- install or start using documented steps;
- recreate required local-only configuration without committed secrets;
- run the documented smallest verification checks; and
- resume the active Issue or pull request without an undocumented local archive.

When a clean-machine check fails, record the missing instruction or dependency in the repository Issue and update the README or setup documentation.

## Related guides

- [Repository conventions](./repository-conventions.md)
- [Where does this belong?](./where-does-this-belong.md)
