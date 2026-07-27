---
name: geo-crawl-freshness-check
description: When the user wants to check whether content is fresh enough to remain eligible for AI citation. Also use when the user mentions "crawl freshness," "how often does AI recrawl my site," or "is my content too old to be cited." For traditional SEO content decay, use content-refresh-audit (content category). For crawler access itself, use ai-crawler-access-audit (technical category).
metadata:
  version: 1.0.0
---

# GEO: Crawl Freshness Check

Assesses whether content is being recrawled and re-evaluated frequently enough by AI systems to stay citation-eligible — freshness functions as an explicit citation factor for AI engines in a way it doesn't as strongly for traditional search.

**When invoking**: On first use, briefly explain why freshness matters more for AI citation than for traditional ranking. On subsequent use, go straight to the check.

## Scope

AI-specific freshness and recrawl assessment. Not general content decay diagnosis for traditional organic traffic (see **content-refresh-audit**) or crawler access rules (see **ai-crawler-access-audit**, technical category).

## Why Freshness Is a Stronger AI-Citation Factor

Multiple studies report that recently updated content is substantially more likely to be cited by AI answer engines than older content, even when the older content still ranks well in traditional search — one commonly cited figure suggests content under roughly three months old is several times more likely to be cited than older equivalents. Content left untouched for six or more months has been observed losing citation eligibility even when its traditional search performance hasn't visibly declined — meaning a page can look "fine" by traditional SEO metrics while quietly falling out of AI citation contention.

## Freshness Signals to Check

| Signal | What to verify |
|---|---|
| **Visible last-updated date** | Present and accurate — a page silently updated without a visible date change gets less credit than one with a clear, current timestamp |
| **Actual content changes, not date-only edits** | Cosmetic date changes without substantive updates are a weaker signal than genuine content refreshes (updated data, expanded sections) |
| **Recrawl cadence** | Server logs (where available) showing how often AI crawlers are actually revisiting the page — infrequent revisits mean even a freshly updated page may not be re-evaluated promptly |
| **Comparison against competitor freshness** | If competing pages in the same topic are updated more recently, that's a direct competitive freshness gap, not just an internal maintenance question |

## Workflow

1. Identify priority pages (highest current or potential AI-citation value) and check their visible last-updated dates.
2. Cross-check whether recent "updates" were substantive or cosmetic.
3. Where server logs are available, check actual AI crawler revisit frequency for these pages.
4. Compare freshness against the top-cited competitor pages for the same topic.
5. Prioritize a refresh cadence for high-value pages specifically for AI-citation purposes, which may be more frequent than the cadence needed for traditional SEO alone.

## Related Skills

- **content-refresh-audit** (content): Broader content decay diagnosis this skill specializes for AI citation
- **ai-overview-optimization**: Where freshness is one of several citation factors
- **ai-crawler-access-audit** (technical): Confirms crawlers can actually reach the content to reassess it
