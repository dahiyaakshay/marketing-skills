---
name: ai-overview-optimization
description: When the user wants to optimize specifically for citation in Google's AI Overviews (the AI summary at the top of Google Search results). Also use when the user mentions "AI Overviews," "AIO citation," "how do I get cited in Google's AI summary," or "AI Overview ranking factors." For the general cross-platform citation structuring, use ai-citation-optimization. For ChatGPT-specific visibility, use chatgpt-search-visibility.
metadata:
  version: 1.0.0
---

# GEO: AI Overview Optimization

Optimizes specifically for citation within Google's AI Overviews — the SERP-integrated AI summary shown above organic results — which is a structurally distinct surface from traditional Google ranking and from standalone chat assistants like Gemini or ChatGPT.

**When invoking**: On first use, briefly note that ranking #1 traditionally no longer guarantees AIO citation. On subsequent use, go straight to the optimization plan.

## Scope

Google AI Overview-specific tactics. For the platform-agnostic structural patterns this specializes, see **ai-citation-optimization**. For ChatGPT-specific and Perplexity-specific tactics, see **chatgpt-search-visibility** and **perplexity-citation-audit**.

## The Declining Rank-to-Citation Correlation

Large-scale studies have tracked a declining correlation between top-10 Google ranking and AIO citation — one widely cited analysis found the correlation dropped from roughly 76% to 38% over time, meaning a meaningful share of cited URLs now rank well outside the traditional top 10, sometimes beyond position 50. AI Overviews frequently pull cited sources from positions 4–20 or further, based on passage-level quality and trust signals rather than overall page rank alone. Practically: don't treat "we already rank #1" as sufficient for AIO visibility — structure and extractability now compete alongside rank.

## What Correlates With Citation

| Factor | Why it matters |
|---|---|
| **Self-contained, extractable passages** | A paragraph should answer completely on its own — the test is whether a reader would understand it fully if it were shown with no other context |
| **Multiple citations per answer are the norm** | The large majority of AI Overviews cite three or more sources, and citing just one source is rare — meaning the goal is to be one of several credible sources, not the single answer |
| **Content freshness** | Recently updated content is disproportionately more likely to be cited; pages left untouched for many months tend to lose citation eligibility even if they still rank well |
| **Citation position within the page** | A large share of citations are pulled from the introductory portion of a page rather than the middle or conclusion — front-loading the direct answer matters more than burying it after a long build-up |
| **E-E-A-T and structured data** | Expert authorship signals and explicit schema markup both correlate with higher citation likelihood, reinforcing the case for both credentialed content and technical markup working together |

## Business Impact of Citation

Being cited in an AI Overview has been associated with a meaningfully higher click-through rate per impression compared to appearing in the AIO's linked results without being directly cited — citation functions as a visibility premium, not just a vanity signal, which is why chasing it is worth the structural investment.

## Workflow

1. Identify target queries known to trigger AI Overviews (informational, comparison, and definitional queries trigger AIOs far more often than narrow transactional ones).
2. Audit the page's introductory section specifically — this is where most citations are pulled from — and ensure the direct answer appears there, self-contained.
3. Check content freshness; if the page hasn't been meaningfully updated recently, treat that as a priority fix.
4. Confirm structured data (schema) is present and accurate.
5. Don't rely on traditional rank alone as a proxy for AIO visibility — track actual citation appearance separately.

## Related Skills

- **ai-citation-optimization**: The general cross-platform structural patterns this skill specializes for Google
- **chatgpt-search-visibility**, **perplexity-citation-audit**: Platform-specific counterparts for other engines
- **content-refresh-audit** (content): Freshness maintenance this skill depends on
- **geo-crawl-freshness-check**: Broader freshness-and-crawl diagnostic across AI platforms
