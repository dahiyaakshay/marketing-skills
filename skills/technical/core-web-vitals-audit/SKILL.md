---
name: core-web-vitals-audit
description: When the user wants to audit or improve a site's Core Web Vitals (LCP, INP, CLS). Also use when the user mentions "Core Web Vitals," "page speed," "LCP," "INP," "CLS," or "Search Console page experience warning." For JavaScript-rendering issues specifically, use javascript-seo-audit. For the broader technical audit this fits into, use technical-seo-audit.
metadata:
  version: 1.0.0
---

# Technical: Core Web Vitals Audit

Diagnoses and prioritizes fixes for Google's three Core Web Vitals Largest Contentful Paint (LCP), Interaction to Next Paint (INP), and Cumulative Layout Shift (CLS) using real-user field data, not just lab scores.

**When invoking**: On first use, briefly explain the field-data-vs-lab-data distinction below. On subsequent use, go straight to the audit.

## Scope

Core Web Vitals diagnosis and fixes specifically. For broader JS-rendering/crawlability issues, see **javascript-seo-audit**. This audit is one component of the full **technical-seo-audit**.

## Thresholds ("Good" Rating)

| Metric | Measures | Good threshold | Poor threshold |
|---|---|---|---|
| **LCP** (Largest Contentful Paint) | Loading speed | Under 2.5 seconds | Above 4.0 seconds |
| **INP** (Interaction to Next Paint) | Responsiveness replaced FID in March 2024 | Under 200 milliseconds | Above 500 milliseconds |
| **CLS** (Cumulative Layout Shift) | Visual stability | Under 0.1 | Above 0.25 |

All three must be in the "good" range at the 75th percentile of real Chrome users, measured over a rolling 28-day window (CrUX data), for a page to pass overall. A perfect Lighthouse (lab) score does not guarantee a passing field-data result if a meaningful share of real visitors have a worse experience than the simulated lab environment assumes.

## Field Data vs. Lab Data

Google's ranking assessment uses field data (CrUX real Chrome users), not lab data (Lighthouse/PageSpeed Insights simulations). Lab tools are diagnostic they explain *why* something is slow but the number that actually counts for ranking is the real-user 75th-percentile figure. Treat a good Lighthouse score with real-user field data still failing as unresolved; don't stop at the lab score.

## Fix Patterns by Metric

| Metric | Common fixes |
|---|---|
| **LCP** | Image preloading and compression, critical CSS inlining, font preloading with `font-display: swap`, server-side rendering or faster server response times, CDN usage |
| **INP** | Break up long JavaScript tasks, defer non-critical scripts, yield to the main thread during interactions, minimize DOM complexity this metric currently requires the deepest technical/architectural changes of the three and is the one most sites fail |
| **CLS** | Explicit width/height on every image, video, iframe, and ad slot; reserved space for dynamically-injected content; `font-display: swap` to avoid font-swap layout shift |

## Workflow

1. Pull field data from Search Console's Core Web Vitals report or CrUX directly, segmented by mobile and desktop (mobile typically performs worse due to network and processing constraints).
2. Identify which of the three metrics is failing and at what real-user percentile.
3. Run a lab tool (PageSpeed Insights) on the specific failing pages to diagnose root causes.
4. Apply the fix pattern matching the failing metric.
5. Wait for the 28-day CrUX window to reflect the fix before judging results don't revert a good change out of impatience because the dashboard hasn't updated yet.
6. Set proactive alerts at roughly 80% of the "good" threshold (e.g. INP > 160ms) to catch regressions before they fully surface in the 28-day window.

## Related Skills

- **javascript-seo-audit**: JS-rendering issues that often underlie both CLS and INP problems
- **technical-seo-audit**: Broader technical audit this is one component of
- **mobile-first-indexing-check**: Related page-experience audit, since Google indexes and measures CWV primarily from mobile
