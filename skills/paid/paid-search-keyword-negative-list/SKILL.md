---
name: paid-search-keyword-negative-list
description: When the user wants to build or audit a negative keyword list for paid search campaigns. Also use when the user mentions "negative keywords," "search terms report," or "wasted ad spend on irrelevant queries." For match type selection more broadly, cross-reference ppc-ad-copy-writer for ad-to-keyword alignment. For Quality Score impact, use quality-score-optimizer.
metadata:
  version: 1.0.0
---

# Paid: Negative Keyword List Builder

Builds and maintains negative keyword lists to prevent ad spend on irrelevant queries increasingly important as match types have become fuzzier (broad match now captures synonyms and related-intent searches well beyond its historical scope) and as AI Overviews absorb a growing share of informational search volume, shifting the composition of remaining paid auction traffic.

**When invoking**: On first use, briefly note why negatives matter more now than a few years ago. On subsequent use, go straight to building/auditing the list.

## Scope

Negative keyword strategy and list building. For ad-copy-to-keyword relevance (a related Quality Score input), see **ppc-ad-copy-writer**. For the Quality Score mechanics negatives indirectly influence, see **quality-score-optimizer**.

## Why Negatives Matter More in 2026

Match types have become progressively fuzzier broad match, now often the default under automated bidding, can trigger on synonyms and same-intent searches well beyond the literal keyword, and Google's AI Overviews are absorbing a meaningful share of purely informational search volume, changing the composition of what remains in the paid auction. Both trends mean more irrelevant queries entering auctions than in previous years, making a disciplined, current negative keyword list a more active lever than it used to be not a "set once" task.

## Building the List

| Source | What to look for |
|---|---|
| **Search terms report** | Sort by cost, review every query with zero conversions or a cost-per-acquisition well above the account average |
| **Pre-launch exclusions** | For new campaigns, a standard list of obvious industry-irrelevant terms (e.g. "free," "jobs," "DIY," "how to" if the business doesn't sell an informational/DIY product) applied before launch, ideally before the campaign enters the automated-bidding learning phase |
| **Ongoing review** | Regular (at least monthly) review of new search terms as they accumulate this should be a standing habit, not a one-time list |

## Level of Exclusion

Add negatives at the narrowest level that prevents the specific waste without blocking genuinely related traffic an overly broad negative can silently exclude valuable, converting queries alongside the irrelevant ones it was meant to catch. Broad negative match applied carelessly is one of the most common ways well-intentioned negative keyword work backfires.

## Why the Pre-Launch Timing Matters

If irrelevant queries are allowed to accumulate spend during a new campaign's early learning phase, automated bidding systems can anchor to that early, noisy signal cleaning up the negative list later doesn't fully undo the effect of the algorithm having learned from bad initial data. A pre-launch negative list, locked in before the campaign starts accumulating conversion history, avoids this problem structurally.

## Workflow

1. For new campaigns, compile a pre-launch negative list covering obvious industry-irrelevant terms before the campaign goes live.
2. For running campaigns, pull the search terms report sorted by cost.
3. Flag every query with zero conversions or well-above-average cost-per-acquisition.
4. Add negatives at the narrowest level that excludes the specific waste without catching related, valid traffic.
5. Repeat this review at least monthly as a standing practice, not a one-time cleanup.

## Related Skills

- **quality-score-optimizer**: Negatives indirectly improve Quality Score by improving overall CTR, not as a direct scoring input
- **ppc-ad-copy-writer**: Tighter ad-to-keyword alignment reduces reliance on negatives as the sole relevance lever
