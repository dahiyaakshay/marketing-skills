---
name: schema-markup-generator
description: When the user wants to select and implement schema.org structured data for a page type. Also use when the user mentions "schema markup," "structured data," or "which schema should I use." For validating already-implemented markup, use structured-data-validator (technical category). For local business schema specifically, use local-schema-markup (local category). For AI-citation-specific schema priorities, use answer-engine-schema (geo category).
metadata:
  version: 1.0.0
---

# On-Page: Schema Markup Generator

Selects and implements the correct schema.org type for a given piece of content the goal is matching schema precisely to what the content actually is, since an incorrect or overly generic schema type forfeits rich-result eligibility the content might otherwise qualify for.

**When invoking**: On first use, briefly confirm the content type before recommending a schema. On subsequent use, go straight to generating the markup.

## Scope

Schema type selection and initial implementation across content types generally. For validation of already-implemented markup, see **structured-data-validator** (technical category). For local-business-specific schema, see **local-schema-markup** (local category). For AI-citation-specific schema prioritization, see **answer-engine-schema** (geo category).

## Common Schema Types by Content

| Content type | Schema type | Key properties |
|---|---|---|
| Blog post / article | Article, BlogPosting | headline, author, datePublished, dateModified, image |
| Product page | Product | name, image, offers (price, availability), aggregateRating |
| FAQ content | FAQPage | mainEntity with Question/Answer pairs |
| How-to guide | HowTo | step-by-step structure, estimated time/cost if relevant |
| Recipe | Recipe | ingredients, instructions, cookTime, nutrition |
| Event | Event | startDate, location, offers |
| Review/comparison content | Review | itemReviewed, reviewRating, author |
| Organization/brand identity | Organization | name, logo, sameAs (links to verified profiles) |

## Selection Principle

Choose the most specific applicable schema type over a more generic one a Recipe page should use Recipe schema, not just generic Article schema, since the more specific type unlocks richer, more relevant result formatting and signals clearer content identity to both search engines and AI systems.

## Workflow

1. Identify the actual content type of the page being marked up.
2. Select the most specific applicable schema type from schema.org's vocabulary, not just the most familiar or generic one.
3. Populate all required properties for that type, plus recommended properties where the data genuinely exists.
4. Ensure every schema value matches the visible page content exactly.
5. Hand off to **structured-data-validator** for syntax and completeness validation before publishing.

## Related Skills

- **structured-data-validator** (technical): Validation and error-checking of the implemented markup
- **local-schema-markup** (local): Local-business-specific schema
- **answer-engine-schema** (geo): AI-citation-specific schema priorities
- **faq-schema-builder**: Deeper, dedicated treatment of FAQPage schema specifically
