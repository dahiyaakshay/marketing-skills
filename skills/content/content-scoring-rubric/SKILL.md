---
name: content-scoring-rubric
description: When the user wants a standardized rubric to score content quality across a library, not just a single page. Also use when the user mentions "content scoring rubric," "quality standards for content," or "how do we grade our content library." For scoring one specific draft, use content-optimizer.
metadata:
  version: 1.0.0
---

# Content: Content Scoring Rubric

Defines a repeatable, library-wide quality rubric so every piece of content — regardless of author or age — is judged against the same standard, distinct from **content-optimizer**'s single-page, SEO-focused scoring pass.

**When invoking**: On first use, briefly note this is a library-wide standard, not a one-off score. On subsequent use, go straight to applying it.

## Scope

A standing quality bar applied across a content library, used for editorial QA and pruning/refresh prioritization. Not a single-page SEO score (see **content-optimizer**).

## Rubric Dimensions

| Dimension | What it captures |
|---|---|
| **Accuracy & currency** | Facts, statistics, and examples still correct and not stale (a common trigger for **content-refresh-audit**) |
| **Depth relative to competitors** | Does this page cover the topic as thoroughly as what's currently ranking, not just as thoroughly as it did when published? |
| **Originality / expertise signal** | First-hand insight, real examples, or genuine expertise vs. generic, easily-replicated information |
| **Structural quality** | Scannable formatting, clear headings, appropriate use of lists/tables |
| **Alignment with house style** | Consistency with **editorial-style-guide** rules |

## Using the Rubric at Library Scale

Apply the rubric as a periodic library-wide pass, not just at publication — content quality is not static, and a page that scored well at launch can decay in accuracy and competitiveness without any single dramatic event. Use the resulting scores to feed **content-refresh-audit** (moderate scores, worth saving) and **content-pruning-audit** (low scores with no realistic path to improvement).

## Workflow

1. Define or confirm the rubric dimensions and scoring scale for the specific content library.
2. Sample or fully audit the library against the rubric on a recurring cadence.
3. Flag pages scoring low on accuracy/currency specifically for **content-refresh-audit**.
4. Flag pages scoring low across the board with minimal traffic/backlinks for **content-pruning-audit**.
5. Track scores over time per page to distinguish genuine improvement from one-time fixes that later decay again.

## Related Skills

- **content-optimizer**: Single-page SEO/readability scoring, complementary but narrower in scope
- **content-refresh-audit**, **content-pruning-audit**: Downstream actions this rubric's scores feed
- **editorial-style-guide**: House style component of the rubric
