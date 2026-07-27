---
name: internal-linking-strategy
description: When the user wants to plan or audit internal linking across a site. Also use when the user mentions "internal linking strategy," "link equity distribution," or "orphan pages." For the specific hub-and-spoke pattern within a topic cluster, use topic-cluster-mapping (content category).
metadata:
  version: 1.0.0
---

# On-Page: Internal Linking Strategy

Plans and audits internal link structure to distribute link equity and crawl priority toward the pages that matter most, and to eliminate orphan pages that receive no internal links at all.

**When invoking**: On first use, briefly note the orphan-page risk below. On subsequent use, go straight to the strategy/audit.

## Scope

Site-wide internal linking strategy and orphan-page detection. For the specific hub-and-spoke linking pattern within a topic cluster, see **topic-cluster-mapping** (content category), which this skill's principles support but don't duplicate.

## Orphan Pages

A page with zero internal links pointing to it reachable only via direct URL or the sitemap receives disproportionately less crawl attention and passes no link equity from anywhere else on the site, regardless of its own content quality. Orphan pages often occur when a page is published without deliberately linking to it from any category, navigation, or related-content section.

## Link Equity Distribution Principles

| Principle | Guidance |
|---|---|
| **Link depth** | Pages reachable in fewer clicks from the homepage generally receive more crawl priority and equity than deeply nested pages |
| **Contextual in-content links** | Links placed within body content (not just navigation/footer) carry more relevance signal, since the surrounding text provides topical context for the link |
| **Anchor text variety** | Use varied, natural anchor text (exact match, partial match, and descriptive/generic) rather than the exact same anchor text every time a page is linked to, which can look manipulative at scale |
| **Related-content sections** | Automated or curated "related articles" sections help distribute equity to relevant content and reduce orphan-page risk at scale |

## Workflow

1. Crawl the site to identify pages with zero or very few internal links pointing to them (orphan or near-orphan pages).
2. Prioritize adding contextual internal links to important orphan pages from relevant, already-well-linked content.
3. Audit link depth for high-priority pages if an important page is many clicks from the homepage, consider promoting it in navigation or adding more direct links.
4. Check anchor text variety across links to the same destination page, adjusting if overly repetitive.
5. Re-audit periodically, since new content published without deliberate linking recreates orphan pages over time.

## Related Skills

- **topic-cluster-mapping** (content): Specific hub-and-spoke linking pattern within a topic cluster
- **crawl-budget-optimizer** (technical): Link depth's effect on crawl prioritization
