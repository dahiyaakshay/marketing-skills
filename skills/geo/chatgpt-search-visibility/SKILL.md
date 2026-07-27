---
name: chatgpt-search-visibility
description: When the user wants to optimize specifically for visibility in ChatGPT Search citations. Also use when the user mentions "ChatGPT Search," "get cited by ChatGPT," or "OAI-SearchBot." For Google's AI Overviews specifically, use ai-overview-optimization. For crawler access rules distinguishing training vs. retrieval bots, use ai-crawler-access-audit (technical category).
metadata:
  version: 1.0.0
---

# GEO: ChatGPT Search Visibility

Optimizes for citation specifically within ChatGPT Search OpenAI's retrieval-augmented search surface, distinct from the base ChatGPT model's training data and distinct from Google's AI Overviews.

**When invoking**: On first use, briefly note the access prerequisite below. On subsequent use, go straight to the optimization plan.

## Scope

ChatGPT Search-specific tactics. For the underlying access-control prerequisite, see **ai-crawler-access-audit** (technical category) a site with OAI-SearchBot blocked cannot appear here regardless of content quality.

## Access Prerequisite

ChatGPT Search's retrieval crawler (OAI-SearchBot) is a separate bot from GPTBot, the training crawler a site can legitimately block GPTBot to opt out of model training while still allowing OAI-SearchBot for citation eligibility. Confirm this distinction is correctly configured before doing any content-level optimization work; blocking the wrong bot is the single most common reason a site's content quality doesn't translate into ChatGPT Search citations.

## Retrieval Rank Correlation

Evidence suggests a meaningful relationship between how well a URL performs in ChatGPT's internal "retrieval rank" (its own index of candidate sources for a query) and whether it's ultimately cited although OpenAI doesn't fully disclose how this retrieval process works, so tactics here are necessarily somewhat less certain than for Google's more studied AI Overviews. Strong performance on fan-out/related sub-queries (see **multi-hop-citation-mapping**) appears to matter here as much as for other AI search surfaces.

## Optimization Checklist

| Area | Action |
|---|---|
| Access | Confirm OAI-SearchBot and ChatGPT-User are allowed even if GPTBot is blocked |
| Structure | Apply the self-contained, answer-first patterns from **ai-citation-optimization** |
| Freshness | Apply **geo-crawl-freshness-check** freshness is broadly cited as a factor across AI search surfaces, ChatGPT Search included |
| Entity clarity | Apply **entity-density-optimizer** so ChatGPT can confidently identify and corroborate the brand/topic |
| Verification | Query ChatGPT Search directly with target questions and check whether the site appears the most reliable verification available given limited disclosure |

## Workflow

1. Confirm crawler access is correctly configured for OAI-SearchBot/ChatGPT-User specifically.
2. Apply general AI-citation structural best practices to priority pages.
3. Check freshness and entity clarity signals.
4. Directly query ChatGPT Search with representative target questions to verify actual citation behavior, since indirect signals are less reliable here than for Google.
5. Track citation appearance over time as a distinct metric from traditional rank or Google AI Overview citation.

## Related Skills

- **ai-crawler-access-audit** (technical): Prerequisite bot-access configuration
- **ai-citation-optimization**: General structural patterns applied here
- **ai-overview-optimization**: Parallel, platform-specific counterpart for Google
- **multi-hop-citation-mapping**: Fan-out query coverage relevant to retrieval rank
