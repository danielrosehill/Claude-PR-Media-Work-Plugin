Draft a PR response to a piece of coverage. Covers statements, corrections, reactive pitches, and Q&A documents.

Ask the user for:
- The trigger: URL of the article, or a summary of what needs responding to.
- The response type: `statement`, `correction`, `holding-statement`, `reactive-pitch`, `qa-document`, or `custom`.
- The desired tone (if brand voice isn't already documented in the workspace).
- Any facts or proof points the response must include.

1. **Load brand/subject context**: Read any `context/brand/voice-and-tone.md`, `context/brand/messaging-framework.md`, `context/strategy/key-messages.md`, or workspace `CLAUDE.md` for voice guidance and approved messaging.

2. **Analyse the trigger**: If a URL was given, fetch the article (or use an already-archived version). Identify the specific claims, framing, or opportunities to respond to.

3. **Draft the response** according to type:
   - **statement**: on-the-record quote or short written statement.
   - **correction**: polite but firm correction with evidence.
   - **holding-statement**: short, defensible, non-committal wording for an emerging situation.
   - **reactive-pitch**: pitch offering the client as a source or perspective on a live story.
   - **qa-document**: anticipated questions with approved answers.

4. **Save the draft**:
   - `pr-response` workspace: `responses/drafts/YYYY-MM-DD-<slug>.md`
   - `comms-strategy` workspace: `outputs/pitches/reactive/YYYY-MM-DD-<slug>.md` or `outputs/press/YYYY-MM-DD-<slug>.md` as appropriate.
   - Include YAML front matter: trigger URL, response type, target audience/publication, status (draft), date.

5. **Present the draft inline** and flag:
   - Any claims that need sign-off before sending.
   - Any references to the brand voice guide or key messages that were applied.
   - Suggested next steps (internal review, approve and send, escalate to `crisis-advisor` agent, etc.).
