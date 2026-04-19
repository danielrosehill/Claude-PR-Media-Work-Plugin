Roll up recent press coverage into a concise brief. Use this after `/pr-media-work:scan-coverage` or any time the user wants a digest of what's been published.

Ask the user for a time window (default: last 7 days) and any scope constraints (specific subject, publications, campaign) if not evident from the workspace context.

1. **Gather coverage**:
   - In a `media-monitoring` workspace: read from `articles/YYYY/MM_MonthName/` within the time window, and any recent scan reports in `reports/`.
   - In a `pr-response` workspace: read from `coverage/` and any recent scan reports.
   - In a `comms-strategy` workspace: read from `context/historical/media-coverage.md` and `outputs/reports/`.

2. **Structure the brief**:
   - **Headline summary** (2-3 sentences): volume, tone, standout hits.
   - **Top stories**: 3-5 most significant hits with one-line takeaway each.
   - **Themes**: dominant narratives and framings across the coverage.
   - **Sentiment breakdown**: positive / neutral / negative counts and notable outliers.
   - **Publication mix**: where coverage landed, by tier.
   - **Risks and opportunities**: anything requiring response, any pitch angles that emerged.
   - **Recommended actions**: which commands or workflows to run next.

3. **Save the brief**:
   - Write to `reports/press-brief-YYYY-MM-DD.md` (media-monitoring) or `outputs/reports/press-brief-YYYY-MM-DD.md` (comms-strategy) or `coverage/press-brief-YYYY-MM-DD.md` (pr-response).

4. **Present** the brief inline and link the saved path.
