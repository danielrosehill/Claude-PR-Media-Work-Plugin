# PR Response Workspace

## Purpose

This workspace is tuned for reactive PR work — monitoring coverage of a client/brand, logging hits, and drafting responses (statements, corrections, reactive pitches, Q&A, holding statements).

Primitives for this workspace are provided by the `pr-media-work` Claude Code plugin. The plugin's commands are globally available; this workspace holds the **data** (archived coverage, response drafts, logs).

## Client / Brand Context

<!--
Edit this section to reflect the client or brand this workspace serves.
-->

- **Client / brand**: _TBD_
- **Spokespeople**: _names and titles_
- **Approved voice / tone**: _summary or link to full guide_
- **Core messages**: _3-5 approved key messages_
- **Do-not-say list**: _terms, claims, or framings to avoid_
- **Approval chain**: _who signs off on what_

## Directory Structure

```
articles/              # Archived articles (same structure as media-monitoring variant)
  YYYY/
    MM_MonthName/
      article_<theme>_<DDMMYY>_<publication>.md
coverage/              # Coverage log + scan reports + press briefs
  coverage-log.md      # Running log of every coverage hit
responses/
  drafts/              # Response drafts pending approval
  sent/                # Responses that have been sent / published
schemas/               # Article schema + fetch instructions
  fetched-article/
    fetch-schema.json
    fetch-instructions.md
logs/                  # Activity logs
notes/                 # Working notes
```

## Workflows

### React to a new piece of coverage

1. `/pr-media-work:scan-coverage` — surface recent hits.
2. `/pr-media-work:pr-log-coverage` or `/pr-media-work:media-fetch` — record the hit (lightweight or full archive).
3. `/pr-media-work:draft-response` — draft the response (statement / correction / reactive pitch / Q&A).
4. Internal review — move approved drafts from `responses/drafts/` to `responses/sent/`.

### Handle an emerging situation

1. `/pr-media-work:pr-crisis-hold` — generate a holding statement.
2. As facts firm up, `/pr-media-work:draft-response` for a fuller statement.
3. `/pr-media-work:scan-coverage` — track how the situation develops in press.

### Proactive outreach

1. `/pr-media-work:pr-find-opportunities` — podcast, speaking, reactive-pitching opportunities.
2. `/pr-media-work:pr-build-media-list` — build a targeted media list.
3. `/pr-media-work:pr-media-pitch` — draft the pitch.

## Primary Commands

| Command | Purpose |
|---------|---------|
| `/pr-media-work:scan-coverage` | Scan recent coverage for new hits |
| `/pr-media-work:summarize-press` | Roll up coverage into a brief |
| `/pr-media-work:draft-response` | Draft a statement / correction / pitch / Q&A |
| `/pr-media-work:pr-crisis-hold` | Produce a holding statement |
| `/pr-media-work:pr-log-coverage` | Log a coverage hit |
| `/pr-media-work:pr-monitor-news` | Monitor news and mentions |
| `/pr-media-work:pr-media-pitch` | Draft a media pitch |
| `/pr-media-work:pr-build-media-list` | Build a targeted media list |
| `/pr-media-work:pr-find-opportunities` | Find pitch opportunities |
| `/pr-media-work:media-fetch` | Archive an article for the coverage record |

## Quality Standards

- Every response draft has a clear trigger (URL or situation) in its front matter.
- Nothing leaves `responses/drafts/` without going through the documented approval chain.
- The coverage log is the single source of truth for what's been published about the client.
- Holding statements are dated and superseded versions archived, not deleted.
