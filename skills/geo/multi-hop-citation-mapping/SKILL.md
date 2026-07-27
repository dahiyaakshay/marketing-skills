---
name: multi-hop-citation-mapping
description: When the user wants to understand how AI systems chain together multiple sources (fan-out queries) to construct an answer, rather than citing a single page. Also use when the user mentions "multi-hop citation," "fan-out queries," or "how does AI combine multiple sources for one answer." For single-page citation optimization, use ai-citation-optimization.
metadata:
  version: 1.0.0
---

# GEO: Multi-Hop Citation Mapping

Maps how AI answer engines perform "fan-out" issuing multiple related sub-queries to gather and cross-reference several sources before assembling a single answer and identifies where a site's content fits into that broader retrieval pattern rather than assuming one page competes for one query in isolation.

**When invoking**: On first use, briefly explain the fan-out concept below. On subsequent use, go straight to the mapping.

## Scope

Multi-source, multi-query citation patterns. Not single-page structural optimization (see **ai-citation-optimization**), which remains a prerequisite for any individual page to be selected within a fan-out.

## What Fan-Out Means in Practice

Beyond ranking for the literal query typed by a user, AI systems often run several supplementary searches to ground and supplement their answer a query about "best CRM for small business" might trigger separate sub-queries for pricing comparisons, specific competitor names, and recent reviews, each potentially pulling from a different source. A page's citation odds depend not only on how well it answers the primary query but also on how well it ranks for these related fan-out queries evidence shows a clear relationship between ranking well on fan-out-adjacent queries and being cited in the final answer.

## Mapping Workflow

| Step | What to do |
|---|---|
| 1. Identify the primary target query | The main query a piece of content is built around |
| 2. Brainstorm likely fan-out sub-queries | Comparison variants, "best X for Y" variants, pricing/spec-specific variants, recent-news variants the kinds of adjacent questions an AI system would plausibly ask to enrich its answer |
| 3. Check current ranking/citation status for each sub-query | Not just the primary query a page or site can win the primary query but lose valuable fan-out citations entirely |
| 4. Identify gaps | Sub-queries where the site has no strong candidate page at all represent a citation opportunity, not just a ranking one |

## Workflow

1. Select a priority topic/query cluster.
2. Generate the plausible fan-out sub-queries an AI system would likely issue alongside the primary query.
3. Audit current content coverage and ranking against each sub-query, not just the primary term.
4. Flag sub-queries with no strong existing page as content gaps (route to **content-gap-analysis**, content category).
5. Prioritize closing the gaps most likely to appear across multiple related fan-out patterns, since those have compounding citation value.

## Related Skills

- **ai-citation-optimization**: Prerequisite single-page structure for any page to be selected within a fan-out
- **content-gap-analysis** (content): Where identified fan-out gaps get addressed with new content
- **geo-competitive-benchmark**: Comparing fan-out coverage against competitors
