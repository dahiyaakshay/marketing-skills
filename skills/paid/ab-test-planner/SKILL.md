---
name: ab-test-planner
description: When the user wants to design a structured A/B test for ads, landing pages, or CRO experiments. Also use when the user mentions "A/B test," "split test," or "how do I test this properly." For the funnel diagnosis that often precedes deciding what to test, use conversion-funnel-analysis (analytics category).
metadata:
  version: 1.0.0
---

# Paid: A/B Test Planner

Designs a structured test one clear hypothesis, one clear variable, a defined sample size and duration rather than an ad-hoc "let's try this and see" comparison that can't produce a reliable conclusion.

**When invoking**: On first use, briefly note the single-variable principle below. On subsequent use, go straight to the test design.

## Scope

Test design and structure. For diagnosing where in a funnel a test is even needed, see **conversion-funnel-analysis** (analytics category).

## Core Test Design Principles

| Principle | Why |
|---|---|
| **One variable per test** | Testing multiple changes simultaneously (new headline + new image + new CTA all at once) makes it impossible to attribute the result to any single change |
| **Clear, falsifiable hypothesis** | State the expected outcome and why, before running the test ("Changing the CTA from 'Submit' to 'Get My Free Quote' will increase conversion rate because it's more specific and lower-commitment-sounding") this prevents post-hoc rationalization of whatever result comes out |
| **Adequate sample size** | Low-traffic pages/campaigns need a longer test duration or a bigger expected effect size to reach statistical confidence running a test on low volume and calling a result early is one of the most common CRO mistakes |
| **Fixed test duration decided in advance** | Stopping a test as soon as it looks like it's "winning" (rather than at the pre-planned sample size/duration) inflates the risk of a false positive |
| **Account for external variability** | Day-of-week and seasonal effects can distort a short test running a test across at least one full weekly cycle helps average these out |

## Workflow

1. Identify the specific variable to test, informed by a diagnosed problem (e.g. from **conversion-funnel-analysis** or **content-optimizer**).
2. Write a clear, falsifiable hypothesis before designing the variants.
3. Create exactly one variant differing by the single variable being tested.
4. Estimate required sample size/duration given current traffic volume, and commit to that duration in advance.
5. Run the test for the full planned duration, resisting the urge to call it early based on an early lead.
6. Analyze results against the original hypothesis, and document the outcome (including failed hypotheses) to build an institutional testing record.

## Related Skills

- **conversion-funnel-analysis** (analytics): Diagnoses where testing effort is likely to pay off
- **landing-page-cro-audit**: Structural audit that often generates test hypotheses
- **ppc-ad-copy-writer**: Common subject of ad-copy A/B tests
