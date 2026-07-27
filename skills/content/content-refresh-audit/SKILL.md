---
name: content-refresh-audit
description: When the user wants to identify and update decaying content that's losing organic traffic. Also use when the user mentions "content decay," "refresh old content," "why is this page losing traffic," or "content that needs updating." For deciding whether a page should instead be deleted, use content-pruning-audit. For scoring the page after refresh, use content-optimizer.
metadata:
  version: 1.0.0
---

# Content: Content Refresh Audit

Identifies pages in content decay gradual, not sudden, traffic loss and prioritizes which ones are worth refreshing based on recovery potential, not just how much traffic they've lost.

**When invoking**: On first use, briefly explain the decay-vs-sudden-drop distinction below. On subsequent use, go straight to the audit.

## Scope

Detecting and prioritizing refresh candidates. Not the prune-vs-keep decision for pages with no recovery potential (see **content-pruning-audit**) or scoring the page post-refresh (see **content-optimizer**).

## Decay vs. Sudden Drop

A sudden, sharp traffic drop (roughly 50%+ overnight or within days) usually signals a technical problem, algorithm penalty, or tracking break that's a **traffic-anomaly-detector** investigation, not a refresh candidate. Content decay, by contrast, is a gradual decline a page slipping a position or two per month, losing a few clicks per week typically becoming visible over a 3–6+ month window. Pages often peak 6–18 months after publication and then begin this gradual slide as competitors improve, search intent shifts, and facts go stale.

## Detection Signals

| Signal | What it indicates |
|---|---|
| Declining organic clicks + rising average position (worse rank) together | Classic decay pattern, not just a traffic dip |
| Falling CTR at a stable or improving position | Meta title/description no longer compelling relative to what else appears in the SERP (including AI Overviews now capturing clicks even on page-one rankings) |
| Rising bounce rate / falling session duration on an otherwise stable-ranking page | Content itself may be thinning relative to competitors, even if rank hasn't moved yet |
| Page hasn't grown or has declined over the trailing 12 months | A reasonable rule of thumb for flagging decay candidates for review |

## Prioritization

Prioritize by the intersection of three factors: historical traffic peak, current business relevance, and realistic recovery ceiling. Pages with a strong existing backlink profile and a content gap (rather than a link gap) tend to recover fastest refreshing content is often faster and cheaper than publishing new pages, since the page builds on existing authority rather than starting from zero. Not every refresh candidate deserves the effort: some proportion of proposed candidates, after closer review, belong in the prune or consolidate column instead (see **content-pruning-audit**) because they have minimal traffic and no backlinks to build on.

## What a Real Refresh Includes

Cosmetic date changes alone don't work. A genuine refresh: updates statistics and examples (replacing anything roughly 18–24 months old or older), expands thin sections relative to what current top-ranking competitors cover, checks whether search intent for the target query has shifted since publication, and updates headline/metadata rather than only the body. Recovery from a properly executed refresh is often visible within 30–45 days.

## Workflow

1. Pull organic performance trends (clicks, impressions, position, CTR) over the trailing 12 months for the site's content library.
2. Flag pages showing the gradual-decline pattern (not sudden drops route those to **traffic-anomaly-detector**).
3. Score each flagged page on backlink strength, current business relevance, and gap type (content gap vs. link gap vs. technical gap).
4. Prioritize the intersection of highest recovery ceiling and highest business relevance first.
5. For each prioritized page, identify what changed: check current search intent, compare structure/depth against current top-3 competitors, and list specific outdated statistics or examples.
6. Route unrecoverable low-value pages to **content-pruning-audit** instead of refreshing them.

## Related Skills

- **content-pruning-audit**: Prune/consolidate decision for pages with no realistic recovery ceiling
- **traffic-anomaly-detector**: Distinguishes sudden drops (different root cause) from gradual decay
- **content-optimizer**: Post-refresh scoring against SEO/readability rubric
- **evergreen-content-identifier**: Identifying which content types need this kind of maintenance least
