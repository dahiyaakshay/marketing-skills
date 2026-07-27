---
name: llm-retrievability-audit
description: When the user wants a comprehensive audit of whether a site is technically retrievable and citable by AI systems (crawler access, indexability, content extractability) end-to-end. Also use when the user mentions "AI retrievability," "can AI models see my site," or "LLM visibility audit." For robots.txt specifically, use ai-crawler-access-audit (technical category). For content-structure tactics specifically, use ai-citation-optimization.
metadata:
  version: 1.0.0
---

# GEO: LLM Retrievability Audit

A comprehensive, end-to-end audit of whether a site can be crawled, indexed, and cited by AI systems — combining crawler access, rendering, and content structure into one diagnostic rather than checking each in isolation.

**When invoking**: On first use, briefly explain the three-layer model below. On subsequent use, go straight to the audit.

## Scope

The full-stack retrievability diagnostic. Draws on and cross-references **ai-crawler-access-audit** (technical), content structure from **ai-citation-optimization**, and freshness from **geo-crawl-freshness-check** — this skill is the umbrella audit that checks all three together.

## Three-Layer Model

| Layer | What breaks if this layer fails |
|---|---|
| **1. Access** (can the crawler reach the content) | robots.txt blocking the wrong bot, server errors, aggressive rate-limiting against AI crawler IP ranges |
| **2. Rendering** (can the crawler see the content) | AI crawlers generally do not execute JavaScript — content that only appears after client-side rendering is invisible regardless of access rules |
| **3. Extraction/citation** (is the content structured to be cited) | Content technically visible but buried in narrative prose, requiring surrounding context, is deprioritized versus self-contained, answer-first passages |

Most failed audits find the breakdown at layer 1 or 2, not layer 3 — teams often invest in content restructuring before confirming the content is even reachable.

## Audit Workflow

1. **Layer 1 — Access**: Run the full **ai-crawler-access-audit** checklist; confirm training vs. retrieval bots are correctly allowed/blocked per the site's posture.
2. **Layer 2 — Rendering**: Fetch the page as a non-JS crawler would (view source / disable JS) and confirm the core content is present in the initial HTML, not injected client-side.
3. **Layer 3 — Extraction**: Apply the **ai-citation-optimization** structural checklist (self-contained sections, answer-first paragraphs, TL;DR blocks).
4. **Cross-check freshness**: Run **geo-crawl-freshness-check** since stale content underperforms even when perfectly structured and accessible.
5. **Verify via direct query**: Where feasible, query the target AI platforms directly with relevant questions and check whether the site appears — the most direct verification available, since indirect proxies (rank, crawl stats) don't guarantee actual citation behavior.

## Related Skills

- **ai-crawler-access-audit** (technical): Layer 1 detail
- **ai-citation-optimization**: Layer 3 detail
- **geo-crawl-freshness-check**: Freshness cross-check
- **geo-competitive-benchmark**: Comparing retrievability against competitors once this audit is clean
