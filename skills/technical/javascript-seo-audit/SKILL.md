---
name: javascript-seo-audit
description: When the user wants to audit whether JavaScript-rendered content is visible to search engines and AI crawlers. Also use when the user mentions "JavaScript SEO," "client-side rendering issues," or "is my React/Vue site crawlable." For AI-crawler-specific rendering concerns, cross-reference ai-crawler-access-audit (which notes AI crawlers generally don't execute JS at all).
metadata:
  version: 1.0.0
---

# Technical: JavaScript SEO Audit

Audits whether content rendered via client-side JavaScript is actually visible to search engine and AI crawlers — a technically reachable page (per robots.txt) can still be functionally invisible if its content only appears after JS execution a crawler doesn't perform.

**When invoking**: On first use, briefly explain the rendering-budget concept below. On subsequent use, go straight to the audit.

## Scope

JS-rendering visibility for crawlers. Distinct from crawler access rules (see **robots-txt-generator**, **ai-crawler-access-audit**) — a page can be fully allowed by robots.txt and still be invisible in practice if this layer fails.

## Crawler Rendering Behavior Varies

| Crawler type | JS rendering behavior |
|---|---|
| **Googlebot** | Executes JavaScript via a rendering queue, but on a delay separate from the initial crawl — content requiring JS may be indexed later than static HTML content, and complex or slow-rendering JS can be abandoned before completion |
| **Bingbot** | More limited JS rendering support than Google historically |
| **AI training/retrieval crawlers (GPTBot, ClaudeBot, PerplexityBot, etc.)** | Generally do not execute JavaScript at all — content must be present in the initial server-rendered HTML response to be seen by these crawlers, regardless of robots.txt configuration (see **ai-crawler-access-audit**) |

This means a JS-heavy site optimized only for Googlebot's eventual rendering may still be substantially invisible to AI answer engines, which is an increasingly important consideration alongside traditional search visibility.

## Diagnostic Method

Compare the raw server response (view-source, or fetch with JS disabled) against the fully rendered page (what a browser shows). Any content present in the rendered version but absent from the raw response is JS-dependent and at risk of delayed indexing or, for non-JS-executing crawlers, complete invisibility.

## Fix Patterns

| Approach | What it solves |
|---|---|
| **Server-side rendering (SSR)** | Delivers fully-rendered HTML on the initial request — the most robust fix for both traditional and AI crawler visibility |
| **Static site generation (SSG)** | Pre-renders pages at build time — similarly robust, appropriate for content that doesn't need to be dynamic per-request |
| **Dynamic rendering** (serving a pre-rendered version specifically to crawlers) | A workaround rather than a structural fix — generally considered less reliable long-term than SSR/SSG |
| **Critical content in initial HTML, progressive enhancement for the rest** | A middle-ground approach: ensure the core content and navigation are present without JS, and layer interactive enhancements on top |

## Workflow

1. Fetch the raw server response for key page templates and compare against the fully rendered version.
2. Identify any content, links, or metadata present only after JS execution.
3. Check specifically whether critical content (main body text, primary navigation, canonical/meta tags) is JS-dependent — this is highest priority to fix.
4. Recommend SSR/SSG for JS-heavy frameworks where feasible, given it's the most robust and future-proof fix.
5. Cross-reference against **ai-crawler-access-audit** — any JS-dependent content is effectively invisible to non-JS-executing AI crawlers regardless of the fix timeline for traditional search.

## Related Skills

- **ai-crawler-access-audit** (this is cross-referenced here since AI crawlers generally skip JS rendering entirely, making this audit especially important for GEO)
- **core-web-vitals-audit**: JS architecture issues often underlie both rendering-visibility and INP performance problems
- **technical-seo-audit**: Broader audit this fits into
