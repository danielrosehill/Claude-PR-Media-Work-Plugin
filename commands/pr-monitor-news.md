---
tags: [monitoring, news, tracking, brand]
description: Monitor news and mentions for reactive opportunities and brand tracking
---

# Monitor News

Monitor news, industry developments, and brand mentions to identify opportunities and track coverage.

## Monitoring Types

### 1. Industry News
Track news relevant to client's industry:
- Breaking news
- Trends and developments
- Regulatory/policy changes
- Market movements

### 2. Competitor News
Monitor competitor activity:
- Announcements
- Coverage received
- Campaign activity
- Executive moves

### 3. Brand Mentions
Track mentions of client brand:
- Media coverage
- Social mentions
- Analyst commentary
- Review sites

### 4. Topic Monitoring
Watch specific topics for reactive opportunities:
- Key industry themes
- Trending topics
- Policy areas
- Market events

## Monitoring Sources

### News Sources
- **Google News**: Search for industry and competitor news
- **NewsAPI**: Programmatic news access (if MCP available)
- **RSS Feeds**: Industry publication feeds
- **Wire Services**: PR Newswire, Business Wire

### Social Monitoring
- **Twitter/X**: Trending topics, journalist conversations
- **LinkedIn**: Industry discussions, executive commentary
- **Reddit**: Industry subreddits

### Brand Monitoring
- **Google Alerts**: Set up for brand, competitors, keywords
- **Mention.com**: Brand monitoring (if integrated)
- **Meltwater**: Media monitoring (if integrated)

## Execution

### Quick Scan

Perform web searches for:
```
"[Brand Name]" news
"[Competitor Name]" news
"[Industry keyword]" news today
"[Topic]" trending
```

### Comprehensive Monitoring

1. **Set up alerts**
   - Brand name variants
   - Competitor names
   - Industry keywords
   - Executive names

2. **Create RSS feed list**
   - Key trade publications
   - Industry news sites
   - Competitor newsrooms
   - Analyst blogs

3. **Build Twitter lists**
   - Industry journalists
   - Competitors
   - Industry influencers

## Output Format

```markdown
# News Monitoring Report: [Date]

## Summary
- **Period**: [Timeframe]
- **Brand Mentions**: [Count]
- **Competitor Activity**: [Notable items]
- **Reactive Opportunities**: [Count]

## Brand Mentions

### Media Coverage
| Date | Outlet | Headline | Sentiment | Link |
|------|--------|----------|-----------|------|
| | | | | |

### Social Mentions
[Notable mentions summary]

## Competitor News

### [Competitor Name]
- **News**: [Summary]
- **Implication**: [What it means for us]
- **Action**: [If any needed]

## Industry Developments

### [Development]
- **What**: [Summary]
- **Relevance**: [Why it matters]
- **Opportunity**: [How we can respond]

## Reactive Opportunities

### [Opportunity 1]
- **Story**: [What's happening]
- **Our Angle**: [Commentary opportunity]
- **Urgency**: [Timing]
- **Recommended Action**: [What to do]

## Monitoring Recommendations

### New Alerts to Set Up
- [Alert suggestion]

### Accounts to Follow
- [Account suggestion]
```

## MCP Integration

If available, use:
- **NewsAPI MCP**: Fetch latest news programmatically
- **Mention MCP**: Pull brand mention data
- **Social media MCPs**: Access platform data

Without MCPs, use web search to gather news.

## Output Location

Save monitoring reports to: `outputs/reports/monitoring/[date]-monitoring.md`

## Ongoing Setup

For continuous monitoring, recommend user set up:

### Google Alerts
- Brand: `"[Company Name]"`
- Competitor: `"[Competitor Name]"`
- Keywords: `"[Industry keyword]"`
- Product: `"[Product Name]"`

### RSS Feeds
Recommend feed reader with:
- Industry publications
- Competitor newsrooms
- News searches

## Completion

1. Present monitoring findings
2. Highlight immediate opportunities
3. Flag any concerning mentions
4. Recommend monitoring setup improvements
