---
name: xml-sitemap-builder
description: When the user wants to create, audit, or troubleshoot an XML sitemap. Also use when the user mentions "XML sitemap," "sitemap.xml," or "why isn't Google finding my pages." For robots.txt configuration, use robots-txt-generator.
metadata:
  version: 1.0.0
---

# Technical: XML Sitemap Builder

Builds and audits XML sitemaps to help search engines efficiently discover and prioritize a site's important URLs — a sitemap is a discovery aid, not a ranking or indexing guarantee.

**When invoking**: On first use, briefly note the discovery-vs-indexing-guarantee distinction. On subsequent use, go straight to building/auditing.

## Scope

Sitemap structure and content. For the robots.txt reference to this sitemap, see **robots-txt-generator**.

## What Belongs in the Sitemap

| Include | Exclude |
|---|---|
| Canonical, indexable URLs the site wants search engines to prioritize | Non-canonical URL variants (parameter/filter URLs) |
| Pages returning a 200 status | Redirected (3xx) or error (4xx/5xx) URLs |
| Pages not blocked by robots.txt or noindex | Pages intentionally excluded from indexing |

A sitemap containing broken links, redirects, or noindexed pages sends a conflicting signal and wastes crawl attention — treat sitemap hygiene as an ongoing maintenance task, not a one-time build.

## Structural Guidance

- **Sitemap index files**: for large sites, split into multiple sitemap files referenced by a single sitemap index, since most search engines cap the number of URLs and file size per individual sitemap file.
- **lastmod accuracy**: only update the `lastmod` timestamp when the page's content has genuinely changed — inflating this value to signal false freshness undermines its usefulness as a signal over time.
- **Priority and changefreq fields**: largely ignored by major search engines in practice; don't spend significant effort fine-tuning these.
- **Segmented sitemaps**: separating sitemaps by content type (pages, posts, images) makes issues easier to isolate in Search Console's coverage reports than one giant combined file.

## Workflow

1. Generate or export the current list of canonical, indexable, 200-status URLs.
2. Exclude any redirected, error, noindexed, or non-canonical parameter URLs.
3. Split into multiple files with a sitemap index if the site is large.
4. Reference the sitemap in robots.txt (see **robots-txt-generator**).
5. Submit directly in Search Console for faster initial discovery.
6. Periodically audit for broken links or stale entries — a sitemap should be treated as a living document, re-validated whenever site structure changes significantly (e.g. a migration, see **site-migration-checklist**).

## Related Skills

- **robots-txt-generator**: Where this sitemap should be referenced
- **redirect-chain-audit**: Ensures redirected URLs are removed from the sitemap
- **site-migration-checklist**: Sitemap regeneration is a required step during migrations
