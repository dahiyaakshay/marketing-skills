---
name: local-schema-markup
description: When the user wants to implement LocalBusiness structured data for a business or location. Also use when the user mentions "local schema," "LocalBusiness markup," or "structured data for my location." For general (non-local) schema types, use schema-markup-generator (on-page category).
metadata:
  version: 1.0.0
---

# Local: Local Schema Markup

Implements LocalBusiness (and relevant subtype) structured data so search engines and AI systems can extract accurate, structured location, hours, and business details directly from the page.

**When invoking**: On first use, confirm the correct LocalBusiness subtype for the business category. On subsequent use, go straight to implementation.

## Scope

LocalBusiness-specific schema. For general (non-local) schema types, see **schema-markup-generator** (on-page category).

## Required Properties

| Property | Guidance |
|---|---|
| **name, address, telephone** | Must exactly match the canonical NAP established in **local-citation-audit** — mismatches between schema and visible page content undermine trust in the markup |
| **LocalBusiness subtype** | Use the most specific applicable subtype (e.g. Restaurant, Dentist, Plumber) rather than the generic LocalBusiness type where a more specific one exists — specificity aids relevance matching the same way GBP category specificity does |
| **openingHours** | Structured, current hours — inconsistent or outdated hours in schema versus what's shown on GBP creates a trust discrepancy |
| **geo (latitude/longitude)** | Supports accurate map and proximity-based display |
| **priceRange, servesCuisine, or category-specific properties** | Populate any subtype-specific properties available, since these add relevance signal beyond the base LocalBusiness fields |
| **aggregateRating / review** | If displaying reviews on-page, mark them up so they're eligible for rich results, using only genuine review data |

## Consistency Is the Priority

Every value in the schema must match what's visibly on the page and consistent with the GBP listing and directory citations — schema that contradicts visible content or other verified business data is a red flag rather than a ranking boost, since it signals a broken or manipulated data source rather than a trustworthy one.

## Workflow

1. Confirm the canonical NAP and hours from **gbp-optimizer**/**local-citation-audit**.
2. Select the most specific applicable LocalBusiness subtype.
3. Implement all core and subtype-specific properties with values matching the canonical data exactly.
4. Validate the markup with a structured data testing tool.
5. Re-verify consistency any time hours, address, or contact details change anywhere else.

## Related Skills

- **schema-markup-generator** (on-page): General schema mechanics this specializes for local business
- **local-citation-audit**: Canonical NAP source this schema must match
- **local-landing-page-builder**: The page this schema is typically embedded in
