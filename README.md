# pr-media-work-plugin

Claude Code plugin for work-focused PR and media monitoring — scanning coverage, summarizing press, drafting responses, and building comms strategy. Ships domain primitives plus a provisioning skill that scaffolds a fresh workspace.

Part of the [danielrosehill Claude Code marketplace](https://github.com/danielrosehill/Claude-Code-Plugins).

## What you get

### Primitives (always available once the plugin is installed)

**Cluster-level** (`/pr-media-work:*`):
- `scan-coverage` — scan for new coverage of a subject across sources
- `summarize-press` — roll up press hits into a brief
- `draft-response` — draft a PR response (statement, pitch, correction, Q&A)

**Media monitoring** (`/pr-media-work:media-*`):
- `media-fetch` — fetch and save an article into the date-based archive
- `media-batch` — batch-fetch multiple URLs
- `media-analyze` — generate stats/trends over the archive
- `media-search` — search the archive by keyword/publication/date
- `media-stats` — quick collection stats
- `media-validate` — validate against naming/schema
- `media-export` — export (CSV/JSON/markdown)
- `media-profile-pub` — build a publication profile
- `media-setup` — interactive setup to capture monitoring subject context

**PR response** (`/pr-media-work:pr-*`):
- `pr-monitor-news` — monitor news/mentions for opportunities
- `pr-media-pitch` — draft a tailored media pitch
- `pr-build-media-list` — build a targeted media list
- `pr-find-opportunities` — find podcast/speaking/reactive opportunities
- `pr-crisis-hold` — produce a holding statement
- `pr-log-coverage` — log a coverage hit into the workspace

**Comms strategy** (`/pr-media-work:comms-*`):
- `comms-initialize` — interactive setup for a new client/brand
- `comms-update-context` — refresh client/brand context
- `comms-refresh-strategy` — revise the strategy doc
- `comms-competitive-scan` — analyze competitive comms landscape
- `comms-create-campaign` — develop a campaign framework
- `comms-draft-content` — draft content in brand voice
- `comms-generate-social` — generate social content ideas
- `comms-audit-messaging` — audit messaging consistency
- `comms-analyze-performance` — analyze performance data
- `comms-client-report` — generate a client-ready PDF report

### Agents

- `article-fetcher` — fetch a single article into the archive
- `batch-fetch` — process multiple article URLs
- `article-analyzer` — analyze the collection for trends and insights
- `publication-profiler` — research publications and build profiles
- `archive-organizer` — archive maintenance and validation
- `campaign-strategist` — design campaign frameworks
- `content-creator` — draft content on-brand
- `media-relations-advisor` — media relations strategy
- `media-list-builder` — media/podcast/speaking opportunity lists
- `brand-voice-guardian` — review content for brand consistency
- `crisis-advisor` — crisis comms guidance
- `metrics-analyst` — performance analysis
- `strategy-director` — high-level strategic direction
- `positioning-analyst` — positioning and differentiation
- `audience-researcher` — audience personas and insights
- `social-media-manager` — social strategy and execution
- `client-report-generator` — Typst PDF client report generation

### Provisioning skill

- `/pr-media-work:new-workspace <name> [--variant=media-monitoring|pr-response|comms-strategy] [--local-only] [--private]`

Scaffolds a new workspace, personalises it from `~/.claude/CLAUDE.md`, and (by default) creates a public GitHub repo.

## Pattern

Primitives live in the plugin → globally available from any cwd.
Workspace scaffolds are provisioned as **data** → no `.claude/` tree inside provisioned workspaces.
Plugin updates never touch your workspace data.

See [PLAN.md in Claude-Workspace-Reshaping-190426](https://github.com/danielrosehill/Claude-Workspace-Reshaping-190426) for the full pattern spec this plugin follows.

## Variants

- `media-monitoring` — date-based article archive for tracking coverage. Schema-validated article capture with analysis and export commands.
- `pr-response` — coverage log + response drafting workspace. Tuned for drafting statements, pitches, corrections, and Q&A against live coverage.
- `comms-strategy` — full communications strategist workspace. Brand/audience/competitive/historical context, campaign and content outputs, client-ready reporting.

## Install

Via the danielrosehill marketplace:

```
/plugin marketplace add danielrosehill/Claude-Code-Plugins
/plugin install pr-media-work
```

## License

MIT.
