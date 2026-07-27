---
name: quality-score-optimizer
description: When the user wants to improve Google Ads Quality Score. Also use when the user mentions "Quality Score," "why is my CPC so high," or "improve expected CTR / ad relevance / landing page experience." For negative keyword specifics, use paid-search-keyword-negative-list. For ad copy itself, use ppc-ad-copy-writer.
metadata:
  version: 1.0.0
---

# Paid: Quality Score Optimizer

Diagnoses and improves Google Ads Quality Score by addressing its three component ratings individually Quality Score directly affects cost-per-click and ad rank, so a below-average component is often the highest-leverage fix available in an underperforming account.

**When invoking**: On first use, briefly note the three-component breakdown below. On subsequent use, go straight to diagnosis.

## Scope

Quality Score diagnosis and improvement. For the negative keyword mechanics that indirectly support this, see **paid-search-keyword-negative-list**. For the ad copy itself, see **ppc-ad-copy-writer**.

## The Three Components

| Component | What it measures | Primary lever |
|---|---|---|
| **Expected CTR** | The likelihood a given ad will be clicked when shown for a keyword, relative to what's typical | Ad copy specificity, negative keywords removing irrelevant impressions, and match type tighter match types (phrase/exact) generally support higher expected CTR ratings than broad match, since query-to-ad alignment is inherently closer |
| **Ad relevance** | Whether the ad directly addresses the intent behind the triggering keyword | Tighter ad group structure grouping closely related keywords together so ad copy can speak directly to them, rather than one broad ad group covering loosely related terms |
| **Landing page experience** | Whether the destination page is relevant, useful, transparent, and reasonably fast for the query | Landing page content directly matching the ad's promise, load speed, and clear navigation/information |

## Prioritization

Check the per-keyword component ratings for the lowest-performing keywords first, and focus initial effort on whichever component is rated "Below Average" specifically that's typically where the fastest, most direct improvement is available, rather than spreading effort evenly across all three components regardless of which is actually weak.

## Fixes by Component

- **Expected CTR weak**: audit ad copy for genuine specificity (numbers, concrete pain points, urgency) rather than generic corporate messaging; add negative keywords to prevent irrelevant impressions that drag down CTR without generating valuable clicks; reconsider whether broad match is appropriate for underperforming keywords.
- **Ad relevance weak**: restructure ad groups to tighten keyword-to-ad-copy alignment move broad, loosely-related keywords into their own more targeted ad group rather than sharing one generic ad across many keyword variants.
- **Landing page experience weak**: confirm the landing page content genuinely matches what the ad promises, check page load speed (see **core-web-vitals-audit**, technical category), and ensure the page isn't misleading or difficult to navigate.

## Workflow

1. Pull per-keyword Quality Score component ratings for the account's lowest performers.
2. Identify which component (expected CTR, ad relevance, landing page experience) is rated "Below Average" for each.
3. Apply the matching fix from the list above, prioritizing the weakest component first.
4. Re-check ratings after changes have had time to accumulate enough impression/click data to update.

## Related Skills

- **paid-search-keyword-negative-list**: Supports expected CTR indirectly by removing irrelevant impressions
- **ppc-ad-copy-writer**: Direct lever for both expected CTR and ad relevance
- **landing-page-cro-audit**: Direct lever for landing page experience
