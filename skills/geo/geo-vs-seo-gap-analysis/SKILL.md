---
name: geo-vs-seo-gap-analysis
description: When the user wants to compare a site's traditional SEO performance against its AI-citation performance to find where the two diverge. Also use when the user mentions "GEO vs SEO gap," "we rank well but don't get cited by AI," or "why isn't our SEO success translating to AI visibility." For fixing an identified access or structure gap, use llm-retrievability-audit or ai-citation-optimization.
metadata:
  version: 1.0.0
---

# GEO: GEO vs. SEO Gap Analysis

Compares a page's traditional organic ranking against its AI-citation performance to identify pages that succeed in one dimension but not the other — a diagnostic specifically for the disconnect between the two, not a general audit of either alone.

**When invoking**: On first use, briefly explain why the two can diverge. On subsequent use, go straight to the comparison.

## Scope

The comparative gap between traditional ranking and AI citation for the same content. Not a general SEO audit (see **seo-audit-to-roadmap**, strategy category) or a general AI-citation audit (see **llm-retrievability-audit**) in isolation — this skill's value is in the side-by-side comparison.

## Why the Two Diverge

Traditional ranking and AI citation are increasingly decoupled: strong backlink profiles and historical ranking authority still matter for traditional search, but AI systems increasingly select sources based on extractability, entity clarity, and structural fit rather than rank alone. A page can rank #1 traditionally while being passed over for AI citation because its content isn't self-contained or answer-first — and conversely, a page ranking outside the top 10 can still earn AI citations if its passages are unusually well-structured for extraction.

## Gap Categories

| Pattern | Likely cause | Fix |
|---|---|---|
| Ranks well, rarely cited by AI | Content is topically correct but not structured for extraction (long narrative build-up, no self-contained passages) | **ai-citation-optimization** structural rewrite |
| Ranks well, AI crawler access is the issue | Retrieval bot inadvertently blocked at robots.txt level | **ai-crawler-access-audit** |
| Ranks well but page is stale | Hasn't been updated recently despite still ranking | **geo-crawl-freshness-check**, **content-refresh-audit** |
| Cited by AI, ranks poorly traditionally | Strong structural/extractability signals compensating for weaker traditional authority — worth studying as a template for other pages | Reinforce the pattern elsewhere rather than "fixing" |

## Workflow

1. Pull traditional ranking data for the priority keyword/topic set (see **rank-tracking-summary**, analytics category).
2. Pull or directly test AI citation status for the same queries across relevant platforms.
3. Cross-reference the two datasets and classify each page into a gap category above.
4. Route each gap category to the appropriate fix skill.
5. Re-check periodically, since AI citation behavior shifts more frequently than traditional ranking as platforms update their retrieval methods.

## Related Skills

- **llm-retrievability-audit**: Full access/rendering/extraction diagnostic for pages found to have a citation gap
- **ai-citation-optimization**: Structural fix for extractability gaps
- **rank-tracking-summary** (analytics): Traditional ranking data input to this comparison
