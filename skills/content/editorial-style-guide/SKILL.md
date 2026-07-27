---
name: editorial-style-guide
description: When the user wants to define or apply a house style guide for tone, spelling, punctuation, and formatting across content. Also use when the user mentions "editorial style guide," "house style," "British vs American English," or "our writing standards." This is a reference standard other content skills (blog-post-writer, content-optimizer, content-scoring-rubric) should defer to.
metadata:
  version: 1.0.0
---

# Content: Editorial Style Guide

Defines the house style rules tone, regional spelling, punctuation preferences, formatting conventions that every other content-generating skill in this library should defer to when producing output.

**When invoking**: On first use, ask for or confirm the specific rules if not already established. On subsequent use, apply the established guide silently.

## Scope

The style reference itself. Individual writing skills (**blog-post-writer**, page-type writers, **content-optimizer**) should read and apply this guide rather than duplicating style rules internally.

## Core Categories to Define

| Category | Example decisions to lock in |
|---|---|
| **Regional spelling** | British vs. American English (e.g. "optimise" vs. "optimize," "colour" vs. "color") pick one and apply consistently, including in technical terms where the two conventions diverge |
| **Punctuation** | Oxford comma or not; em dash usage or a ban on them in favor of periods/commas; number formatting (spelled out vs. numerals below a threshold) |
| **Tone** | Formal vs. conversational; first person allowed or avoided; contractions permitted or not |
| **Structural conventions** | Standard heading capitalization (title case vs. sentence case); preferred section naming patterns; standard call-to-action phrasing |
| **Citation/attribution style** | How sources are credited; whether direct quotes are used and how sparingly |
| **Banned words/phrases** | Jargon or filler phrases the house style specifically avoids (e.g. "in today's fast-paced world," "unlock," "leverage" as a verb) |

## Why This Should Be a Shared Reference

Style drift across a content library some pages British English, some American; some with em dashes, some without reads as inconsistent and undermines credibility, especially at scale across many writers or AI-assisted drafts. Defining the rules once, here, and having every other content skill defer to them is more reliable than restating style preferences in every individual brief.

## Workflow

1. Establish or confirm the rules for each core category above.
2. Document them in a single reference (this file, or a project-context.md entry).
3. When any other content skill produces a draft, check its output against this guide before finalizing.
4. Update the guide when a new style decision is made, so it stays the single source of truth rather than drifting out of sync with actual practice.

## Related Skills

- **content-brief-generator**: Should reference this guide rather than restating style rules per brief
- **blog-post-writer** and other page-type writers: Should apply this guide to every draft
- **content-scoring-rubric**: Style-guide alignment is one of its scoring dimensions
