---
name: technical-seo-audit
description: When the user wants a comprehensive technical SEO audit covering crawlability, indexability, and site health broadly. Also use when the user mentions "technical SEO audit," "site health check," or "why isn't Google indexing my pages." This is the umbrella audit for specific sub-areas, use the specialized skill (core-web-vitals-audit, robots-txt-generator, structured-data-validator, etc.).
metadata:
  version: 1.0.0
---

# Technical: Technical SEO Audit

The umbrella technical audit covering crawlability, indexability, and site health end-to-end this skill sequences and cross-references the more specialized technical skills rather than duplicating their depth.

**When invoking**: On first use, briefly note the layered order below. On subsequent use, go straight to running the audit.

## Scope

Comprehensive technical health check, sequencing the specialized technical skills. For deep detail on any single area, defer to the relevant specialized skill listed below.

## Audit Layers, in Order

| Layer | Specialized skill | Why this order |
|---|---|---|
| **1. Crawlability** | **robots-txt-generator**, **crawl-budget-optimizer** | If crawlers can't reach the content, nothing downstream matters |
| **2. Renderability** | **javascript-seo-audit** | Confirms content is actually visible to crawlers, not just technically reachable |
| **3. Indexability** | Canonical tags (**canonical-tag-strategy**), redirects (**redirect-chain-audit**) | Confirms the right version of each page is the one being indexed |
| **4. Page experience** | **core-web-vitals-audit**, **mobile-first-indexing-check** | Confirms the indexed page performs well for real users |
| **5. Structured data** | **structured-data-validator** | Confirms rich-result and entity eligibility |
| **6. Internationalization (if applicable)** | **hreflang-implementation** | Only relevant for multi-region/multi-language sites |
| **7. AI crawler access** | **ai-crawler-access-audit** | Modern technical audits should include this alongside traditional crawler access |

## Why Sequencing Matters

Working top-down avoids wasted effort there's no value auditing Core Web Vitals on pages that aren't even being crawled, and no value optimizing structured data on pages blocked by a canonical or redirect misconfiguration. Each layer assumes the ones above it are already resolved.

## Workflow

1. Confirm crawlability first: check robots.txt (traditional and AI bots), and crawl budget/log file data if available.
2. Confirm renderability: check whether core content requires JavaScript execution to appear.
3. Confirm indexability: audit canonical tags and redirect chains for conflicts.
4. Check page experience: run **core-web-vitals-audit** and **mobile-first-indexing-check**.
5. Validate structured data across key page templates.
6. If the site serves multiple regions/languages, audit hreflang implementation.
7. Compile findings into a single prioritized report, ordered by which layer they affect (fixing a Layer 1 issue takes priority over a Layer 5 issue, since it may be blocking everything downstream).

## Related Skills

- **robots-txt-generator**, **crawl-budget-optimizer**, **javascript-seo-audit**, **canonical-tag-strategy**, **redirect-chain-audit**, **core-web-vitals-audit**, **mobile-first-indexing-check**, **structured-data-validator**, **hreflang-implementation**, **ai-crawler-access-audit**: Specialized sub-audits this skill sequences
- **site-migration-checklist**: A related, higher-stakes application of this same layered audit during a migration
