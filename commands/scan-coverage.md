Scan for new coverage of a subject across publications and online sources. Use this to triage what's new since the last sweep.

Ask the user for the monitoring subject if it isn't obvious from the current workspace's CLAUDE.md (look for a configured subject under "Monitoring Subject Context" or similar). Also confirm the time window (default: last 7 days).

1. **Load subject context**: If running inside a provisioned workspace, read `CLAUDE.md` and any `context/` directory for subject, priority keywords, and publications of interest.

2. **Survey sources**: Search the web / configured feeds for coverage matching the subject + keywords within the time window. Prioritise publications in the user's priority list. Deduplicate near-identical hits.

3. **Classify each hit**: coverage / op-ed / by-subject / passing-mention. Note sentiment if obvious. Flag anything urgent (correction required, negative framing, inaccuracy).

4. **Save the scan report**: Write a markdown file to `reports/` (media-monitoring variant), `coverage/` (pr-response variant), or `outputs/reports/` (comms-strategy variant) named `coverage-scan-YYYY-MM-DD.md`. Include:
   - Subject, time window, date of scan
   - One row per hit: publication, title, URL, date, classification, sentiment, urgency flag
   - Summary: total hits, breakdown by classification, top publications
   - Urgent items flagged at the top

5. **Present to user** and recommend next steps — `/pr-media-work:summarize-press` for a brief, `/pr-media-work:draft-response` for anything urgent, or `/pr-media-work:media-fetch` to archive specific hits.
