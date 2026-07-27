---
name: kpi-dashboard-builder
description: When the user wants to design a KPI dashboard that shows the metrics that actually matter for a role or stakeholder, rather than everything available. Also use when the user mentions "KPI dashboard," "what metrics should I track," "executive dashboard," "north star metric," or "too many metrics, need to simplify." For client-facing report writing specifically, use client-report-writer. For SEO-specific dashboards, use seo-reporting-dashboard.
metadata:
  version: 1.0.0
---

# Analytics: KPI Dashboard Builder

Designs a dashboard around the small number of metrics that actually drive decisions for a specific audience, rather than surfacing every available metric. The most common dashboard failure isn't missing data it's too much data, presented with equal visual weight, so nothing stands out as actionable.

**When invoking**: On first use, briefly explain the audience-first framing before building the metric list. On subsequent use, go straight to the dashboard spec.

## Scope

Covers metric selection, hierarchy, and dashboard structure. Does not cover the underlying data quality this depends on (see **ga4-audit**), or client-facing narrative reporting (see **client-report-writer**).

## Audience-First Framing

The right metrics depend entirely on who's looking and what decision they're making with the dashboard a dashboard is not "more useful" for including more metrics.

| Audience | What they need to decide | Typical top-level metrics |
|---|---|---|
| **Executive/C-suite** | Is the business/channel healthy, and does it need attention? | Revenue, CAC, LTV, overall conversion rate, 1–2 leading indicators rarely more than 5–6 numbers total |
| **Marketing lead** | Where should budget and effort shift this month? | Channel-level traffic, conversion rate by channel, cost per conversion, funnel stage drop-off |
| **SEO/content specialist** | What content or technical work should happen next? | Organic sessions, ranking movement, indexed pages, crawl errors, top landing pages by conversion |
| **Client (external)** | Is the engagement delivering value? | Outcome metrics tied to the contract (leads, revenue, rankings for agreed terms) avoid vanity metrics not tied to what was promised |

## Metric Hierarchy

Structure every dashboard in three tiers so the eye lands on what matters first:

1. **North star / headline metrics** (1–3 max) — the numbers that answer "is this working," always visible at the top.
2. **Supporting/diagnostic metrics** (4–8) — the numbers that explain *why* the headline moved, one level down.
3. **Detail/drill-down data** — full tables, segment breakdowns, available on demand but not competing visually with tiers 1–2.

## Common Mistakes to Avoid

- **Vanity metrics without context**: raw session counts or impressions with no conversion or revenue tie-in tell a stakeholder nothing about business impact.
- **Equal visual weight for all metrics**: if everything is the same font size and prominence, nothing is prioritized the dashboard fails at its one job.
- **No comparison baseline**: a number without a prior-period or target comparison can't be judged as good or bad at a glance.
- **Metrics that don't map to a decision**: if a stakeholder can't say what action they'd take differently based on a metric moving, it doesn't belong on their dashboard it may still belong in the drill-down layer.

## Workflow

1. **Identify the audience and the decision(s)** they make using this dashboard not just "reporting on performance" in the abstract.
2. **Select 1–3 north-star metrics** that most directly answer whether things are going well for that audience.
3. **Select 4–8 supporting metrics** that explain movement in the north-star metrics.
4. **Add comparison context** (prior period, target, benchmark) to every top-tier metric.
5. **Push everything else to a drill-down layer** rather than the main view.
6. **Confirm data quality** for every included metric against the underlying analytics setup before finalizing (see **ga4-audit** if GA4-sourced).

## Related Skills

- **client-report-writer**: Narrative reporting layer that often sits on top of this dashboard's data
- **seo-reporting-dashboard**: SEO-specific application of this same audience-first dashboard framework
- **ga4-audit**: Data quality prerequisite for any metric sourced from GA4
- **attribution-model-selector**: Determines how conversion credit is calculated before it appears on a KPI dashboard
