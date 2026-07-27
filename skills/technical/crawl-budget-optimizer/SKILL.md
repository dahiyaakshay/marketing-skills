---
name: crawl-budget-optimizer
description: When the user wants to ensure search engine crawlers spend their limited crawl attention on the most valuable pages. Also use when the user mentions "crawl budget," "crawl efficiency," or "important pages aren't being crawled/indexed." For robots.txt implementation, use robots-txt-generator. For content worth removing entirely, use content-pruning-audit (content category).
metadata:
  version: 1.0.0
---

# Technical: Crawl Budget Optimizer

Directs a search engine's limited crawl attention toward the pages that matter most — crawl budget is finite, especially for large sites, and pages competing for that attention with low-value URLs can go unindexed or infrequently recrawled as a result.

**When invoking**: On first use, briefly note that this is primarily a large-site concern. On subsequent use, go straight to the optimization plan.

## Scope

Crawl efficiency and prioritization, primarily relevant for large sites (typically tens of thousands of pages or more, where crawl budget is a genuine constraint). For small sites, crawl budget is rarely the bottleneck — focus there on **technical-seo-audit** basics instead. For blocking low-value paths, see **robots-txt-generator**; for removing genuinely low-value content, see **content-pruning-audit** (content category).

## What Wastes Crawl Budget

| Waster | Why it matters |
|---|---|
| **Faceted navigation / filter URLs** | Can generate a combinatorial explosion of near-duplicate URLs (color × size × price-range permutations) that consume crawl attention without adding unique indexable value |
| **Thin, low-value pages** | Pages with little unique content still get crawled at the expense of pages that matter more |
| **Redirect chains** | Each additional hop consumes crawl attempts before the crawler reaches content worth indexing (see **redirect-chain-audit**) |
| **Server response time/errors** | Slow or error-prone server responses cause crawlers to reduce their crawl rate for the site overall, compounding the budget problem |
| **Orphaned or deeply-nested pages** | Pages many clicks deep from the homepage receive disproportionately less crawl attention regardless of their actual value |

## Prioritization Levers

- **Robots.txt exclusions** for genuinely non-valuable paths (see **robots-txt-generator**) — the most direct lever for reducing wasted crawl attempts on faceted/filter URLs.
- **Internal linking depth** (see **internal-linking-strategy**, on-page category) — pages linked closer to the homepage and from high-authority pages tend to receive more frequent crawl attention.
- **XML sitemap prioritization** — ensuring the sitemap accurately reflects the most important, canonical URLs (see **xml-sitemap-builder**).
- **Server performance** — faster, more reliable server responses directly support a higher sustained crawl rate.

## Workflow

1. Confirm this is genuinely a crawl-budget-constrained site (large URL count, or evidence in Search Console of pages "discovered, not indexed").
2. Identify the biggest sources of low-value crawl volume — typically faceted navigation and thin/duplicate content.
3. Apply robots.txt exclusions to the highest-volume, lowest-value URL patterns.
4. Check internal linking depth for genuinely important pages that may be under-linked and therefore under-crawled.
5. Confirm server response times and error rates aren't independently suppressing crawl rate.
6. Re-check Search Console crawl stats after changes to confirm crawl attention has shifted toward the intended pages.

## Related Skills

- **robots-txt-generator**: Primary implementation tool for excluding low-value crawl paths
- **content-pruning-audit** (content): Removing genuinely low-value pages rather than just deprioritizing them
- **redirect-chain-audit**: Chains that consume crawl attempts unnecessarily
- **internal-linking-strategy** (on-page): Link depth's effect on crawl prioritization
