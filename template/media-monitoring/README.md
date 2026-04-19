# Media Monitoring Workspace

A data workspace for tracking media coverage of a subject. Provisioned by the [`pr-media-work`](https://github.com/danielrosehill/pr-media-work-plugin) Claude Code plugin.

## What's in here

- `articles/` — clean, schema-validated article archive organised by date.
- `schemas/` — JSON schema and fetch instructions that govern article structure.
- `publication-profiles/` — metadata profiles for publications being tracked.
- `reports/` — scan reports and press briefs.
- `exports/` — exported datasets (CSV, JSON, markdown).
- `logs/` — activity logs.
- `notes/` — working notes.

See `CLAUDE.md` for the full workflow and the subject-context section to configure.

## Using it

Plugin commands (globally available once `pr-media-work` is installed):

- `/pr-media-work:media-setup` — configure the monitoring subject
- `/pr-media-work:media-fetch <url>` — archive an article
- `/pr-media-work:scan-coverage` — scan for new coverage
- `/pr-media-work:summarize-press` — generate a brief

Full command reference: see the [plugin README](https://github.com/danielrosehill/pr-media-work-plugin).
