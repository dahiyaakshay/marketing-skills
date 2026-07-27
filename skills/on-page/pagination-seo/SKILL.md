---
name: pagination-seo
description: When the user wants to handle SEO for paginated content (category pages, blog archives, product listings spanning multiple pages). Also use when the user mentions "pagination SEO," "page 2 not ranking," or "rel=next/prev." For canonical tag mechanics generally, use canonical-tag-strategy.
metadata:
  version: 1.0.0
---

# On-Page: Pagination SEO

Handles SEO for content split across multiple paginated pages (page 1, 2, 3... of a category, archive, or product listing) — the goal is ensuring each page in the series is indexable and doesn't compete against the others for the same query.

**When invoking**: On first use, briefly note the self-canonicalization principle below. On subsequent use, go straight to the recommendation.

## Scope

Multi-page series SEO specifically. For general canonical tag mechanics, see **canonical-tag-strategy**.

## Canonicalization for Paginated Series

Each page in a paginated series should typically canonicalize to itself, not all point to page 1 — page 2 and page 3 often contain genuinely distinct products/content, and forcing them to canonicalize to page 1 can prevent that unique content from being indexed at all. The historical `rel="next"/"prev"` link annotation is no longer used by Google as a grouping signal, so self-canonicalization plus clean internal linking between pages is the current best practice.

## Structural Guidance

| Element | Guidance |
|---|---|
| **Self-canonical** | Page 2's canonical tag points to page 2's own URL, not page 1 |
| **Unique title/meta per page** | Include the page number in the title/meta to differentiate ("Category Name - Page 2") rather than identical titles across the series |
| **"View all" alternative** | For shorter series, a single "view all" page can consolidate everything into one indexable URL, avoiding the pagination question entirely — appropriate when the combined content isn't excessively long |
| **Clean internal links** | Direct, crawlable links between pages (not JS-only pagination controls that a non-JS-executing crawler might miss — see **javascript-seo-audit**) |
| **Infinite scroll considerations** | If using infinite scroll, ensure a paginated URL structure exists underneath for crawlability, since crawlers generally don't trigger scroll-based loading |

## Workflow

1. Confirm each page in the paginated series has a self-referencing canonical tag.
2. Differentiate titles/meta descriptions per page with the page number.
3. Confirm pagination links are crawlable HTML links, not JS-only interactions.
4. For shorter series, evaluate whether a "view all" consolidated page is a better fit than pagination at all.
5. If infinite scroll is used for UX, confirm a parallel paginated URL structure exists for crawler access.

## Related Skills

- **canonical-tag-strategy**: General canonical mechanics this specializes for paginated series
- **javascript-seo-audit** (technical): Relevant if pagination controls are JS-dependent
