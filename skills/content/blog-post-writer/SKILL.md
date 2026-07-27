---
name: blog-post-writer
description: When the user wants to draft a blog post or article from a brief or topic. Also use when the user mentions "write a blog post," "draft an article," or "blog content." For the pre-writing brief this should follow, use content-brief-generator. For house style rules, defer to editorial-style-guide. For scoring the draft afterward, use content-optimizer.
metadata:
  version: 1.0.0
---

# Content: Blog Post Writer

Drafts a blog post from a brief, applying house style and structural best practice assumes the strategic groundwork (keyword, audience, outline) is already done via **content-brief-generator**.

**When invoking**: On first use, confirm a brief exists or gather the minimum needed (topic, audience, primary keyword) before drafting. On subsequent use, go straight to drafting.

## Scope

Drafting the post itself. Not the pre-writing brief (see **content-brief-generator**), house style definition (see **editorial-style-guide**), or post-draft scoring (see **content-optimizer**).

## Structural Defaults

| Element | Default guidance |
|---|---|
| **Opening** | Lead with the reader's problem or the direct answer, not a broad throat-clearing intro |
| **Headings** | H2 per major subtopic, H3 for sub-points; each H2 should be able to stand alone if extracted |
| **Length** | Match depth to what's needed to competitively cover the topic (see brief), not an arbitrary word count |
| **Formatting** | Break up long paragraphs; use lists/tables where they aid scanning, not for their own sake |
| **Close** | End with a clear next step or takeaway, not a generic summary restating the intro |

## Workflow

1. Confirm or request the brief (topic, primary keyword, audience, outline, required sources).
2. Apply house style rules from **editorial-style-guide** (spelling convention, punctuation, tone) throughout.
3. Draft following the brief's outline, leading each section with its direct point before elaborating.
4. Insert internal links per the brief's specified targets.
5. Hand the finished draft to **content-optimizer** for scoring before publication.

## Related Skills

- **content-brief-generator**: Upstream pre-writing specification
- **editorial-style-guide**: Style rules applied throughout drafting
- **content-optimizer**: Post-draft scoring and edit pass
