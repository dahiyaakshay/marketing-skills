---
name: content-pruning-audit
description: When the user wants to decide whether underperforming pages should be deleted, redirected, or merged rather than refreshed. Also use when the user mentions "content pruning," "should I delete this page," "low-value pages," or "crawl budget cleanup." For pages worth saving instead, use content-refresh-audit.
metadata:
  version: 1.0.0
---

# Content: Content Pruning Audit

Classifies underperforming pages into keep/refresh, merge, redirect, or delete — the counterpart decision to **content-refresh-audit** for pages that don't have a realistic recovery ceiling.

**When invoking**: On first use, note that pruning is a legitimate growth lever, not just cleanup — sites with a large backlog of aging content often see meaningful traffic recovery from disciplined pruning without publishing anything new. On subsequent use, go straight to the classification.

## Scope

The prune/consolidate/delete decision. Not the refresh path for recoverable pages (see **content-refresh-audit**) or the redirect implementation mechanics (see **redirect-chain-audit**, technical category).

## Classification Matrix

| Category | Criteria | Action |
|---|---|---|
| **Keep/Refresh** | Decaying but still has traffic, backlinks, or clear business relevance; the gap is content-based and fixable | Route to **content-refresh-audit** instead |
| **Merge/Consolidate** | Topic is covered better by a stronger existing page; some unique value worth preserving | Fold unique content into the stronger page, 301 redirect to it |
| **Redirect only** | Page has lost nearly all traffic and a closely related page already covers the topic well | 301 to the most semantically relevant page — a category or pillar page if no exact match exists |
| **Delete (410)** | Never ranked, no backlinks, topic no longer relevant to the site's strategy, no realistic path to useful content | Return a 410 (Gone) status, or 301 if a reasonable alternative exists |

## Why Pruning Matters Beyond Cleanup

Pruning keeps crawl budget focused on pages that matter and removes signals of low-quality, thin, or abandoned content from the domain as a whole — a large volume of thin, never-ranking pages can quietly drag down how a search engine or AI crawler evaluates the whole site's quality, not just the individual pages.

## Workflow

1. Pull the full content inventory with traffic, backlink count, and last-meaningful-update date for each page.
2. Flag pages with minimal-to-no organic traffic and no backlinks as prune candidates by default.
3. For each candidate, check for a genuine recovery ceiling (backlinks present, topic still relevant, content gap rather than fundamental irrelevance) — if present, redirect the candidate to **content-refresh-audit** instead.
4. Classify remaining candidates into merge, redirect-only, or delete using the matrix above.
5. For merge/redirect decisions, identify the closest semantically relevant destination page before implementing.
6. Never delete outright without a redirect if there's any existing link equity worth preserving — noindexing or redirecting protects that equity even when the page itself isn't worth keeping live.

## Related Skills

- **content-refresh-audit**: The keep/refresh path for pages this audit routes away from deletion
- **redirect-chain-audit** (technical): Implementation and validation of the 301s this audit recommends
- **content-scoring-rubric**: Can supply the quality signal used to separate genuinely thin content from content that's simply under-promoted
