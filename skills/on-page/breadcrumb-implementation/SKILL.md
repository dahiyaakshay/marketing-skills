---
name: breadcrumb-implementation
description: When the user wants to implement breadcrumb navigation and its structured data. Also use when the user mentions "breadcrumbs," "breadcrumb schema," or "breadcrumb navigation." For the broader site hierarchy this reflects, use internal-linking-strategy.
metadata:
  version: 1.0.0
---

# On-Page: Breadcrumb Implementation

Implements breadcrumb navigation and the corresponding BreadcrumbList schema so the site's hierarchical structure is clear to both users and search engines, and eligible for the breadcrumb-trail rich result in search listings.

**When invoking**: On first use, briefly confirm the site's actual hierarchy before implementing. On subsequent use, go straight to implementation.

## Scope

Breadcrumb UI and schema implementation. For the broader internal linking strategy this hierarchy reflects, see **internal-linking-strategy**.

## Structural Guidance

| Element | Guidance |
|---|---|
| **Reflects actual site hierarchy** | Breadcrumbs should mirror the real information architecture (Home > Category > Subcategory > Product), not an arbitrary or aspirational structure that doesn't match the site's actual navigation |
| **BreadcrumbList schema** | Implement alongside the visible breadcrumb trail, matching it exactly mismatched visible breadcrumbs and schema breadcrumbs is a trust/consistency issue |
| **Every level is a working link** | Each breadcrumb level except the current page should link to that actual category/parent page, not just be decorative text |
| **Consistent across the site** | The same hierarchy pattern applied consistently across all pages of a given type, not varying template to template |

## Why This Matters Beyond Navigation

Breadcrumbs give users an easy way to navigate up the hierarchy, which reduces bounce rate on deep pages, and the BreadcrumbList schema makes the page eligible for a breadcrumb trail shown directly in search results instead of the full URL path a small but real click-through improvement in the SERP snippet.

## Workflow

1. Confirm the site's actual information architecture/hierarchy.
2. Implement visible breadcrumb navigation matching that hierarchy on all relevant page templates.
3. Add BreadcrumbList schema matching the visible breadcrumb exactly.
4. Confirm every breadcrumb level (except the current page) is a working, correctly-targeted link.
5. Validate the schema with **structured-data-validator** (technical category).

## Related Skills

- **internal-linking-strategy**: Broader linking strategy this hierarchy is one visible expression of
- **structured-data-validator** (technical): Schema validation
