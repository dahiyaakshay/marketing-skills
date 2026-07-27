---
name: robots-txt-generator
description: When the user wants to create or audit a robots.txt file for traditional search engine crawlers. Also use when the user mentions "robots.txt," "block crawlers," or "disallow rules." For AI-crawler-specific rules (GPTBot, ClaudeBot, etc.), use ai-crawler-access-audit.
metadata:
  version: 1.0.0
---

# Technical: robots.txt Generator

Generates or audits a robots.txt file for traditional search engine crawlers (Googlebot, Bingbot) — access control and crawl-path management, not AI-specific bot rules.

**When invoking**: On first use, briefly confirm what should and shouldn't be crawlable. On subsequent use, go straight to generating/auditing.

## Scope

Traditional search engine crawler rules. For AI crawler-specific rules (GPTBot, ClaudeBot, PerplexityBot, etc.), see **ai-crawler-access-audit**, which should be layered on top of this file, not treated as a separate document.

## Core Syntax Reference

| Directive | Purpose |
|---|---|
| `User-agent:` | Specifies which crawler the following rules apply to (`*` for all) |
| `Disallow:` | Blocks a path from being crawled |
| `Allow:` | Explicitly permits a path, typically used to carve out an exception within a disallowed directory |
| `Sitemap:` | Points to the XML sitemap location — always include this |
| `Crawl-delay:` | Rate-limits crawl frequency (respected inconsistently across engines; Google ignores it in favor of Search Console-based crawl rate settings) |

## Common Patterns

```
User-agent: *
Disallow: /admin/
Disallow: /cart/
Disallow: /checkout/
Disallow: /*?*sort=
Allow: /

Sitemap: https://example.com/sitemap.xml
```

## Common Mistakes

- **Blocking CSS/JS directories**: this was once common practice for "cleanliness" but actively harms rendering-based ranking evaluation — Google needs to render the page like a browser does, which requires crawling the assets that render it.
- **Disallowing a path that's also canonicalized elsewhere**: creates a conflicting signal — pick one mechanism (robots.txt exclusion or canonical tag) as authoritative for a given path, not both contradicting each other.
- **Forgetting the sitemap directive**: a small omission that removes one of the easiest ways to help a crawler efficiently discover the site's URL structure.
- **Using robots.txt to try to remove already-indexed pages**: robots.txt only prevents future crawling, it doesn't deindex existing pages — use a noindex meta tag or Search Console removal tool for that instead.

## Workflow

1. Identify paths that should never be crawled (admin, cart, checkout, internal search/filter parameters generating near-duplicate URLs).
2. Draft the Disallow rules, with Allow exceptions where a subset of a disallowed path should remain crawlable.
3. Confirm CSS/JS assets are not blocked.
4. Add the sitemap directive.
5. Layer AI-crawler-specific rules on top via **ai-crawler-access-audit** rather than treating them as unrelated.
6. Validate the final file with a robots.txt testing tool before publishing.

## Related Skills

- **ai-crawler-access-audit**: AI-specific bot rules layered on top of this file
- **xml-sitemap-builder**: The sitemap this file should reference
- **canonical-tag-strategy**: The correct tool for signaling a preferred URL version, rather than using robots.txt for that purpose
