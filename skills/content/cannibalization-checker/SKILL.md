---
name: cannibalization-checker
description: When the user wants to check whether two or more pages on the same site are competing for the same keyword. Also use when the user mentions "keyword cannibalization," "two pages ranking for the same term," or "which page should I consolidate." For the upstream keyword-to-page mapping that prevents this, use keyword-clustering. For rank data this diagnosis often starts from, use rank-tracking-summary.
metadata:
  version: 1.0.0
---

# Content: Cannibalization Checker

Detects when multiple pages on the same site compete for the same query, and recommends whether to consolidate, differentiate, or leave them as-is.

**When invoking**: On first use, briefly explain that cannibalization prevention (clean keyword ownership) is cheaper than cannibalization fixing (consolidation after the fact). On subsequent use, go straight to the check.

## Scope

Diagnosing and resolving existing overlap between owned pages. Not the upfront keyword-to-page assignment that prevents it in the first place (see **keyword-clustering**).

## Detection Method

Run a SERP overlap check for the suspected keyword: if two of the site's own pages appear in the same search results for the same query, that's the clearest signal of cannibalization not just similar topics, but literal competing rankings.

## Decision Matrix

| Condition | Action |
|---|---|
| Two pages target the same keyword and serve identical intent | **Consolidate** merge into one stronger page, 301 redirect the weaker one |
| One page clearly outperforms the other on the same term | **Consolidate toward the winner** redirect the underperformer, don't leave both live |
| Each page ranks for hundreds of distinct keywords beyond the overlapping term | **Keep separate** the overlap is incidental, not a true competition |
| Pages serve genuinely different intents despite similar topic | **Keep separate**, but clarify the differentiation in titles/H1s so both search engines and readers can tell them apart |
| A page is simply off-topic relative to its cluster | Don't delete outright noindex or fold into the correct cluster to preserve any link equity |

## Prevention (the cheaper fix)

The most effective prevention is assigning clear keyword ownership at the clustering stage every keyword maps to exactly one URL before content is written (see **keyword-clustering**). Maintain a tracking sheet of primary keyword → target URL → cluster assignment, and review it quarterly; cannibalization tends to accumulate silently as new content gets published without checking the existing map.

## Workflow

1. Identify the keyword(s) suspected of cannibalization, typically flagged via **rank-tracking-summary** showing two owned URLs trading position.
2. Run the SERP overlap check to confirm both pages actually appear for the same query.
3. Apply the decision matrix to determine consolidate vs. keep-separate.
4. If consolidating: choose the stronger page (by traffic, backlinks, or engagement), merge unique value from the weaker page into it, and 301 redirect.
5. If keeping separate: sharpen title/H1/intent differentiation so the distinction is clear to both readers and search engines.
6. Update the keyword tracking sheet to reflect the resolved ownership.

## Related Skills

- **keyword-clustering**: Upfront prevention via clean keyword-to-page assignment
- **rank-tracking-summary**: Often the first signal that cannibalization is occurring
- **redirect-chain-audit** (technical): Executing the 301 redirect correctly once consolidation is decided
