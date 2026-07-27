---
name: utm-tracking-setup
description: When the user wants to set up or standardize UTM parameter tracking for campaigns. Also use when the user mentions "UTM parameters," "campaign tracking setup," or "why doesn't my campaign show up correctly in GA4." For the underlying GA4 configuration this depends on, use ga4-audit (analytics category).
metadata:
  version: 1.0.0
---

# Paid: UTM Tracking Setup

Standardizes UTM parameter conventions across campaigns so channel/campaign performance data in analytics platforms is consistent and comparable, rather than fragmented by inconsistent naming.

**When invoking**: On first use, briefly note the consistency-over-cleverness principle below. On subsequent use, go straight to setting the convention.

## Scope

UTM parameter naming convention and application. For the underlying GA4 configuration this data feeds into, see **ga4-audit** (analytics category).

## The Five UTM Parameters

| Parameter | Purpose | Example |
|---|---|---|
| `utm_source` | The referring platform | google, facebook, newsletter |
| `utm_medium` | The marketing channel type | cpc, email, social, referral |
| `utm_campaign` | The specific campaign name | spring_sale_2026 |
| `utm_term` | Paid search keyword (optional, often auto-populated) | running_shoes |
| `utm_content` | Differentiates similar content/ads within the same campaign (optional) | headline_a vs headline_b |

## Consistency Principles

- **Fixed casing convention** (all lowercase is the standard recommendation) — GA4 treats UTM values as case-sensitive, so "Google" and "google" register as two separate sources, fragmenting reporting.
- **A documented naming reference sheet** — every person setting up campaigns should reference the same source/medium/campaign naming list, rather than each person inventing their own naming pattern.
- **Consistent separators** (underscore vs. hyphen) applied uniformly across all campaign names, not mixed.
- **utm_medium values matching GA4's default channel groupings** where possible (e.g. using "cpc" rather than an idiosyncratic value) so campaigns are correctly bucketed into GA4's default channel reports rather than falling into "unassigned" or a mismatched channel.

## Why Fragmentation Happens

The most common failure is inconsistent casing or naming across team members or over time — "Newsletter" vs. "newsletter" vs. "email_newsletter" for what should be the same source fragments what should be one clean channel into three separate rows in every report, understating the channel's true performance and making trend analysis unreliable.

## Workflow

1. Establish or confirm the documented naming convention (casing, separators, standard source/medium values).
2. Build UTM links for all planned campaigns using the standardized convention, not ad hoc per-campaign naming.
3. Validate that new campaign UTMs are correctly bucketed into GA4's expected channel groupings before launch.
4. Periodically audit live UTM usage across the team for drift from the documented convention.
5. Cross-check with **ga4-audit** (analytics category) to confirm the underlying property configuration supports accurate attribution of this tagged traffic.

## Related Skills

- **ga4-audit** (analytics): Underlying property configuration this tracking data feeds
- **attribution-model-selector** (analytics): How credit is assigned to the campaigns this tracking identifies
