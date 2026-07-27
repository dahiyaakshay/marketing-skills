---
name: conversion-funnel-analysis
description: When the user wants to analyze where users drop off between landing and converting. Also use when the user mentions "funnel analysis," "drop-off rate," "cart abandonment," "checkout completion rate," "where are we losing users," or "funnel benchmark." For fixing the underlying analytics setup this depends on, use ga4-audit. For which channel gets credit for the eventual conversion, use attribution-model-selector. For CRO test design once a drop-off point is identified, use ab-test-planner (paid category).
metadata:
  version: 1.0.0
---

# Analytics: Conversion Funnel Analysis

Breaks a multi-step conversion path into stages, identifies which stage has the highest drop-off, and distinguishes genuinely fixable friction from expected, unrecoverable attrition (browsers who were never going to buy). The core discipline here is stage-level diagnosis — a single overall conversion rate tells you almost nothing about where to act.

**When invoking**: On first use, briefly explain why stage-level breakdown matters more than the headline conversion rate. On subsequent use, go straight to the analysis.

## Scope

Covers funnel-stage breakdown and benchmarking. Does not cover the analytics configuration this depends on (see **ga4-audit**), attribution of which channel drove the visit (see **attribution-model-selector**), or the actual test design to fix an identified leak (see **ab-test-planner**).

## Why Overall Conversion Rate Misleads

A single blended conversion-rate number hides more than it reveals: a low overall rate with a healthy add-to-cart rate points specifically to checkout friction, while a low add-to-cart rate points to a product-page or merchandising problem — the same headline number can have entirely different root causes and entirely different fixes. Always segment by funnel stage, device, and traffic source before drawing conclusions from an aggregate rate.

## Typical E-commerce Funnel Benchmarks (2026, directional only)

| Stage | Typical range | What a low number signals |
|---|---|---|
| Visit → Add-to-cart | Roughly 6–7.5% average, with well-optimized stores well above that | Landing/product page problem — the largest single drop in most funnels happens before add-to-cart, meaning the majority of visitors never even try the product |
| Add-to-cart → Checkout start | Often a 50–60% drop at this exact transition | An under-examined leak — many teams focus checkout optimization on the payment step and overlook this earlier one |
| Checkout start → Purchase | Roughly 45–50% of users who start checkout abandon before completing, across recent large-sample studies | Checkout friction — payment options, unexpected costs, form length, trust signals |

These figures vary meaningfully by industry, AOV, device, and traffic source, and different research firms report different numbers depending on methodology — treat any single published benchmark as directional, and always benchmark against the property's own historical baseline as the primary comparison point, not an external average.

## Segmentation Is Not Optional

Benchmarks are only actionable once segmented by channel, device, and visitor type — a blended average across a paid-social-driven mobile audience and an organic-search-driven desktop audience will misrepresent both. Referral and affiliate traffic, for instance, tends to convert meaningfully higher than average because visitors arrive pre-qualified by a third-party endorsement; folding that traffic into a blended rate obscures both the strength of that channel and the weakness of others.

## Sample Size Caution

Low-traffic properties should rely more on qualitative signals — session recordings, heatmaps — than on percentage-based funnel metrics, since small sample sizes at each stage make percentage swings look meaningful when they're actually noise. Don't over-interpret a stage-to-stage percentage change unless there's enough volume at each stage for it to be statistically meaningful.

## Workflow

1. **Define the funnel stages** specific to the business (e.g. landing → product view → add-to-cart → checkout start → purchase, or signup form → email verify → onboarding → activation for SaaS).
2. **Pull stage-by-stage conversion rates** from GA4 or the relevant analytics source, confirming the underlying tracking is reliable first (see **ga4-audit** if uncertain).
3. **Identify the single largest percentage drop** between adjacent stages — this is where to focus first, not the stage with the lowest absolute rate.
4. **Segment the largest drop-off** by device, channel, and new-vs-returning visitor to isolate which segment is actually driving the leak.
5. **Distinguish fixable friction from expected attrition** — not every abandonment is recoverable; some portion of any funnel is simply browsers who were never a real prospect.
6. **Recommend the next step**: if the leak is well-understood (e.g. checkout has too many form fields), route to a fix; if the cause is unclear, route to **ab-test-planner** for a structured test rather than guessing.

## Related Skills

- **ga4-audit**: Data quality prerequisite — funnel numbers are only as reliable as the underlying tracking
- **attribution-model-selector**: Channel-level credit assignment, complementary to this skill's stage-level view
- **ab-test-planner**: Structured testing once a drop-off point is identified but the cause isn't obvious
- **landing-page-cro-audit**: Page-level CRO audit for the specific stage identified as the leak
