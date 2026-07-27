---
name: content-brief-generator
description: When the user wants to create a writing brief for a new piece of content before drafting begins. Also use when the user mentions "content brief," "writer brief," or "brief for this article." For the actual draft, use blog-post-writer or the relevant page-type skill. For the keyword this brief is built around, use keyword-clustering.
metadata:
  version: 1.0.0
---

# Content: Content Brief Generator

Produces a writer-ready brief that specifies audience, intent, structure, and required sources before any drafting starts the goal is to remove ambiguity a writer would otherwise have to guess at.

**When invoking**: On first use, briefly note the brief's role as a pre-writing artifact. On subsequent use, go straight to producing it.

## Scope

Pre-writing specification. Not the draft itself (see **blog-post-writer** and other page-type skills) or the keyword research that feeds the brief's target term (see **keyword-clustering**).

## Required Brief Components

| Component | Purpose |
|---|---|
| **Primary keyword + 3–5 secondaries** | One primary per page, non-negotiable prevents future cannibalization |
| **Target audience & intent** | Who's reading and what they came to accomplish shapes tone, depth, and structure decisions |
| **Outline (H2/H3 level)** | The subtopic structure, ideally informed by a **content-gap-analysis** against top-ranking competitors |
| **Required sources / data** | Statistics, screenshots, or citations the writer needs to gather, flagged up front rather than discovered mid-draft |
| **Internal link targets** | Which existing pages this piece should link to/from, with proposed anchor text |
| **FAQs** | Common questions the piece should address, often pulled from "People Also Ask" or actual customer questions |
| **Word count / format guidance** | Directional length and whether the format should favor lists, tables, or narrative prose |

## Workflow

1. Confirm the target primary keyword and cluster assignment (see **keyword-clustering**).
2. Run or reference a **content-gap-analysis** to inform the outline against what top-ranking competitors already cover.
3. Define audience and intent explicitly don't leave this implicit.
4. Draft the H2/H3 outline.
5. List required sources/data and internal link targets.
6. Specify format and length guidance, and hand the brief to **blog-post-writer** or the relevant page-type skill.

## Related Skills

- **keyword-clustering**: Supplies the primary/secondary keyword assignment
- **content-gap-analysis**: Informs the outline with competitor coverage
- **blog-post-writer**: Typical downstream consumer of this brief
- **editorial-style-guide**: House style rules the brief should reference rather than restate
