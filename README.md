# Marketing Skills (Akshay Dahiya)

100 Agent Skills for SEO, Content, and GEO (Generative Engine Optimization) — markdown skill files following the Agent Skills spec, no lock-in to a single tool. Works with Claude Code, Cursor, Claude.ai (paste the SKILL.md contents), and any agent supporting the spec.

## Structure

```
skills/
  technical/   (13)  robots.txt, crawlability, redirects, canonical, Core Web Vitals, AI crawler access
  on-page/     (10)  title tags, meta descriptions, schema, headings, internal linking
  content/     (29)  content strategy, scoring, keyword clustering, all page-type writers
  off-page/    (8)   backlinks, digital PR, outreach, brand mentions
  local/       (6)   Google Business Profile, local citations, multi-location SEO
  paid/        (8)   PPC ad copy, Quality Score, CRO, remarketing, negative keywords
  analytics/   (8)   GA4, attribution, funnels, dashboards, reporting
  geo/         (15)  AI citation optimization, AI Overviews, ChatGPT Search, Perplexity, entity strategy
  strategy/    (3)   audits-to-roadmaps, proposals, client onboarding
templates/
  project-context.md   fill in per-project so skills produce tailored, non-generic output
  SKILL-TEMPLATE.md    blank skeleton for writing additional skills in the same format
```

**100 skills total**, each a folder containing a single `SKILL.md` with YAML frontmatter (`name`, `description`, `metadata.version`) followed by the skill body. Every skill cross-references related skills by name so an agent — or a human — can navigate between them.

## Install

**Clone everything:**
```
git clone https://github.com/<your-username>/marketing-skills.git
cp -r marketing-skills/skills/* .cursor/skills/
cp -r marketing-skills/templates .cursor/
```

**Individual skill:** copy a single skill folder into `.claude/skills/`, `.cursor/skills/`, or `.agents/skills/` depending on your agent.

**Claude.ai / ChatGPT (no file system access):** open the relevant `SKILL.md` and paste its contents directly into the conversation.

## Add Project Context

Skills read `project-context.md` automatically if present in `.claude/` or `.cursor/`. Copy the template from `templates/project-context.md` and fill in your product, audience, and brand voice — without this, output stays generic.

## Skill Directory

### Technical (13)

| Skill | Covers |
|---|---|
| technical-seo-audit | Umbrella technical health check, sequences the skills below |
| ai-crawler-access | robots.txt rules for GPTBot, ClaudeBot, PerplexityBot, Google-Extended |
| robots-txt-generator | Traditional search engine crawler rules |
| xml-sitemap-builder | Sitemap structure and hygiene |
| canonical-tag-strategy | Resolving duplicate/near-duplicate URLs |
| redirect-chain-audit | Detecting and flattening redirect chains and loops |
| crawl-budget-optimizer | Directing crawler attention on large sites |
| core-web-vitals-audit | LCP, INP, CLS diagnosis and fixes |
| mobile-first-indexing-check | Mobile/desktop content parity |
| structured-data-validator | Schema syntax and consistency validation |
| hreflang-implementation | Multi-language/region page targeting |
| javascript-seo-audit | JS-rendering visibility for crawlers |
| site-migration-checklist | Pre/during/post migration sequencing |

### On-Page (10)

| Skill | Covers |
|---|---|
| title-tag-optimizer | Title tag copy and length |
| meta-description-writer | Meta description CTR optimization |
| heading-hierarchy-audit | H1–H6 structure and accessibility |
| schema-markup-generator | Schema type selection by content type |
| image-alt-text-writer | Accessible, non-spammy alt text |
| internal-linking-strategy | Link equity distribution, orphan pages |
| url-structure-optimizer | URL slug design and stability |
| pagination-seo | Multi-page series canonicalization |
| breadcrumb-implementation | Breadcrumb UI and schema |
| faq-schema-builder | FAQPage schema for Q&A content |

### Content (29)

