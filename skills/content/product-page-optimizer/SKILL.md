---
name: product-page-optimizer
description: When the user wants to write or optimize an e-commerce product page. Also use when the user mentions "product page copy," "product description," or "optimize this product listing." For category/collection-level pages, use category-page-writer. For pricing-specific pages, use pricing-page-optimizer.
metadata:
  version: 1.0.0
---

# Content: Product Page Optimizer

Writes or optimizes a single product page for both conversion (does this convince a buyer) and findability (can search engines and AI shopping surfaces understand and cite it accurately).

**When invoking**: On first use, confirm whether the task is a new draft or an audit of an existing page. On subsequent use, go straight to the output.

## Scope

Single product page copy and structure. Not category/collection pages (see **category-page-writer**) or pricing-page-specific concerns (see **pricing-page-optimizer**).

## Required Elements

| Element | Guidance |
|---|---|
| **Title** | Product name + the 1–2 attributes buyers actually search on (size, material, use case) |
| **Description** | Lead with the primary benefit/use case, not a spec dump; specs belong in a separate structured section |
| **Structured specs** | Table or list format — scannable and machine-parseable, both for search engines and AI shopping assistants |
| **Images/alt text** | Descriptive alt text naming the product and key visible attribute, not just the filename |
| **Reviews/social proof** | Visible rating and review count near the top, full reviews further down |
| **Structured data (schema)** | Product schema with price, availability, and rating so the page is eligible for rich results |
| **Cross-sell/related products** | Placed after the primary conversion elements, not competing with them above the fold |

## Workflow

1. Confirm the product's primary use case and the buyer's likely search intent (informational research vs. ready-to-buy).
2. Draft or revise the description to lead with benefit, specs second.
3. Structure specs in a scannable table/list.
4. Check image alt text and confirm product schema markup is present and accurate.
5. Verify reviews/ratings are surfaced prominently.
6. Hand off to **content-optimizer** for a final scoring pass if SEO performance is the concern, or **landing-page-cro-audit** if conversion is the primary concern.

## Related Skills

- **category-page-writer**: Collection-level page, one level up from this single-product scope
- **pricing-page-optimizer**: Dedicated pricing-page concerns beyond a single product listing
- **schema-markup-generator** (on-page): Product schema implementation detail
