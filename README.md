# Marketing Skills (Akshay Dahiya)

Agent Skills for SEO, Content, and GEO (Generative Engine Optimization). Markdown skill files following the Agent Skills spec — no lock-in to a single tool. Works with Claude Code, Cursor, Claude.ai (paste the SKILL.md contents), and any agent supporting the spec.

## Structure

```
skills/
  technical/       robots.txt, crawlability, redirects, canonical, AI crawler access
  on-page/         title tags, meta, schema, headings
  content/         content strategy, scoring, page-type writers
  off-page/        backlinks, digital PR, outreach
  local/           Google Business Profile, local citations
  paid/            PPC, CRO, remarketing
  analytics/       GA4, reporting, attribution
  geo/             AI citation optimization, AI Overviews, Perplexity/ChatGPT/Claude visibility
  strategy/        cross-cutting strategy and meta skills
templates/
  project-context.md   fill in per-project so skills produce tailored, non-generic output
```

Each skill is a folder containing a single `SKILL.md` with YAML frontmatter (`name`, `description`, `metadata.version`) followed by the skill body.

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

| Skill | Category | Covers |
|---|---|---|
| ai-crawler-access-audit | technical | robots.txt rules for GPTBot, ClaudeBot, PerplexityBot, Google-Extended |
| content-optimizer | content | Scoring existing drafts for SEO, readability, topical depth |
| ai-citation-optimization | geo | Structuring content to be extracted/cited by AI answer engines |

*(Full list grows as skills are added — see individual folders.)*

## Status

Early-stage, actively expanding. Built by [Akshay Dahiya](https://akshaydahiya.site) — GEO researcher and developer of AI Spider (AI retrievability audit), MarAI (AI marketing ops), and RankScan (AI visibility research).
