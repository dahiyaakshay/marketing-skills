---
name: ga4-audit
description: When the user wants to audit an existing Google Analytics 4 property for configuration errors, data quality issues, or unreliable reporting. Also use when the user mentions "GA4 audit," "is my GA4 set up correctly," "GA4 data looks wrong," "data retention," "why don't my conversions match," or "GA4 health check." For attribution model selection specifically, use attribution-model-selector. For building dashboards on top of clean GA4 data, use seo-reporting-dashboard or kpi-dashboard-builder. For funnel-specific analysis, use conversion-funnel-analysis.
metadata:
  version: 1.0.0
---

# Analytics: GA4 Audit

Systematically inspects a GA4 property for the configuration errors that silently distort reporting the kind that don't throw an error, they just quietly make every downstream report and decision wrong. Independent audits across many B2B properties have found a large majority contain at least one critical configuration error actively distorting conversion data, so treat "the setup is probably fine" as the wrong starting assumption.

**When invoking**: On first use, briefly note that audits should happen on a recurring cadence, not just once. On subsequent use, go straight to the checklist output.

## Scope

Covers GA4 property configuration, data collection integrity, and cross-platform alignment (GA4 ↔ Google Ads ↔ Search Console). Does not cover attribution model selection (see **attribution-model-selector**), funnel-stage drop-off analysis (see **conversion-funnel-analysis**), or dashboard/report building on top of already-clean data (see **seo-reporting-dashboard**, **kpi-dashboard-builder**).

## Audit Checklist — 6 Categories

| Category | What to check | Why it matters |
|---|---|---|
| **Data stream & collection** | Stream status shows "Receiving data"; correct Measurement ID (G-XXXXXXX) matches the tag on the live site; Enhanced Measurement enabled | A wrong Measurement ID sends data to the wrong property entirely; without Enhanced Measurement you silently lose scroll tracking, outbound clicks, site search, video engagement, and file downloads |
| **Conversions & key events** | Key events correctly marked; no duplicate event firing; event parameters populated | Duplicate firing inflates conversion counts; missing parameters break downstream segmentation |
| **Data retention & privacy** | Data retention window set (default is only 2 months); Consent Mode v2 configured if serving EU/regulated traffic | GA4's default event/user data retention is 2 months after that window, raw event data needed for custom explorations or audience building is permanently gone; this is the single most common "silent" misconfiguration and should be changed to the maximum available window immediately upon setup |
| **Attribution & cross-platform linking** | GA4 ↔ Google Ads linked; GA4 ↔ Search Console linked; consistent UTM tagging across campaigns | Misaligned linking fragments reporting so paid and organic performance appear disconnected, and can cause Google Ads to optimize bidding against the wrong signal if imported conversions are misconfigured |
| **Data quality & filters** | Internal traffic filter active; bot filtering enabled; no double-counted sessions from cross-domain tracking gaps | Unfiltered internal/agency traffic and bot traffic silently inflate every top-line number |
| **Audiences & segments** | Audiences built on correctly-scoped conditions; segment definitions match current event schema | Audiences built against deprecated or renamed events silently stop populating |

## Anomaly Detection as a Standing Practice

Beyond a one-time configuration check, review historical and current data for sudden spikes, unexplained drops, or persistent inconsistencies on a recurring basis these are usually the visible symptom of an underlying implementation error, an unaccounted-for traffic source, or a data collection failure, and catching them early prevents months of decisions being made on bad data. Re-run the full checklist at minimum quarterly, and always after a site relaunch, major template change, new subdomain, or CMP/consent-banner change, since tracking tends to break unnoticed around exactly those events.

## Workflow

1. **Confirm access** to GA4 Admin and, if available, the linked BigQuery export (BigQuery gives event-level data quality visibility the UI alone doesn't).
2. **Work the 6-category checklist in order** start with data stream & collection, since if that's broken nothing downstream matters.
3. **Flag critical vs. cosmetic issues** separately: retention window, wrong Measurement ID, and unlinked Ads/Search Console are critical; naming convention inconsistencies are cosmetic but still worth listing.
4. **Check for silent DDA fallback**: if data-driven attribution is selected but conversion volume for a key event is below GA4's threshold, GA4 falls back to last-click without notifying the user compare the Model Comparison report; if data-driven and last-click numbers are identical, DDA isn't actually active.
5. **Document findings** as a plain-English action list: issue, why it matters, exact fix location (Admin path), priority.
6. **Recommend a recurring audit cadence** rather than treating this as a one-time deliverable.

## Related Skills

- **attribution-model-selector**: Choosing between GA4's two remaining attribution models once the property itself is clean
- **conversion-funnel-analysis**: Stage-by-stage drop-off analysis, a downstream use of clean GA4 data
- **traffic-anomaly-detector**: Ongoing spike/drop monitoring vs. this skill's one-time/periodic configuration audit
- **seo-reporting-dashboard**, **kpi-dashboard-builder**: Reporting layers built on top of an already-audited property
- **utm-tracking-setup**: Campaign tagging consistency that this audit checks but doesn't itself configure
