---
tags: [content, creation, writing]
description: Generate specific content pieces (blog posts, articles, emails, etc.)
---

# Draft Content

Generate content aligned with brand voice and messaging.

## Prerequisites

Read:
- `context/brand/voice-and-tone.md`
- `context/brand/messaging-framework.md`
- `context/audiences/primary-audiences.md`
- `context/strategy/key-messages.md`

## Content Brief

Gather from user:
1. **Content type**: Blog post, article, email, landing page, etc.
2. **Topic**: Subject matter and angle
3. **Target audience**: Which persona(s)
4. **Objective**: What should reader think/feel/do
5. **Key messages**: Which messages to include
6. **Length**: Target word count or format
7. **SEO requirements**: Keywords (if applicable)
8. **Call to action**: Desired next step

## Content Creation

Use the `content-creator` agent to draft content.

### Process:
1. Review brand voice guidelines
2. Research topic as needed
3. Create outline
4. Draft content
5. Self-review against brand guidelines
6. Include SEO elements if applicable

### Quality Checks:
- Voice consistency
- Message accuracy
- Audience appropriateness
- Clear call to action
- Grammar and style

## Output

Save to appropriate location:
- Blog posts: `outputs/content/blog/`
- Articles: `outputs/content/articles/`
- Emails: `outputs/content/email/`
- Website copy: `outputs/content/web/`

Naming: `[date]-[content-type]-[topic].md`

## Review

After drafting:
1. Present content for review
2. Offer to run through `brand-voice-guardian` agent
3. Make revisions as needed
4. Commit final version
