# Communications Strategy Workspace

## Purpose

This workspace supports comms professionals — in-house teams, agencies, or consultants — developing and executing communications strategy for a client or brand. It covers strategic planning, content creation, campaign management, media relations, performance analysis, and ongoing strategic refinement.

Primitives for this workspace are provided by the `pr-media-work` Claude Code plugin. The plugin's commands are globally available; this workspace holds the **data** (brand context, strategy docs, campaign materials, reports).

## Getting Started

Run `/pr-media-work:comms-initialize` first. It runs an interactive interview and populates the context files.

## Directory Structure

```
context/                       # Source of truth for client/brand info
  client-profile.md            # Core client/brand information
  brand/                       # Brand identity + guidelines
    brand-overview.md
    messaging-framework.md
    voice-and-tone.md
    visual-identity-notes.md
  audiences/                   # Audience profiles
    primary-audiences.md
    secondary-audiences.md
    stakeholder-map.md
  competitive/                 # Competitive landscape
    competitor-profiles.md
    market-position.md
  strategy/                    # Strategic documents
    communications-strategy.md
    goals-and-objectives.md
    key-messages.md
  historical/                  # Past performance + materials
    campaign-history.md
    media-coverage.md
    performance-benchmarks.md
outputs/                       # Generated deliverables
  strategy/                    # Strategic documents
  campaigns/                   # Campaign materials (one folder per campaign)
  content/                     # Blog posts, articles, thought leadership
  social/                      # Social content and calendars
  press/                       # Press releases + media materials
    media-lists/
  pitches/                     # Media pitches and outreach
    podcasts/
    speaking/
    reactive/
  reports/                     # Performance reports + analysis
  recommendations/             # Strategic recommendations
  client-docs/                 # Client-ready deliverables
    drafts/
    typst/                     # Typst source for PDFs
    pdf/                       # Final PDF reports
inputs/                        # Raw materials for processing
  briefs/                      # Campaign / content briefs
  metrics/                     # Raw performance data
  reference/                   # Reference materials
prompts/                       # Reusable research prompts
  drafting/
  queue/
  archive/
logs/                          # Activity + decision logs
```

## Context Management

The `context/` folder is the single source of truth. Keep it current — strategy, content, and analysis all read from here.

- **Brand** (`context/brand/`) — identity, messaging framework, voice/tone, visual notes.
- **Audiences** (`context/audiences/`) — primary/secondary personas, stakeholder map.
- **Competitive** (`context/competitive/`) — competitor profiles, market position.
- **Strategy** (`context/strategy/`) — strategy doc, goals, key messages.
- **Historical** (`context/historical/`) — campaign history, coverage log, benchmarks.

## Primary Commands

| Command | Purpose |
|---------|---------|
| `/pr-media-work:comms-initialize` | Interactive setup for a new client/brand |
| `/pr-media-work:comms-update-context` | Refresh client/brand context |
| `/pr-media-work:comms-refresh-strategy` | Revise the communications strategy |
| `/pr-media-work:comms-competitive-scan` | Analyse the competitive comms landscape |
| `/pr-media-work:comms-create-campaign` | Develop a campaign framework |
| `/pr-media-work:comms-draft-content` | Draft content in brand voice |
| `/pr-media-work:comms-generate-social` | Generate social content ideas |
| `/pr-media-work:comms-audit-messaging` | Audit messaging consistency |
| `/pr-media-work:comms-analyze-performance` | Analyse performance data |
| `/pr-media-work:comms-client-report` | Generate client-ready PDF report |
| `/pr-media-work:pr-media-pitch` | Draft a media pitch |
| `/pr-media-work:pr-build-media-list` | Build a targeted media list |
| `/pr-media-work:pr-find-opportunities` | Find podcast/speaking/reactive opportunities |
| `/pr-media-work:scan-coverage` | Scan recent coverage |
| `/pr-media-work:summarize-press` | Generate a press brief |
| `/pr-media-work:draft-response` | Draft a reactive response |

## Core Workflows

1. **Strategy development** — gather context, review, use `campaign-strategist` / `strategy-director` agents, write to `outputs/strategy/`, refine via `/pr-media-work:comms-refresh-strategy`.
2. **Campaign planning** — drop brief in `inputs/briefs/`, run `/pr-media-work:comms-create-campaign`, materials land in `outputs/campaigns/<campaign-name>/`.
3. **Content creation** — reference `context/brand/voice-and-tone.md`, run `/pr-media-work:comms-draft-content`, review with `brand-voice-guardian` agent.
4. **Media relations** — use `media-relations-advisor` + `media-list-builder` agents, run `/pr-media-work:pr-media-pitch` and `/pr-media-work:pr-build-media-list`.
5. **Performance analysis** — drop metrics into `inputs/metrics/`, run `/pr-media-work:comms-analyze-performance`, reports land in `outputs/reports/`.
6. **Crisis communications** — use `crisis-advisor` agent, `/pr-media-work:pr-crisis-hold` for holding statements, `/pr-media-work:draft-response` for fuller responses.

## Output Conventions

- Date-prefix time-sensitive files: `2025-01-12-q1-campaign-strategy.md`.
- Campaigns get their own subfolder under `outputs/campaigns/`.
- Client-ready PDFs built via Typst: source in `outputs/client-docs/typst/`, final PDFs in `outputs/client-docs/pdf/`.

## Best Practices

- Treat `context/` as the source of truth; update it whenever the engagement evolves.
- Always reference `context/brand/voice-and-tone.md` before creating content.
- Check alignment against `context/strategy/goals-and-objectives.md` in every campaign brief.
- Archive superseded strategy docs rather than deleting them — history matters for retrospectives.
- Keep sensitive client info in `context/`; consider a private repo for highly sensitive engagements.
