---
name: rank-tracking-summary
description: When the user wants to summarize keyword ranking movement over a period, or explain a sudden ranking change. Also use when the user mentions "rank tracking," "keyword position report," "we dropped in rankings," "SERP volatility," or "ranking movement summary." For diagnosing whether a ranking drop is really a traffic/tracking issue, use traffic-anomaly-detector. For the underlying content/technical fixes, use technical-seo-audit or content-gap-analysis.
metadata:
  version: 1.0.0
---

# Analytics: Rank Tracking Summary

Turns raw keyword position data into a summary that distinguishes real, actionable ranking movement from normal SERP volatility — and flags when a ranking change is more likely a SERP-feature or tracking artifact than a genuine visibility shift.

**When invoking**: On first use, briefly explain the volatility-vs-signal distinction below. On subsequent use, go straight to the summary.

## Scope

Covers summarizing and interpreting rank tracking data. Does not cover the technical or content fixes that follow from a diagnosed drop (see **technical-seo-audit**, **content-gap-analysis**) or whether the underlying issue is actually a traffic-measurement problem rather than a ranking one (see **traffic-anomaly-detector**).

## Volatility vs. Signal

Day-to-day keyword position fluctuation of a few spots is normal SERP noise, not a trend — especially for competitive, high-volume terms where multiple sites hover within a narrow band. Treat single-day swings as noise and look for movement that holds across at least several consecutive checks before calling it a real change. Position tracking is also inherently noisier for personalized or localized SERPs, where the "true" rank varies by searcher location and history — always confirm the tracking tool's location/device settings match what actually matters for the business before trusting a reported position.

## What to Separate in a Summary

| Category | What it captures | Why it needs its own line item |
|---|---|---|
| **Genuine ranking movement** | Position change sustained across multiple checks, tied to a specific page/URL | The only category that should drive action |
| **SERP feature changes** | A featured snippet, AI Overview, or People Also Ask box appearing/disappearing above organic results | Can make a "position 1" ranking suddenly deliver far less visible real estate and traffic without the tracked position number changing at all |
| **Cannibalization** | Two of the client's own pages trading rank for the same query | Looks like "we're still ranking" in aggregate but often means neither page is optimized as well as one consolidated page would be |
| **New competitor entrants** | A domain not previously present now ranking above the tracked page | Distinguishes an algorithmic drop from simply being outcompeted by better content |

## Workflow

1. **Pull position data** across the reporting period, segmented by device and location if the tool supports it.
2. **Filter out single-day noise** — require movement to hold across multiple consecutive data points before flagging it as significant.
3. **Check for SERP feature changes** on the affected queries, not just organic position — a stable position 1 next to a new AI Overview is a different story than a stable position 1 alone.
4. **Check for cannibalization** if two owned URLs both appear for the same query across the period.
5. **Group findings**: genuine wins, genuine losses, noise (excluded from headline summary but available in the detail view), and SERP-feature-driven visibility changes.
6. **Route genuine losses** to the appropriate next skill — **technical-seo-audit** if the cause looks technical (deindexing, crawl errors), **content-gap-analysis** if a competitor is winning on topical depth.

## Related Skills

- **traffic-anomaly-detector**: Confirms whether a reported ranking drop is actually showing up as a real traffic change, or is a tracking artifact
- **technical-seo-audit**: Technical causes of ranking loss (deindexing, crawl errors, redirects)
- **content-gap-analysis**: Content-driven causes of ranking loss (competitor covering more ground)
- **client-report-writer**: Where this summary typically feeds into a client-facing narrative
