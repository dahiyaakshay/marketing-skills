---
name: content-optimizer
description: When the user wants to score, grade, or optimize existing content for SEO and readability before publishing. Also use when the user mentions "content score," "keyword density," "content grade," "readability score," "Flesch-Kincaid," "over-optimization," "how well is this page optimized," or pastes a draft asking "how can I improve this." For generating new content from scratch, use blog-post-writer or the relevant page-type skill. For AI-citation scoring specifically, use ai-citation-optimization. For keyword research/clustering upstream of this, use keyword-clustering.
metadata:
  version: 1.0.0
---

# Content: Content Optimizer

Scores an existing draft or published page across SEO, readability, and topical depth, then returns specific, prioritized edits — not just a number. Commercial tools (Surfer, Clearscope, MarketMuse) score across hundreds of on-page signals; this skill uses a compact, transparent rubric so the reasoning is visible and the score is explainable, not a black box.

**When invoking**: On first use, briefly note the rubric dimensions before scoring. On subsequent use, go straight to the score and edit list.

## Scope

Applies to a single piece of already-drafted content (blog post, landing page, article). Not for keyword discovery (see **keyword-clustering**) or new-content generation (see **blog-post-writer**, **landing-page-copywriter**).

## Scoring Rubric

Score each dimension 0–20, sum to a 0–100 grade.

| Dimension | What it measures | 0–20 scoring guide |
|---|---|---|
| **Keyword placement** | Primary keyword in title, H1, first 100 words, at least one subheading | Full marks only if present in all four positions naturally, not forced |
| **Keyword density** | Ratio of primary keyword occurrences to total word count | 0.5–1.5% is the healthy range; above ~2% risks reading as stuffed and functions as a diagnostic flag rather than a lever to maximize |
| **Semantic/topical coverage** | Presence of related terms, synonyms, and subtopics a thorough treatment of the subject would include | Score by comparing against what top-ranking competitor pages cover, not by a fixed checklist |
| **Readability** | Sentence length, paragraph length, jargon density, passive voice | Target a Flesch-Kincaid grade level appropriate to the audience; most web content performs best written for an 8th–10th grade reading level |
| **Structure** | Use of H2/H3 hierarchy, lists, tables, short paragraphs | Reward scannable structure over long unbroken blocks |

## Density Is a Diagnostic, Not a Target

The most common content-optimization mistake is treating keyword density as something to maximize. Density should be used as a health check, not a goal to hit — a page that reads naturally and happens to sit at 0.8% is healthier than one artificially inflated to 2% to satisfy a tool. If a sentence makes the keyword noticeable before the meaning lands, that sentence needs rewriting regardless of what the density number says.

## Topical Depth Over Repetition

Thorough topical coverage is a stronger signal than repetition of the exact target phrase. A page targeting "content scoring" should also naturally address scoring rubrics, common metrics, tools in the category, and common pitfalls — covering the surrounding vocabulary a genuine expert would use, not just the literal keyword.

## Workflow

1. **Ingest the draft** (or fetch the live URL) and the target primary keyword.
2. **Run each rubric dimension** and assign a 0–20 score with a one-line justification.
3. **Identify competitor coverage gaps** if competitor URLs are available — list subtopics they cover that this draft doesn't.
4. **Flag over-optimization risks** — keyword stuffing, unnatural phrase repetition, forced exact-match anchor text.
5. **Return a prioritized edit list**, ordered by expected impact: structural fixes first (missing H2s, wall-of-text paragraphs), then coverage gaps, then density/placement fine-tuning last.
6. **Give the total score and grade band** (90–100 excellent, 70–89 solid with targeted fixes, below 70 needs structural rework) — but frame it as a directional signal, not a guarantee of ranking, since no on-page score alone determines search performance.

## Calibration Note

If applying this rubric repeatedly for the same site or client, periodically score a sample of already-published, already-ranking pages and check whether high scorers actually correlate with strong performance in Search Console or analytics. If they don't, adjust the dimension weights rather than assuming the rubric is fixed — calibration against real performance data typically takes a couple of rounds before the scores become predictive for that specific site.

## Related Skills

- **keyword-clustering**: Upstream keyword research and intent grouping
- **ai-citation-optimization**: Parallel scoring for AI-citation eligibility (TL;DR blocks, QAE pattern, answer-first structure) rather than traditional SEO
- **content-gap-analysis**: Site-wide gap analysis vs. single-page optimization
- **editorial-style-guide**: House style rules this skill should defer to when they conflict with generic best practice
- **blog-post-writer**, **landing-page-copywriter**: New-content generation upstream of this skill
