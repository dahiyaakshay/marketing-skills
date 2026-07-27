---
name: answer-engine-schema
description: When the user wants to implement structured data specifically to support AI answer engine citation, beyond traditional rich-result schema. Also use when the user mentions "answer engine schema," "structured data for AI," or "schema for AI Overviews." For general schema markup implementation, use schema-markup-generator (on-page category).
metadata:
  version: 1.0.0
---

# GEO: Answer Engine Schema

Implements the specific structured data types that most directly support AI answer engine citation and extraction, as a specialization of general schema markup practice for AI-specific goals.

**When invoking**: On first use, briefly note which schema types matter most for AI citation specifically. On subsequent use, go straight to implementation.

## Scope

AI-citation-specific schema selection and priority. For general schema implementation mechanics across all schema types, see **schema-markup-generator** (on-page category).

## Priority Schema Types for AI Citation

| Schema type | Why it matters for AI citation |
|---|---|
| **FAQPage** | Directly matches the question-answer extraction pattern AI systems favor explicit machine-readable Q&A pairs |
| **HowTo** | Structures step-based content in a format that's naturally extractable as a self-contained procedure |
| **Article / NewsArticle** | Signals authorship, publish/update date, and publisher feeding directly into freshness and E-E-A-T signals |
| **Organization / Person** | Supports entity clarity and disambiguation (see **entity-density-optimizer**) |
| **Product** | Supports structured extraction of price, availability, and rating for product-related queries |

Explicit schema markup has been associated with a meaningfully higher citation selection rate compared to equivalent unmarked content, reinforcing that structured data is not just a traditional-search rich-result tactic it's directly relevant to AI extraction as well.

## Workflow

1. Identify the highest-priority pages for AI citation (per **geo-competitive-benchmark** or existing traffic value).
2. Select the schema type(s) matching the content's actual structure don't force FAQPage schema onto content that isn't genuinely question-and-answer formatted.
3. Implement the schema with complete, accurate properties (not placeholder or thin data).
4. Validate the markup with a structured data testing tool before publishing.
5. Pair schema implementation with the content-level structural work from **ai-citation-optimization** schema alone doesn't substitute for genuinely well-structured prose.

## Related Skills

- **schema-markup-generator** (on-page): General schema implementation mechanics
- **ai-citation-optimization**: Content-level structure this schema should reinforce, not replace
- **entity-density-optimizer**: Entity schema specifically supports this skill's entity-clarity goals
