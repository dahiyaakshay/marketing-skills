---
name: ai-crawler-access-audit
description: When the user wants to audit, configure, or troubleshoot robots.txt rules for AI crawlers (GPTBot, ClaudeBot, PerplexityBot, Google-Extended, Bytespider, CCBot). Also use when the user mentions "AI crawler," "GPTBot," "ClaudeBot," "PerplexityBot," "block AI training," "llms.txt," "AI bot access," "is my site blocking ChatGPT," or "robots.txt for AI search." For traditional Googlebot/Bingbot robots.txt rules, use robots-txt. For GEO strategy overall, use generative-engine-optimization. For rendering/JS-blocking issues affecting crawlers, use rendering-strategies.
metadata:
  version: 1.0.0
---

# Technical: AI Crawler Access Audit

Audits and configures robots.txt so a site is correctly positioned between two competing goals: keeping proprietary content out of AI model training data, and staying eligible for citation in AI-generated answers (ChatGPT, Claude, Perplexity, Google AI Overviews). These are not the same decision — treating "AI crawler" as one category is the most common mistake in this space.

**When invoking**: On first use, briefly explain the training-vs-retrieval distinction below before producing the audit or robots.txt block. On subsequent use, go straight to output.

## Scope

This skill covers robots.txt directives for AI-related user-agents only. It does not cover llms.txt authoring (see **llms-txt-generator**), general robots.txt hygiene for traditional search engines (see **robots-txt**), or content structure for citation (see **generative-engine-optimization**).

## The Core Distinction: Training vs. Retrieval vs. On-Demand

Every major AI lab runs multiple, independently-governed bots. Blocking the wrong one has the opposite effect of what most site owners intend.

| Category | Purpose | Respects robots.txt? | Effect of blocking |
|---|---|---|---|
| **Training crawlers** | Bulk crawl to build foundation-model training sets | Yes (OpenAI, Anthropic, Google) | Content excluded from future model training only — no effect on real-time citation |
| **Search/retrieval crawlers** | Index content for citation in live AI answers | Yes (documented, though enforcement varies) | Content becomes ineligible for citation in that platform's answers |
| **On-demand/user-triggered fetchers** | Fetch a specific URL when a user asks the assistant to visit it | Inconsistently — some labs note these may not follow robots.txt the same way as automated crawlers | Blocking may not reliably stop a single-page fetch triggered by a user |

## Bot-by-Bot Reference (2026)

| Bot | Operator | Category | Typical posture |
|---|---|---|---|
| GPTBot | OpenAI | Training | Block if avoiding model training; does not affect ChatGPT Search |
| OAI-SearchBot | OpenAI | Retrieval | Allow — blocking removes the site from ChatGPT Search citations |
| ChatGPT-User | OpenAI | On-demand | Allow; may not fully respect standard robots.txt blocking |
| ClaudeBot | Anthropic | Training | Block if avoiding model training |
| Claude-SearchBot | Anthropic | Retrieval | Allow — powers Claude's web search citations |
| Claude-User | Anthropic | On-demand | Allow |
| PerplexityBot | Perplexity | Retrieval (self-built index) | Allow — Perplexity has been reported running non-compliant stealth crawling in some cases, so robots.txt alone is not a guaranteed block |
| Google-Extended | Gemini/AI Overviews | Training | Block to opt out of Gemini training without affecting standard Google Search indexing |
| Bytespider | ByteDance | Training | Commonly blocked; documented history of non-compliance |
| CCBot | Common Crawl | Training (feeds many downstream models) | Commonly blocked if avoiding indirect training exposure |
| Amazonbot, Applebot-Extended, Cohere-ai | Amazon/Apple/Cohere | Training | Case-by-case per training-data policy |

Verify bot identity via reverse DNS lookup rather than trusting the user-agent string alone, since user-agents can be spoofed.

## Decision Framework

Ask two questions before writing any rule:

1. **Training-data policy**: Is it acceptable for this content to be used to train future foundation models?
2. **Visibility priority**: Does this business depend on being cited in ChatGPT Search, Perplexity, or AI Overviews answers?

| Posture | When to use | Rule pattern |
|---|---|---|
| **Open** | Visibility is the priority; training-data concerns are secondary (media, SaaS docs, consultancies) | Allow all major AI bots |
| **Selective** (most common in 2026) | Want citation eligibility but not training exposure | Block GPTBot, ClaudeBot, Google-Extended, CCBot, Bytespider; allow OAI-SearchBot, Claude-SearchBot, Claude-User, ChatGPT-User, PerplexityBot |
| **Closed** | Content is proprietary/paywalled and citation is not a priority | Block all AI bots |

## robots.txt Template — Selective Posture (most common)

```
# Block training crawlers
User-agent: GPTBot
Disallow: /

User-agent: ClaudeBot
Disallow: /

User-agent: Google-Extended
Disallow: /

User-agent: CCBot
Disallow: /

User-agent: Bytespider
Disallow: /

# Allow retrieval/citation crawlers
User-agent: OAI-SearchBot
Allow: /

User-agent: ChatGPT-User
Allow: /

User-agent: Claude-SearchBot
Allow: /

User-agent: Claude-User
Allow: /

User-agent: PerplexityBot
Allow: /

Sitemap: https://example.com/sitemap.xml
```

Adjust per path if only part of the site should be citable (e.g. allow `/blog/` and `/docs/`, disallow `/account/` and `/checkout/`).

## Audit Workflow

1. **Pull current robots.txt** and list every AI-related user-agent rule already present (or absent — absence means the default `User-agent: *` rule applies to AI bots too).
2. **Classify each bot** referenced against the table above; flag any training bot left open unintentionally, and any retrieval bot blocked unintentionally (this is the single most common misconfiguration — sites blanket-block "GPTBot" thinking it covers ChatGPT Search, when OAI-SearchBot is the separate bot that actually powers citations).
3. **Cross-check server logs** for actual crawler traffic and bandwidth to confirm bots are respecting the published rules.
4. **Recommend a posture** (open/selective/closed) based on the two-question framework above.
5. **Output a copy-paste robots.txt block** plus a one-line rationale per bot.
6. **Flag non-compliant bots** (Bytespider, some Perplexity stealth crawling reports) — note that server-level or WAF blocking is the only reliable defense, since robots.txt is advisory only.

## Related Skills

- **robots-txt**: General robots.txt syntax and traditional search engine rules
- **generative-engine-optimization**: Overall GEO/AEO strategy; this skill is the access-control prerequisite for citation
- **rendering-strategies**: AI crawlers generally do not execute JavaScript — content must be present in initial HTML regardless of robots.txt configuration
- **llms-txt-generator**: Complementary positive-signal file alongside robots.txt
- **site-crawlability**: Broader crawl-budget and indexability audit
