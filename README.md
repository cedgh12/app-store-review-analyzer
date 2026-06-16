# App Store Review Analyzer

Automated weekly digest of mobile app reviews from Apple App Store and Google Play, 
replacing manual review-by-review reading with a structured trend analysis report.

## Context

The product team was reading and responding to app store reviews manually, 
one by one, on an ad-hoc basis. No aggregated view, no trend detection, 
no weekly rhythm. With 50+ reviews per week across both stores, 
this was time-consuming and provided no strategic visibility.

## How it works

1. **Fetch** — Apple App Store RSS feed retrieves new reviews automatically
2. **Classify** — GPT-4.1-mini categorizes each review: Bug, Feature Request, 
   Satisfaction, Dissatisfaction, Authentication Issue
3. **Store** — Results pushed to Google Sheets (date, username, category, summary)
4. **Report** — HTML email digest sent weekly with category breakdown and review details

## Output example

Weekly digest includes:
- Total reviews analyzed
- Breakdown by category (Bug, Feature Request, Satisfaction, etc.)
- Per-review summary with star rating and key insight
- Trend detection across weeks via Google Sheets history

## Stack

- **n8n** — workflow orchestration (self-hosted via Docker)
- **Apple App Store RSS** — review source
- **GPT-4.1-mini** — classification and summarization
- **Google Sheets** — data storage and history
- **HTML email** — weekly digest delivery

## Impact

- Eliminated manual review-by-review reading
- Weekly trend visibility where none existed before
- Enables proactive bug detection and feature prioritization
- Supports response preparation at scale

## Notes

Workflow runs locally via Docker on Windows. 
Source not published — internal tooling built autonomously as a PM initiative.
