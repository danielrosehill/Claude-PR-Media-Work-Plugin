---
tags: [media, PR, outreach]
description: Build a targeted media list for pitching
---

# Build Media List

Build a targeted media list for a specific campaign, story angle, or ongoing coverage needs.

## Prerequisites

Read:
- `context/brand/brand-overview.md`
- `context/audiences/primary-audiences.md`
- `context/historical/media-coverage.md`

## Parameters

Gather from user:
1. **Purpose**: What story/angle are we pitching?
2. **Audience**: What audiences need to see coverage?
3. **Tiers**: What level of coverage needed (Tier 1/2/3)?
4. **Geography**: Regional, national, international?
5. **Industry focus**: Trade/industry publications needed?
6. **Existing relationships**: Any journalists to include?

## Research Process

Use the `media-list-builder` agent to:

1. **Define outlet categories**
   - Identify relevant publication types
   - Map to audience needs

2. **Research publications**
   - Use web search to find relevant outlets
   - Identify beat reporters
   - Review recent coverage

3. **Build contact list**
   - Reporter names and beats
   - Contact information
   - Social media handles
   - Recent relevant articles

4. **Prioritize**
   - Tier by relevance and reach
   - Note relationship status
   - Flag high-priority targets

## Output Format

```markdown
# Media List: [Purpose/Campaign]

## Overview
- **Purpose**: [Story angle]
- **Date**: [Date]
- **Total Contacts**: [Count]

## Tier 1: High Priority

### [Publication]
| Reporter | Beat | Email | Twitter | Recent Article |
|----------|------|-------|---------|----------------|
| | | | | |

## Tier 2: Medium Priority
[Same structure]

## Tier 3: Supplementary
[Same structure]

## Pitch Strategy Notes
- [Reporter-specific notes]
```

## Output Location

Save to: `outputs/press/media-lists/[date]-media-list-[purpose].md`

Update: `context/historical/media-coverage.md` with any new journalist relationships

## Completion

1. Review list with user
2. Prioritize top targets
3. Suggest pitch timing
4. Offer to create pitches with `/media-pitch`
