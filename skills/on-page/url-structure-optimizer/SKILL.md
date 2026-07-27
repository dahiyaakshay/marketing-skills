---
name: url-structure-optimizer
description: When the user wants to design or fix URL slug structure. Also use when the user mentions "URL structure," "SEO-friendly URLs," or "should I change this URL." For redirects needed after a URL change, use redirect-chain-audit (technical category).
metadata:
  version: 1.0.0
---

# On-Page: URL Structure Optimizer

Designs clean, descriptive, stable URL structures stability matters as much as descriptiveness, since changing an existing URL always requires a redirect and carries some risk even when done correctly.

**When invoking**: On first use, briefly note the stability-vs-descriptiveness tradeoff below. On subsequent use, go straight to the recommendation.

## Scope

URL slug and path structure design. For the redirect implementation required when changing an existing URL, see **redirect-chain-audit** (technical category) never change a live, indexed URL without a corresponding redirect plan.

## Structural Guidance

| Element | Guidance |
|---|---|
| **Readable words, not parameters** | `/blog/content-marketing-guide` over `/blog?id=4821` — descriptive slugs are more user- and search-engine-friendly |
| **Hyphens, not underscores** | Search engines treat hyphens as word separators; underscores are treated as joining characters, potentially merging words together in interpretation |
| **Lowercase only** | Avoids case-sensitivity duplicate-URL issues on servers where `/Page` and `/page` could resolve as different URLs |
| **Reasonable length** | Concise and descriptive; avoid stuffing every possible keyword variant into the slug |
| **Logical hierarchy** | Path structure reflecting actual site architecture (`/category/subcategory/product`) helps both users and crawlers understand context |

## The Stability Principle

An existing, already-indexed URL should only be changed for a strong reason (a rebrand, a significant restructure) every URL change requires a 301 redirect and carries some risk of temporary ranking fluctuation while search engines re-process the change, even when executed correctly. "This URL could be slightly more optimal" is rarely sufficient justification on its own to change a URL that's already performing well; the marginal SEO gain from a slightly better slug is often smaller than the risk of the change itself.

## Workflow

1. For new content, design the URL slug using descriptive words, hyphens, lowercase, and a logical path reflecting site hierarchy.
2. For existing URLs being evaluated for change, weigh the marginal benefit of the new structure against the redirect risk and effort.
3. If changing an existing URL, plan the 301 redirect before publishing the change, never after.
4. Update internal links to point to the new URL directly rather than relying on the redirect internally.
5. Monitor rankings and traffic for the affected page for several weeks after any URL change.

## Related Skills

- **redirect-chain-audit** (technical): Required implementation whenever an existing URL changes
- **title-tag-optimizer**: URL slug and title tag should generally align on the core keyword
