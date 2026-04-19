# PR Response Workspace

A data workspace for reactive PR work — tracking coverage and drafting responses. Provisioned by the [`pr-media-work`](https://github.com/danielrosehill/pr-media-work-plugin) Claude Code plugin.

## What's in here

- `articles/` — archived coverage (schema-validated).
- `coverage/` — running coverage log, scan reports, press briefs.
- `responses/drafts/` — drafted responses awaiting approval.
- `responses/sent/` — responses that have shipped.
- `schemas/` — article schema.
- `logs/` — activity logs.
- `notes/` — working notes.

Edit the "Client / Brand Context" section in `CLAUDE.md` to configure this workspace for a specific engagement.

## Using it

Start with `/pr-media-work:scan-coverage` to see what's new, then `/pr-media-work:draft-response` for anything that needs a reply. See the [plugin README](https://github.com/danielrosehill/pr-media-work-plugin) for the full command set.
