Log a coverage hit into the workspace — a quick way to record a piece of press without running the full fetch workflow.

Ask the user for:
- The URL (or title + publication if no URL).
- Date of publication.
- Classification (coverage / op-ed / by-subject / passing-mention).
- Sentiment (positive / neutral / negative / mixed).
- A one-line takeaway.

1. **Determine target file** based on variant:
   - `pr-response`: append a row to `coverage/coverage-log.md` (create if missing).
   - `comms-strategy`: append a row to `context/historical/media-coverage.md`.
   - `media-monitoring`: prefer `/pr-media-work:media-fetch` for a full archive entry; use this for lightweight logging into `reports/coverage-log.md`.

2. **Row format** (markdown table):
   `| Date | Publication | Title | URL | Classification | Sentiment | Takeaway |`

3. **Append the entry**, creating the file with headers if it doesn't yet exist.

4. **Confirm** the save path and the current row count in the log.
