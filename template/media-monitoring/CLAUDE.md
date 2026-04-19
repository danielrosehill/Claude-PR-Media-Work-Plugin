# Media Monitoring Workspace

## Purpose

This workspace is a media monitoring archive — track coverage about a subject (a person, company, campaign, topic) across publications and gather articles into a structured, searchable dataset.

Primitives for this workspace are provided by the `pr-media-work` Claude Code plugin. The plugin's commands are globally available from any cwd; this workspace holds the **data** (articles, reports, publication profiles, logs).

## Monitoring Subject Context

<!--
Populate this section via `/pr-media-work:media-setup`, or edit directly.
-->

- **Subject**: _TBD — who or what is being monitored_
- **Purpose of monitoring**: _reputation tracking / competitive intel / research / etc._
- **Key topics/themes**: _list_
- **Priority publications**: _list_
- **Scope**: _geographic / language / time window_
- **Relevance criteria**: _what counts as in-scope_
- **Use cases**: _reports, analysis, archive, alerts_

## Directory Structure

```
articles/              # Fetched articles, organised by date
  YYYY/                # Year
    MM_MonthName/      # Month
      article_<theme>_<DDMMYY>_<publication>.md
schemas/               # Article schema + fetch instructions
  fetched-article/
    fetch-schema.json
    fetch-instructions.md
publication-profiles/  # Publication metadata profiles
exports/               # Exported datasets (CSV, JSON, markdown)
reports/               # Scan reports, press briefs, analyses
logs/                  # Activity logs
notes/                 # Working notes
```

## Article Naming Convention

Files live under `articles/YYYY/MM_MonthName/` and are named:

```
article_<theme>_<DDMMYY>_<publication>.md
```

- `theme` — 2-4 keyword description, lowercase, underscore-separated
- `DDMMYY` — publication date
- `publication` — shortened publication identifier

Examples:
- `article_climate_policy_debate_171025_economist.md`
- `article_ai_regulation_europe_030325_ft.md`

## Article Schema

All articles must conform to `schemas/fetched-article/fetch-schema.json`. Required fields include title, `pub_name`, `article_url`, `full_text`, `article_word_count`, `claude_summary`, classification (`is_coverage` / `is_oped` / `by_subject`), `has_comments`, `keywords` (5 tags), `display_summary`. Optional enrichment: author info, publication metadata, comment analysis.

## Primary Commands

Provided by the `pr-media-work` plugin:

| Command | Purpose |
|---------|---------|
| `/pr-media-work:media-setup` | Interview-based setup — populates Monitoring Subject Context above |
| `/pr-media-work:media-fetch` | Fetch and save a single article |
| `/pr-media-work:media-batch` | Fetch multiple URLs in one pass |
| `/pr-media-work:scan-coverage` | Scan recent coverage for new hits |
| `/pr-media-work:summarize-press` | Generate a press brief from recent coverage |
| `/pr-media-work:media-analyze` | Analyse the archive for trends and stats |
| `/pr-media-work:media-search` | Search by keyword / publication / date |
| `/pr-media-work:media-stats` | Quick collection stats |
| `/pr-media-work:media-validate` | Validate files against naming + schema |
| `/pr-media-work:media-export` | Export (CSV / JSON / markdown) |
| `/pr-media-work:media-profile-pub` | Build a publication profile |

## Quality Standards

- Clean article extraction — strip ads, nav, non-article chrome.
- Accurate metadata — publication name, date, author where available.
- Consistent classification (coverage / op-ed / by-subject).
- Files always placed in the correct `YYYY/MM_MonthName/` folder.
- Validate against schema before committing.

## Getting Started

1. Run `/pr-media-work:media-setup` to populate the subject context above.
2. Fetch your first article: `/pr-media-work:media-fetch <url>`.
3. After some coverage accumulates: `/pr-media-work:scan-coverage` and `/pr-media-work:summarize-press`.
