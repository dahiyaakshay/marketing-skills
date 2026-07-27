---
name: site-migration-checklist
description: When the user wants a checklist for migrating a site (domain change, platform change, redesign, HTTP to HTTPS) without losing SEO value. Also use when the user mentions "site migration," "domain migration," or "replatforming SEO checklist." This skill sequences the other technical skills around a migration event specifically.
metadata:
  version: 1.0.0
---

# Technical: Site Migration Checklist

Sequences a site migration (domain change, platform change, redesign, protocol change) to preserve existing SEO value migrations are one of the highest-risk events in technical SEO because so many things can go wrong simultaneously, and problems often aren't visible until traffic has already dropped.

**When invoking**: On first use, briefly note the pre/during/post structure below. On subsequent use, go straight to the checklist.

## Scope

Migration-specific sequencing and risk mitigation, drawing on the other technical skills at each phase. Not a substitute for those skills' depth this is the coordination layer.

## Phase 1: Pre-Migration

| Task | Related skill |
|---|---|
| Full crawl and export of the current site's URL structure, rankings, and traffic by page | Baseline for post-migration comparison |
| Map every old URL to its new URL destination | Feeds the redirect map |
| Audit and plan the redirect strategy (never a blanket redirect-everything-to-homepage) | **redirect-chain-audit** |
| Confirm the new site's technical foundation (robots.txt, canonical strategy, structured data) matches or improves on the old site | **robots-txt-generator**, **canonical-tag-strategy**, **structured-data-validator** |

## Phase 2: Migration Day

| Task | Why |
|---|---|
| Implement 301 redirects for every old URL to its mapped new URL, live at the same time as the new site goes live | A gap between old-site-down and redirects-live creates a window of 404s that both users and crawlers encounter |
| Submit the new XML sitemap immediately | **xml-sitemap-builder** accelerates discovery of the new URL structure |
| Update robots.txt for the new site/domain | Confirm nothing is inadvertently blocked on the new platform by default settings |
| Update all internal links to point to new URLs directly, not through the redirect | Redirects should be a safety net for external links and old bookmarks, not the primary internal linking path |

## Phase 3: Post-Migration Monitoring

| Task | Timeframe |
|---|---|
| Monitor Search Console for crawl errors and indexing status | Daily for the first 1–2 weeks |
| Check for redirect chains introduced by the migration | **redirect-chain-audit** migrations are the single most common source of new chains |
| Compare traffic and ranking against the pre-migration baseline | Ongoing for at least 4–8 weeks, since search engines take time to fully re-crawl and re-evaluate a changed site |
| Confirm structured data and Core Web Vitals on the new platform | **structured-data-validator**, **core-web-vitals-audit** |

## The Most Common Migration Failure

The most damaging and common failure is an incomplete redirect map URLs that existed on the old site with no mapped destination on the new site, resulting in 404s for pages that previously ranked and drove traffic. Treat 100% redirect coverage of all previously-indexed URLs as non-negotiable, not just the URLs someone remembered to map.

## Workflow

1. Export the complete current URL list with associated traffic/ranking data as a baseline.
2. Build a 1:1 (or intentional many:1 for consolidation) redirect map covering every existing URL.
3. Implement redirects to go live simultaneously with the new site, with no gap.
4. Update internal links, submit the new sitemap, and confirm robots.txt on migration day.
5. Monitor Search Console daily for the first two weeks, watching specifically for crawl errors and unexpected redirect chains.
6. Compare against the pre-migration baseline for at least 4–8 weeks before declaring the migration successful.

## Related Skills

- **redirect-chain-audit**: Core implementation and chain-prevention tool for this checklist
- **xml-sitemap-builder**: Regeneration and resubmission required at migration
- **technical-seo-audit**: Full technical health check appropriate to run on the new platform post-migration
