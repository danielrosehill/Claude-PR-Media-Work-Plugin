Produce a holding statement for an emerging communications situation. Fast, defensible, non-committal wording for use while facts are still being established.

Ask the user for:
- The situation (one-sentence description of what's happening / what's been reported).
- The audience (media, customers, employees, investors, regulators).
- Any hard constraints (facts that must or must not appear, legal sensitivities).

1. **Load context**: Read brand voice + key messages from `context/brand/` and `context/strategy/` if present. Consult the `crisis-advisor` agent for situational framing.

2. **Draft the holding statement**, aiming for:
   - Acknowledgement of the situation without admitting anything not confirmed.
   - A statement of values or commitment (safety, transparency, cooperation with authorities, etc.) consistent with brand voice.
   - A concrete next step (when more information will be shared, who to contact).
   - Tight wording — holding statements are short.

3. **Provide variants**: one-sentence, short-paragraph, and longer on-the-record versions.

4. **Save the draft**:
   - `pr-response` workspace: `responses/drafts/YYYY-MM-DD-holding-<slug>.md`
   - `comms-strategy` workspace: `outputs/press/crisis/YYYY-MM-DD-holding-<slug>.md`

5. **Flag** anything that needs sign-off from legal/leadership before release. Recommend following up with `/pr-media-work:draft-response` once facts firm up.
