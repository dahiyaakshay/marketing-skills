---
name: redirect-chain-audit
description: When the user wants to find and fix redirect chains or loops. Also use when the user mentions "redirect chain," "redirect loop," or "301 redirect audit." For the decision of which pages should redirect where during content pruning, use content-pruning-audit (content category).
metadata:
  version: 1.0.0
---

# Technical: Redirect Chain Audit

Detects and flattens redirect chains (A → B → C) and loops (A → B → A), both of which waste crawl budget, dilute link equity, and slow page load every additional hop in a chain adds latency and reduces the equity passed to the final destination.

**When invoking**: On first use, briefly note why chains matter beyond just "eventually working." On subsequent use, go straight to the audit.

## Scope

Detecting and fixing existing redirect chains/loops. For the strategic decision of which URL should redirect to which during a content pruning/consolidation exercise, see **content-pruning-audit** (content category) this skill implements and validates redirects, that skill decides them.

## Why Chains Are a Problem Even When They "Work"

A redirect chain that eventually resolves to a working page still causes real harm: each additional hop adds page load latency, some link equity is typically lost at each hop rather than passing through cleanly, and crawlers may abandon very long chains before reaching the final destination, effectively treating the original URL as broken. A chain accumulates over time often the result of successive site migrations or URL restructures each adding one more redirect on top of the last, without anyone flattening the full chain back to a single hop.

## Detection Method

Crawl the site's redirect map and flag: any URL requiring more than one hop to reach its final destination, and any chain that returns to a URL already visited earlier in the same chain (a loop, which never resolves and returns an error to both users and crawlers).

## Fix Pattern

For any chain of length 2+, redirect the original URL directly to the final destination in one hop, rather than leaving the intermediate hops in place. Update the redirect rule at the source rather than layering a new redirect on top of the existing one this is what allows chains to compound in the first place.

## Workflow

1. Crawl the site (or review server redirect rules) to map every redirect and its destination.
2. Follow each redirect to its final resolution, counting hops.
3. Flag any chain of 2+ hops and any loop.
4. For each flagged chain, update the original URL's redirect rule to point directly to the final destination.
5. Re-crawl to confirm every redirect now resolves in a single hop.
6. Re-run this audit after any migration or major URL restructure, since chains most commonly accumulate at exactly those events.

## Related Skills

- **content-pruning-audit** (content): Decides which URLs should redirect where; this skill implements and validates that decision cleanly
- **site-migration-checklist**: The event most likely to introduce new redirect chains if not carefully managed
- **xml-sitemap-builder**: Redirected URLs should be removed from the sitemap, not left in alongside their destination
