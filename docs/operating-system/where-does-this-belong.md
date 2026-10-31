# Where does this belong?

Use the table below to keep one authoritative home for each kind of information. Links and short summaries may point between systems, but detailed copies should not drift.

| Item | Canonical home | What to keep there | Notion treatment |
|---|---|---|---|
| Source code | GitHub repository | Product code, repository documentation, and project configuration | Link only |
| Bug or implementation task | GitHub Issue | Outcome, acceptance criteria, scope, blockers, and implementation discussion | Link or index when useful |
| Pull request or review | GitHub | Diff, review comments, checks, and merge history | Link only |
| Test and CI result | GitHub Actions | Reproducible check output and workflow history | Link or result summary |
| Public demo or documentation | GitHub Pages or repository | The published artifact and its source | Link |
| Reusable package or container | GitHub Packages | Versioned package or image and release metadata | Link and version |
| Cross-project decision | Notion Decisions | Context, chosen option, rejected alternatives, revisit date, and affected links | Canonical record |
| Benefit activation or renewal | Notion Benefits Matrix | Status, intended workflow, dates, evidence link, and limitations | Canonical record |
| Private thinking | Future Obsidian or another approved private location | Journaling, long-form thinking, and personal knowledge graphs | Link only when useful |
| Recovery archive | Private GitHub evidence repository | Frozen manifests, reports, hashes, and verification state | Canonical link and summary |
| Credentials and tokens | Secret manager or GitHub secrets | Secret values, access controls, and rotation records | Never copy into Notion |

## Boundary rules

- GitHub owns implementation details, Issues, pull requests, checks, releases, and source history.
- Notion owns portfolio context, cross-project decisions, benefits, reminders, and links to canonical records.
- Private thinking may remain local or in a future private knowledge system.
- Secrets and sensitive personal or client information stay outside public repositories, Issues, pull requests, Discussions, Pages, and Notion.
- A Notion entry for a GitHub task should be an index or context record, not a competing detailed task.

When an item fits more than one row, keep the canonical record in the system that owns it and link the other context rather than duplicating the full content.
