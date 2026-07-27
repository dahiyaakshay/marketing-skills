---
name: content-gap-analysis
description: When the user wants to find topics or subtopics competitors cover that the site doesn't. Also use when the user mentions "content gap analysis," "what are we missing," "competitor content audit," or "topics we haven't covered." For single-page optimization once gaps are identified, use content-optimizer. For organizing gaps into a structured plan, use content-calendar-builder or topic-cluster-mapping.
metadata:
  version: 1.0.0
---

# Content: Content Gap Analysis

Identifies topics, subtopics, and keyword variants that ranking competitors cover but the site doesn't — site-wide, not page-by-page.

**When invoking**: On first use, briefly note this is a site-wide diagnostic, distinct from single-page scoring. On subsequent use, go straight to the analysis.

## Scope

Site-wide topical coverage vs. competitors. Not single-page optimization (see **content-optimizer**) or keyword-to-page mapping (see **keyword-clustering**).

## Method

| Step | What it reveals |
|---|---|
| Pull top 5–10 ranking URLs per target keyword/topic | The actual competitive set for that topic, not assumed competitors |
| List every subtopic/H2 those pages cover | The topical surface area needed to compete |
| Cross-reference against existing site content | Which subtopics already exist vs. are genuinely missing |
| Check search intent per gap | Whether the gap is a real opportunity or a mismatched intent (e.g. a comparison page vs. a how-to) |

## Decision Framework

| Gap type | Action |
|---|---|
| Subtopic covered by 3+ competitors, missing entirely on-site | High priority — likely a genuine authority gap |
| Subtopic covered thinly on-site (buried, not a dedicated section) | Medium priority — expand existing page rather than create new one |
| Subtopic only 1 competitor covers | Low priority unless it's a rising trend term |
| Gap is really a different intent, not a missing topic | Not a gap — don't force content that doesn't match what searchers want |

## Workflow

1. Identify the target topic/keyword cluster.
2. Pull and read the top-ranking competitor pages for that cluster.
3. Extract their subtopic/H2 structure.
4. Compare against the site's existing coverage (search internal content, not just the one target page).
5. Classify each gap by priority using the framework above.
6. Route findings to **content-calendar-builder** (new content) or **content-optimizer** (expand existing page).

## Related Skills

- **content-optimizer**: Single-page scoring once a gap becomes a specific edit
- **topic-cluster-mapping**: Structuring gaps into a pillar/cluster architecture
- **keyword-clustering**: Upstream keyword grouping that often precedes gap analysis
- **competitor-content-audit**: Broader ongoing competitor monitoring vs. this skill's point-in-time gap check