| Skill | Covers |
|---|---|
| content-gap-analysis | Site-wide topical coverage vs. competitors |
| keyword-clustering | SERP-based keyword-to-page grouping |
| content-brief-generator | Pre-writing specification |
| topic-cluster-mapping | Hub-and-spoke content architecture |
| pillar-page-strategy | Selecting and structuring pillar pages |
| cannibalization-checker | Resolving competing owned pages |
| content-refresh-audit | Detecting and prioritizing content decay |
| content-pruning-audit | Prune/merge/redirect/delete decisions |
| evergreen-content-identifier | Classifying durable vs. time-sensitive topics |
| competitor-content-audit | Ongoing competitor publishing monitoring |
| content-calendar-builder | Sequencing and scheduling publication |
| content-scoring-rubric | Library-wide quality standard |
| editorial-style-guide | House style reference for all content skills |
| content-repurposing-planner | Adapting content across formats/channels |
| content-optimizer | Single-page SEO/readability scoring |
| blog-post-writer | Blog post drafting from a brief |
| landing-page-copywriter | Conversion-focused landing page copy |
| product-page-optimizer | E-commerce product page copy/structure |
| category-page-writer | Category/collection page copy |
| case-study-writer | Problem-solution-result case studies |
| whitepaper-structuring | Long-form research report structure and credibility |
| press-release-writer | Journalistic-format announcements |
| comparison-page-generator | Fair "X vs Y" comparison pages |
| glossary-page-builder | Definitional/terminology reference pages |
| pricing-page-optimizer | Pricing tier copy and structure |
| about-page-writer | Company/founder story pages |
| testimonials-generator | Short-form customer quote content |
| showcase-page-builder | Portfolio/work gallery pages |
| changelog-writer | Product update/release note formatting |

### Off-Page (8)

| Skill | Covers |
|---|---|
| backlink-audit | Existing backlink profile health, toxic link detection |
| competitor-backlink-gap | Domains linking to competitors but not you |
| link-prospecting | Broad-based link opportunity discovery |
| guest-post-outreach | Guest post pitch drafting |
| haro-response-writer | Journalist source-request responses |
| digital-pr-pitch-writer | Proactive story/data pitches to journalists |
| broken-link-building | Dead-link discovery and replacement pitches |
| brand-mention-monitor | Web-wide linked/unlinked mention tracking |

### Local (6)

| Skill | Covers |
|---|---|
| gbp-optimizer | Google Business Profile optimization |
| local-citation-audit | NAP consistency across directories |
| local-landing-page-builder | Genuinely differentiated location pages |
| review-response-writer | Owner responses to customer reviews |
| local-schema-markup | LocalBusiness structured data |
| multi-location-seo | Architecture across many physical locations |

### Paid (8)

| Skill | Covers |
|---|---|
| ppc-ad-copy-writer | Search ad copy, tight ad-group alignment |
| quality-score-optimizer | Improving Google Ads Quality Score components |
| paid-search-keyword-negative-list | Negative keyword strategy |
| ab-test-planner | Structured, single-variable test design |
| ad-fatigue-detector | Diagnosing creative/audience fatigue |
| remarketing-audience-builder | Behavior-based retargeting segments |
| utm-tracking-setup | Standardized campaign tagging |
| landing-page-cro-audit | Structural conversion-friction audit |

### Analytics (8)

| Skill | Covers |
|---|---|
| ga4-audit | GA4 configuration and data-quality audit |
| attribution-model-selector | DDA vs. last-click selection and verification |
| conversion-funnel-analysis | Stage-by-stage drop-off diagnosis |
| traffic-anomaly-detector | Diagnosing sudden traffic spikes/drops |
| kpi-dashboard-builder | Audience-first dashboard metric design |
| rank-tracking-summary | Ranking movement vs. SERP noise |
| seo-reporting-dashboard | Combined analytics/rank/technical SEO reporting |
| client-report-writer | Narrative client-facing reporting |

### GEO (15)

| Skill | Covers |
|---|---|
| ai-citation-optimization | Structuring content for AI answer-engine citation |
| ai-overview-optimization | Google AI Overview-specific citation tactics |
| chatgpt-search-visibility | ChatGPT Search-specific citation tactics |
| perplexity-citation-audit | Perplexity-specific citation tactics |
| llm-retrievability-audit | End-to-end access/render/extraction audit |
| entity-density-optimizer | Entity clarity and disambiguation for AI citation |
| entity-type-citation-strategy | Strategy differentiated by entity type |
| geo-crawl-freshness-check | AI-specific content freshness diagnosis |
| multi-hop-citation-mapping | Fan-out query coverage |
| content-chunking-for-llms | Passage-level structuring for RAG retrieval |
| answer-engine-schema | AI-citation-priority structured data |
| geo-vs-seo-gap-analysis | Where traditional rank and AI citation diverge |
| brand-mention-in-ai-answers | Named-mention tracking in AI-generated answers |
| geo-competitive-benchmark | AI-citation share vs. competitors |
| local-business-llm-visibility | AI recommendation visibility for local businesses |

### Strategy (3)

| Skill | Covers |
|---|---|
| seo-audit-to-roadmap | Turning audit findings into a prioritized plan |
| seo-proposal-writer | Client-facing engagement proposals |
| client-onboarding-questionnaire | New-client intake feeding project-context and reporting |

## Status

100 skills complete across all 9 categories. Built by [Akshay Dahiya](https://akshaydahiya.site) — GEO researcher and developer of AI Spider (AI retrievability audit), MarAI (AI marketing ops), and RankScan (AI visibility research).
