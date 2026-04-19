---
tags: [reporting, client, PDF, deliverables]
description: Generate a professional client-ready report in PDF format
---

# Generate Client Report

Generate a professional, client-ready report in PDF format using Typst.

## Prerequisites

Read:
- `context/client-profile.md`
- Relevant outputs from `outputs/` subdirectories
- Any user materials in `inputs/reference/`

## Report Types

1. **Monthly Performance Report**
   - Performance metrics and analysis
   - Channel breakdown
   - Insights and recommendations

2. **Campaign Report**
   - Campaign results
   - What worked/didn't work
   - Recommendations

3. **Strategic Recommendations**
   - Situation analysis
   - Recommended approach
   - Implementation plan

4. **Competitive Analysis**
   - Market landscape
   - Competitor profiles
   - Positioning recommendations

5. **Communications Audit**
   - Current state
   - Gap analysis
   - Recommendations

## Process

Use the `client-report-generator` agent to:

### Step 1: Gather Content
- Identify relevant existing outputs
- Review any user-provided materials
- Check for analysis gaps

### Step 2: User Input (Optional)
Ask user:
- What type of report?
- What time period?
- Any specific sections to include?
- Additional materials to incorporate?
- Branding requirements?

### Step 3: Generate Draft
Create markdown draft for review:
- Executive summary
- Key sections
- Data tables
- Recommendations

Save to: `outputs/client-docs/drafts/[date]-[type]-draft.md`

### Step 4: User Review
Present draft for:
- Content accuracy check
- Additional input
- Approval to proceed

### Step 5: Generate Typst
Convert to Typst format with:
- Professional styling
- Headers and footers
- Table of contents
- Page numbers

Save to: `outputs/client-docs/typst/[date]-[type].typ`

### Step 6: Compile PDF
```bash
typst compile outputs/client-docs/typst/[report].typ outputs/client-docs/pdf/[report].pdf
```

Save to: `outputs/client-docs/pdf/[date]-[client]-[type].pdf`

## Output Format

### Draft Markdown Structure

```markdown
# [Report Title]
## [Client Name] | [Date Range]

---

## Executive Summary

[Key findings and recommendations - 2-3 paragraphs]

### At a Glance
- **[Metric]**: [Value] ([trend])
- **[Metric]**: [Value] ([trend])
- **[Metric]**: [Value] ([trend])

### Key Recommendations
1. [Recommendation]
2. [Recommendation]
3. [Recommendation]

---

## [Section 1 Title]

[Content with subsections as needed]

### [Subsection]

[Data, analysis, insights]

> **Key Insight**: [Important callout]

---

## Recommendations

### [Recommendation 1]
- **Action**: [What to do]
- **Rationale**: [Why]
- **Expected Impact**: [Outcome]

### [Recommendation 2]
[Repeat structure]

---

## Next Steps

1. [Action item]
2. [Action item]
3. [Action item]

---

## Appendix

[Supporting detail, raw data, etc.]
```

### Typst Template Reference

The `client-report-generator` agent has the full Typst template. Key elements:
- US Letter paper, 1" margins
- Professional header with client name and date
- Footer with page numbers
- Clean typography
- Table formatting
- Callout boxes for insights

## Completion

1. Present draft for review
2. Incorporate feedback
3. Generate final PDF
4. Provide PDF location
5. Offer to make revisions

## Notes

- Typst must be installed for PDF generation
- User can provide additional branding requirements
- All intermediate files saved for future reference
