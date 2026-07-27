---
name: perplexity-citation-audit
description: When the user wants to audit or improve citation likelihood specifically on Perplexity. Also use when the user mentions "Perplexity citations," "PerplexityBot," or "why doesn't Perplexity cite my site." For crawler access rules, use ai-crawler-access-audit (technical category). For general AI citation structure, use ai-citation-optimization.
metadata:
  version: 1.0.0
---

# GEO: Perplexity Citation Audit

Audits citation likelihood specifically on Perplexity, which runs its own independently-built retrieval index rather than depending solely on a partner search engine with a documented history of crawling behavior that doesn't always cleanly respect robots.txt.

**When invoking**: On first use, note the robots.txt reliability caveat below. On subsequent use, go straight to the audit.

## Scope

Perplexity-specific citation tactics. For general crawler access rules, see **ai-crawler-access-audit** (technical category); for cross-platform structural patterns, see **ai-citation-optimization**.

## The robots.txt Reliability Caveat

Perplexity has been reported in some cases to crawl content in ways that don't fully respect published robots.txt directives, unlike the more consistently compliant behavior generally reported for OpenAI's and Anthropic's crawlers. This means robots.txt configuration alone is not a fully reliable lever, in either direction a site trying to be citable can't assume allowing PerplexityBot guarantees crawling, and a site trying to block Perplexity can't assume disallowing it guarantees exclusion. Server-level blocking (IP/user-agent filtering at the server or WAF layer) is the more reliable enforcement mechanism if exclusion is the actual goal.

## Perplexity-Specific Considerations

| Consideration | Implication |
|---|---|
| **Independently-built index** | Perplexity's citation selection isn't a pure reflection of Google or Bing rankings a site can perform differently here than on traditional search or other AI platforms |
| **Freshness weighting** | Citation-tracking research associates content freshness and semantic alignment with Perplexity's source selection specifically, similar to the pattern seen across other AI answer engines |
| **Answer-first structure still applies** | The general self-contained, answer-first structural patterns from **ai-citation-optimization** remain relevant here as elsewhere |

## Workflow

1. Confirm current robots.txt posture toward PerplexityBot, understanding that compliance isn't guaranteed either way.
2. If exclusion is the actual goal, verify at the server level rather than relying on robots.txt alone.
3. Apply general AI-citation structural best practices to priority content.
4. Check content freshness specifically, given Perplexity's apparent freshness weighting.
5. Directly query Perplexity with representative target questions to verify actual citation behavior, since indirect proxies are less reliable for this platform specifically.

## Related Skills

- **ai-crawler-access-audit** (technical): robots.txt configuration and its limits for this specific bot
- **ai-citation-optimization**: General structural patterns applied here
- **geo-crawl-freshness-check**: Freshness signal relevant to Perplexity's selection
