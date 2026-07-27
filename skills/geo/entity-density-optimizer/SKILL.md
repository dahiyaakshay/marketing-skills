---
name: entity-density-optimizer
description: When the user wants to increase how clearly a brand or topic is represented as a recognizable entity within content, to improve AI citation likelihood. Also use when the user mentions "entity density," "entity SEO," "Knowledge Graph," or "does AI recognize my brand as an entity." For citation-eligible content structure generally, use ai-citation-optimization. For entity-type-specific citation patterns, use entity-type-citation-strategy.
metadata:
  version: 1.0.0
---

# GEO: Entity Density Optimizer

Increases the density and clarity of named entities (brand, people, products, related organizations) within content so AI systems can confidently identify and cross-reference the entity, rather than treating it as an ambiguous string of text.

**When invoking**: On first use, briefly explain why entity clarity matters more than link volume for AI citation. On subsequent use, go straight to the optimization.

## Scope

Entity representation and disambiguation within content. Not the broader content-structure patterns (see **ai-citation-optimization**) or entity-type-specific citation research (see **entity-type-citation-strategy**).

## Why Entity Clarity Matters for AI Citation

AI systems increasingly select citation sources based on whether they can confidently identify a brand or topic as a distinct, well-defined entity — not primarily on backlink volume. If entity signals are weak or inconsistent (a brand name spelled differently across pages, no clear connection to related entities, no structured markup identifying it), an AI system is less likely to cite it confidently, regardless of how well the underlying content is written. This is described in current SEO research as a shift from "how many links point here" to "can the system confidently identify what this is."

## Optimization Levers

| Lever | Implementation |
|---|---|
| **Consistent naming** | Use the exact same brand/entity name and spelling across all owned properties and structured data — inconsistency is one of the most common causes of weak entity recognition |
| **Entity schema markup** | Organization, Person, and Product schema explicitly declaring the entity and its properties, rather than relying on AI to infer them from prose alone |
| **Connected-entity mentions** | Reference related, verifiable entities (partners, founders, industry associations) in a way that lets an AI system cross-reference and corroborate identity — research associates a higher count of connected entities in the Knowledge Graph with stronger citation likelihood |
| **Wikidata/Wikipedia presence** | Where eligible, a Wikidata entry is one of the strongest external corroboration signals for entity identity, since many AI systems draw on it directly |
| **Consistent NAP-equivalent data** | For non-local brands, this means consistent "about" info (founding date, HQ, leadership) repeated identically across owned and third-party profiles |

## Workflow

1. Audit current naming consistency across the site and structured data — flag any variant spellings or inconsistent branding.
2. Confirm Organization/Person schema is present, complete, and matches the consistent naming.
3. Identify and add references to genuinely connected, verifiable entities where natural (not forced name-dropping).
4. Check for Wikidata/Wikipedia presence; if absent and the entity is notable enough to qualify, flag as a longer-term opportunity.
5. Re-audit periodically, since inconsistency tends to creep back in as new pages or profiles are created without cross-checking the established entity data.

## Related Skills

- **ai-citation-optimization**: Broader content-structure patterns this skill's entity work supports
- **entity-type-citation-strategy**: Deeper research on which entity types get cited more often
- **answer-engine-schema**: Structured data implementation this skill depends on
