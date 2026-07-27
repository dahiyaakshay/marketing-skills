---
name: ai-citation-optimization
description: When the user wants to structure or rewrite content specifically to increase the odds of being cited in AI-generated answers (ChatGPT, Claude, Perplexity, Google AI Overviews). Also use when the user mentions "get cited by ChatGPT," "AI citation," "answer engine optimization," "TL;DR block," "QAE pattern," "citable content," or "why isn't my content showing up in AI answers." This is a content-structure skill. For the broader platform/crawler strategy, use generative-engine-optimization. For robots.txt access control, use ai-crawler-access-audit. For general on-page SEO scoring, use content-optimizer.
metadata:
  version: 1.0.0
---

# GEO: AI Citation Optimization

Restructures content at the paragraph and section level to maximize the odds an AI answer engine extracts and cites it. Citation eligibility is a prerequisite (crawler access, indexability) but citation *selection* is a separate, content-structure problem this skill addresses the latter.

**When invoking**: On first use, briefly explain why structure (not just topical relevance) drives citation selection, then produce the rewrite or audit. On subsequent use, go straight to output.

## Scope

Assumes the page is already crawlable and indexed (see **ai-crawler-access-audit** if not). This skill covers content structure, answer formatting, and citability not backlink authority or domain-level signals (see **generative-engine-optimization** for the platform-level strategy those sit under).

## Why Structure Matters More Than Topic Match

AI answer engines operate on retrieval-augmented generation: they retrieve candidate passages first, then generate an answer from what was retrieved. A passage that is self-contained, directly answers a specific question, and is easy to extract as a standalone unit is more likely to be selected than a passage that is topically relevant but buried in narrative prose requiring context from surrounding paragraphs to make sense.

## Core Structural Patterns

| Pattern | Implementation |
|---|---|
| **Answer-first** | Give the direct answer within the first 40–60 words after any H2, before elaborating |
| **TL;DR or Key Takeaways block** | Either a 50–100 word bold summary paragraph, or 5–7 bullet points, placed immediately after the intro |
| **QAE structure** | Question as H2 → Answer in 1–2 sentences → Evidence (data, examples, lists) beneath it |
| **Self-contained answer blocks** | Each section (roughly 100–200 words) should be understandable on its own, without requiring the reader to have read prior sections |
| **Structured formats** | Numbered steps, bullet lists, and tables are extracted and cited more readily than equivalent information in unbroken prose |

## Content Freshness and Recency Signals

Answer engines with independently-built crawl indexes weight content freshness and semantic alignment heavily in source selection meaning a well-structured page that is out of date can still lose out to a more recently updated competitor covering the same ground. A visible last-updated date and periodic content refreshes are part of citation optimization, not just a housekeeping task.

## Access Is a Prerequisite, Not a Substitute

Structure work is wasted if the retrieval-indexing crawlers for the target platform (not the training crawlers) are blocked at the robots.txt level. Research published in December 2025 found that publishers blocking AI crawlers broadly experienced a meaningful decline in overall referral traffic without reliably reducing how often their content was cited elsewhere meaning blanket blocking tends to lose traffic without buying back citation exclusivity. Confirm crawler access first via **ai-crawler-access-audit**, then apply this skill's structural changes.

## Workflow

1. **Identify the target question(s)** the page should be citable for usually one primary question per H2, not one per page.
2. **Audit existing structure** against the pattern table: is there a TL;DR/Key Takeaways block? Does each H2 answer within the first 40–60 words? Is data presented in lists/tables where possible?
3. **Rewrite weak sections** to lead with the direct answer, then supporting evidence, rather than building up to the answer narratively.
4. **Check freshness signals** visible update date, current data/statistics rather than stale figures.
5. **Verify self-containment** read each section in isolation and confirm it doesn't require prior sections' context to make sense; if it does, that section is unlikely to be extracted cleanly as a standalone citation.
6. **Cross-check crawler access** for the target platform(s) before treating a citation gap as a content problem when it may be an access problem.

## What This Skill Does Not Cover

- Domain authority and backlink signals that influence which sources a platform considers trustworthy enough to cite (partially covered under **off-page** skills)
- Entity/brand disambiguation signals (see **entity-seo**)
- Platform-specific strategy differences between ChatGPT Search, Perplexity, Claude, and Google AI Overviews (see **generative-engine-optimization**)

## Related Skills

- **generative-engine-optimization**: Platform-level GEO/AEO strategy this skill's tactics feed into
- **ai-crawler-access-audit**: robots.txt prerequisite citation is impossible if retrieval crawlers are blocked
- **content-optimizer**: Traditional SEO scoring; run alongside this skill rather than instead of it, since ranking and citation are different but overlapping goals
- **entity-seo**: Entity and brand-identity signals that support citation trust
- **faq-page-generator**: FAQ structure is a naturally strong fit for the QAE pattern
