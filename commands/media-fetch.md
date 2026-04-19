Fetch and save a single article into the media-monitoring archive following the schema and date-based naming convention.

Provide a URL. The `article-fetcher` agent handles the full fetch → extract → validate → save workflow.

1. **Invoke the `article-fetcher` agent** with the URL.
2. The agent will:
   - Fetch clean markdown content from the URL.
   - Extract metadata (title, publication, publication date, author, keywords).
   - Classify (coverage / op-ed / by-subject).
   - Validate against the article schema (see `schemas/fetched-article/fetch-schema.json` in the provisioned workspace if present).
   - Save to `articles/YYYY/MM_MonthName/article_<theme>_<DDMMYY>_<publication>.md`.
3. **Report back** the saved path, any fields that had to be defaulted, and any paywall/fetch issues encountered.

Pair with `/pr-media-work:media-batch` for multi-URL runs.
