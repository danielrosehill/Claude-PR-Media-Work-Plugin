# Communications Strategy Workspace

A data workspace for communications strategists — brand/audience/competitive context, campaign and content outputs, client-ready reporting. Provisioned by the [`pr-media-work`](https://github.com/danielrosehill/pr-media-work-plugin) Claude Code plugin.

## What's in here

- `context/` — source of truth for client/brand info (brand, audiences, competitive, strategy, historical).
- `outputs/` — generated deliverables (strategy, campaigns, content, social, press, pitches, reports, client-ready PDFs).
- `inputs/` — briefs, metrics, and reference materials dropped in for processing.
- `prompts/` — reusable research prompts (drafting / queue / archive).
- `logs/` — activity logs.

See `CLAUDE.md` for the full workflow.

## Using it

Start with `/pr-media-work:comms-initialize` — an interview-based setup that populates the `context/` files for your client/brand. After that, use the `/pr-media-work:comms-*`, `/pr-media-work:pr-*`, and cluster-level commands listed in `CLAUDE.md`.

Full command reference: [plugin README](https://github.com/danielrosehill/pr-media-work-plugin).
