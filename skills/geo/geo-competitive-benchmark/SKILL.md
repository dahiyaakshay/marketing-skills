---
name: geo-competitive-benchmark
description: When the user wants to benchmark AI-citation visibility against competitors. Also use when the user mentions "GEO competitive benchmark," "who's getting cited instead of us," or "competitor AI visibility comparison." For a single-site retrievability audit without competitive comparison, use llm-retrievability-audit.
metadata:
  version: 1.0.0
---

# GEO: Competitive Benchmark

Benchmarks AI-citation visibility against a defined competitor set across a shared query list, identifying where competitors are winning citations and why.

**When invoking**: On first use, briefly note the query-set approach below. On subsequent use, go straight to the benchmark.

## Scope

Competitive comparison specifically. For a single-site audit without competitive framing, see **llm-retrievability-audit**.

## Method

| Step | What it produces |
|---|---|
| Define a shared query set | The representative questions a target customer would plausibly ask an AI system in this category |
| Query each target platform with the full set | A citation map: which domain got cited (or named, see **brand-mention-in-ai-answers**) for each query, across each platform |
| Score citation share | The proportion of queries where the site itself was cited, versus each named competitor |
| Diagnose winning competitor pages | For queries where a competitor won and the site lost, inspect their structure, freshness, and entity signals against the site's own equivalent page |

## What to Diagnose in a Competitor's Winning Page

When a competitor is cited and the site isn't for the same query, check (in order): crawler access (is the site's equivalent page even reachable — see **ai-crawler-access-audit**), structural extractability (see **ai-citation-optimization**), freshness (see **geo-crawl-freshness-check**), and entity clarity (see **entity-density-optimizer**). Diagnosing in this order avoids restructuring content when the actual problem is that the page isn't being crawled at all.

## Workflow

1. Define the competitor set and the shared query list.
2. Query each target AI platform (ChatGPT Search, Perplexity, Google AI Overviews, Claude) with the full list.
3. Log citation/mention results per query per platform.
4. Calculate citation share for the site versus each competitor.
5. For lost queries, diagnose the winning competitor page using the ordered checklist above.
6. Prioritize fixes by query volume/value, not just by number of gaps.

## Related Skills

- **llm-retrievability-audit**: Single-site diagnostic applied to specific pages flagged by this benchmark
- **brand-mention-in-ai-answers**: Broader mention tracking beyond formal citation links
- **multi-hop-citation-mapping**: Explains why a competitor might win via fan-out queries the primary query list misses
