---
name: seo-reporting-dashboard
description: When the user wants to build a recurring SEO performance dashboard or report covering organic traffic, rankings, and technical health together. Also use when the user mentions "SEO dashboard," "monthly SEO report," "organic performance report," or "SEO scorecard." For general (non-SEO-specific) KPI dashboard design principles, use kpi-dashboard-builder. For the client-facing narrative version, use client-report-writer.
metadata:
  version: 1.0.0
---

# Analytics: SEO Reporting Dashboard

Applies the audience-first, tiered-metric framework from **kpi-dashboard-builder** specifically to SEO reporting, combining three data sources (analytics, rank tracking, and technical crawl health) that are often reported separately even though they explain each other.

**When invoking**: On first use, briefly note why the three data sources need to be combined rather than reported in isolation. On subsequent use, go straight to the dashboard spec.

## Scope

Covers the specific metric set and structure for SEO reporting. For the general audience-first dashboard design principles this inherits, see **kpi-dashboard-builder**. For narrative client communication built on top of this data, see **client-report-writer**.

## The Three Data Sources That Must Be Combined

| Source | What it shows | Why it's insufficient alone |
|---|---|---|
| **Analytics (GA4)** | Organic sessions, conversions, landing page performance | Doesn't explain *why* traffic moved — a ranking drop or a crawl error looks identical to "organic traffic went down" in GA4 alone |
| **Rank tracking** | Keyword position movement, SERP feature presence | Doesn't show whether ranking movement actually translated into traffic or conversions |
| **Technical/crawl health** | Indexation status, crawl errors, Core Web Vitals | Explains ranking or traffic drops that have a technical root cause, but says nothing about whether the content itself is competitive |

A report showing only GA4 traffic numbers cannot distinguish a content problem from a technical problem from a SERP-feature problem — this is the most common gap in SEO reporting.

## Metric Tiers (applying the kpi-dashboard-builder framework)

1. **North star**: organic sessions and organic-attributed conversions/revenue, always shown against the prior period and, where available, against target.
2. **Supporting**: ranking movement summary (wins/losses/noise per **rank-tracking-summary**), top landing pages by organic traffic, indexation status, crawl error count.
3. **Drill-down**: full keyword-level position table, page-by-page technical issue list, backlink changes.

## Workflow

1. **Confirm the underlying data is reliable** — GA4 audit status, rank tracker location/device settings — before building on top of it.
2. **Pull the north-star numbers** (organic sessions, conversions/revenue) with period-over-period comparison.
3. **Pull the ranking summary** using the noise-filtering approach from **rank-tracking-summary**, not raw position swings.
4. **Pull technical health status** — indexation, crawl errors, Core Web Vitals pass/fail.
5. **Cross-reference the three sources** for any notable movement: did a ranking change coincide with a traffic change? Did a crawl error spike precede a traffic drop?
6. **Structure the output** in the three-tier hierarchy, with the narrative explanation (not just the numbers) placed next to the north-star metrics.

## Related Skills

- **kpi-dashboard-builder**: The general dashboard design framework this skill specializes for SEO
- **rank-tracking-summary**: Source of the ranking-movement tier
- **traffic-anomaly-detector**, **ga4-audit**: Data reliability prerequisites
- **client-report-writer**: Narrative layer built on top of this dashboard for external stakeholders
