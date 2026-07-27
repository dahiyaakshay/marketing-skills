---
name: canonical-tag-strategy
description: When the user wants to decide or fix canonical tag implementation to resolve duplicate content. Also use when the user mentions "canonical tag," "rel=canonical," or "duplicate content issue." For resolving cannibalization between genuinely distinct pages, use cannibalization-checker (content category).
metadata:
  version: 1.0.0
---

# Technical: Canonical Tag Strategy

Implements `rel="canonical"` to tell search engines which version of a page is the authoritative one when multiple URLs serve substantially the same content distinct from **cannibalization-checker**, which addresses two genuinely different pages competing for the same keyword.

**When invoking**: On first use, briefly clarify the canonical-vs-cannibalization distinction below. On subsequent use, go straight to implementation.

## Scope

Duplicate/near-duplicate URL consolidation via canonical tags. For two distinct pages targeting the same keyword (not duplicates of each other), see **cannibalization-checker** (content category) that's a content/keyword-mapping problem, not a canonical-tag problem.

## When Canonical Tags Are the Right Tool

| Situation | Canonical target |
|---|---|
| URL parameter variants (sort, filter, session ID) of the same page | The clean, parameter-free version |
| HTTP vs. HTTPS, www vs. non-www duplicates | The single preferred protocol/subdomain version |
| Print-friendly or AMP versions of a page | The primary standard version |
| Syndicated content republished elsewhere | The original publishing source |
| Paginated series (see **pagination-seo**) | Each page typically self-canonicals, not all pointing to page 1 |

## Common Mistakes

- **Canonicalizing to a page that itself redirects or 404s**: creates a broken signal chain always confirm the canonical target returns a clean 200 status.
- **Conflicting signals between canonical tag and sitemap/internal links**: if internal links and the sitemap point to a different URL than the canonical tag declares, the mixed signal weakens confidence in either.
- **Self-referencing canonical missing on the "correct" page**: every indexable page should include a canonical tag pointing to itself by default, not only the pages considered duplicates.
- **Using canonical tags to fix genuine cannibalization**: if two pages have real content differences and just happen to compete for the same term, the fix is content strategy (see **cannibalization-checker**), not forcing one to canonicalize to the other and losing that content's value.

## Workflow

1. Identify sets of URLs serving substantially duplicate content (parameter variants, protocol/subdomain duplicates, syndicated copies).
2. Determine the single authoritative version for each set.
3. Implement self-referencing canonical tags on all indexable pages by default.
4. Implement cross-referencing canonical tags on duplicate variants, pointing to the authoritative version.
5. Confirm the canonical target returns a clean 200 status, not a redirect or error.
6. Cross-check that internal links and the sitemap consistently point to the canonical version, not the duplicate.

## Related Skills

- **cannibalization-checker** (content): The correct tool for genuinely distinct pages competing for the same keyword
- **redirect-chain-audit**: Related consolidation tool when duplicates should be fully merged rather than just canonicalized
- **pagination-seo**: Specific canonical handling for paginated series
