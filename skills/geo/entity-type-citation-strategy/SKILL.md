---
name: entity-type-citation-strategy
description: When the user wants strategy differentiated by the type of entity being optimized (brand, individual expert, product, local business). Also use when the user mentions "entity type strategy," "how should a personal brand approach GEO differently than a company," or "citation strategy by entity type." For general entity clarity tactics, use entity-density-optimizer.
metadata:
  version: 1.0.0
---

# GEO: Entity-Type Citation Strategy

Differentiates AI-citation strategy by the type of entity being represented a company, an individual expert, a product, and a local business each have different available corroboration signals and should be optimized differently.

**When invoking**: On first use, ask or confirm which entity type is the focus. On subsequent use, go straight to the type-specific strategy.

## Scope

Entity-type-specific strategic differences. For the general mechanics of entity clarity itself, see **entity-density-optimizer**.

## Strategy by Entity Type

| Entity type | Strongest corroboration signals | Typical gap |
|---|---|---|
| **Company/brand** | Organization schema, consistent naming across owned and third-party profiles, Wikidata/Wikipedia if notable enough | Inconsistent naming across subsidiaries, product lines, or regional sites |
| **Individual expert** | Person schema, consistent author bylines across publications, credentials stated explicitly and consistently, presence on recognized professional platforms | Content published without consistent author attribution, making expertise hard for an AI system to attribute and corroborate |
| **Product** | Product schema, consistent naming/model numbers, presence in comparison and review content across multiple independent sources | Product renamed or rebranded without updating historical mentions, fragmenting the entity signal across old and new names |
| **Local business** | See **local-business-llm-visibility** and **gbp-optimizer** (local category) local entity signals draw heavily on Google Business Profile data specifically | Inconsistent NAP (name/address/phone) data across directories, which fragments local entity confidence |

## Workflow

1. Identify the entity type in focus.
2. Apply the corroboration-signal checklist for that type.
3. Audit for the typical gap associated with that entity type specifically.
4. Cross-reference with **entity-density-optimizer** for the general mechanics of implementation.
5. For local business entities specifically, hand off to the local category skills for GBP-specific work.

## Related Skills

- **entity-density-optimizer**: General entity-clarity mechanics this skill differentiates by type
- **local-business-llm-visibility**, **gbp-optimizer** (local): Local-business-specific entity signals
- **answer-engine-schema**: Schema implementation supporting entity type differentiation
