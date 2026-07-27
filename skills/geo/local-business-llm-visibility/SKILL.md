---
name: local-business-llm-visibility
description: When the user wants to improve how often a local business is recommended by AI systems for local, "near me," or category-based queries. Also use when the user mentions "AI local visibility," "does ChatGPT recommend local businesses," or "local business GEO." For the underlying Google Business Profile optimization this depends on, use gbp-optimizer (local category). For general entity clarity, use entity-density-optimizer.
metadata:
  version: 1.0.0
---

# GEO: Local Business LLM Visibility

Optimizes a local business's odds of being recommended by AI systems for local and category-based queries — a distinct problem from general GEO, since local recommendation draws heavily on structured local data (Google Business Profile, citations) rather than purely on web content.

**When invoking**: On first use, briefly note the local-data dependency below. On subsequent use, go straight to the optimization.

## Scope

AI-recommendation visibility for local businesses specifically. Draws heavily on **gbp-optimizer** and **local-citation-audit** (local category) as prerequisites — this skill is the AI-specific layer on top of that local SEO foundation.

## Why Local AI Visibility Depends on Structured Data More Than Prose

Unlike general topical GEO, where well-written web content can independently earn citation, local business recommendation by AI systems draws heavily on structured, verifiable local data — Google Business Profile completeness, consistent NAP (name/address/phone) data across directories, and review content — rather than primarily on the business's own website copy. A beautifully written local landing page with inconsistent NAP data across the web will likely underperform a plainer page backed by clean, consistent local data.

## Key Dependencies

| Dependency | Why it matters here |
|---|---|
| **GBP completeness and category accuracy** | Feeds directly into how confidently an AI system can identify and describe the business (see **gbp-optimizer**) |
| **Consistent NAP across citations** | Fragmented or inconsistent business data across directories weakens entity confidence for local AI recommendations, the same way inconsistent branding weakens general entity clarity |
| **Review volume and content** | Review text itself is often a grounding source AI systems draw on when describing what a business is known for |
| **Local landing page structure** | Should still apply general answer-first, self-contained structure (see **ai-citation-optimization**) for any AI system drawing on the website directly |

## Workflow

1. Confirm GBP completeness and category accuracy (see **gbp-optimizer**).
2. Audit NAP consistency across major directories (see **local-citation-audit**).
3. Review the volume and substance of customer reviews — thin or sparse review content limits what an AI system has to draw on.
4. Apply general AI-citation structure to the business's local landing pages.
5. Directly query relevant AI platforms with representative local queries ("best [category] near [location]") to verify actual recommendation behavior.

## Related Skills

- **gbp-optimizer** (local): Structured local data foundation this skill depends on
- **local-citation-audit** (local): NAP consistency audit
- **entity-density-optimizer**: General entity clarity mechanics applied to the local business context
