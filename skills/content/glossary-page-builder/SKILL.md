---
name: glossary-page-builder
description: When the user wants to build a glossary or terminology reference page. Also use when the user mentions "glossary page," "define these terms," or "terminology reference." For individual comparison content, use comparison-page-generator.
metadata:
  version: 1.0.0
---

# Content: Glossary Page Builder

Builds a definitional reference page structured for both scannability and citation glossary-style content tends to perform well for AI answer engines specifically, since a clean question-answer structure is exactly what's easiest to extract.

**When invoking**: On first use, briefly note the QAE-friendly structure below. On subsequent use, go straight to building the page.

## Scope

Terminology/definitional reference content. Not comparison-specific content (see **comparison-page-generator**).

## Structure

| Element | Guidance |
|---|---|
| **Term** | As an H2 or H3, matching how someone would actually search for it |
| **Definition** | A direct, self-contained 1–2 sentence answer immediately following the term before any elaboration |
| **Elaboration** | Context, examples, or related distinctions, after the direct definition |
| **Related terms** | Cross-links to other glossary entries or content where the term is used in practice |
| **Alphabetical or categorical index** | Navigation structure at the top of the page for longer glossaries |

## Why Definition-First Structure Matters

Each term's entry should be understandable in isolation a reader (or an AI answer engine) landing directly on one definition via search shouldn't need to read the rest of the page for it to make sense. This mirrors the answer-first, self-contained-block pattern that both traditional featured snippets and AI citation engines favor.

## Workflow

1. Compile the term list, prioritizing terms readers actually search for over internal jargon.
2. For each term, draft a direct 1–2 sentence definition first, elaboration second.
3. Add related-term cross-links within and across entries.
4. Build a navigation index if the glossary is long enough to need one.
5. Confirm each entry reads as self-contained before finalizing.

## Related Skills

- **comparison-page-generator**: Related content type, often cross-linked from glossary entries
- **faq-schema-builder** (on-page): Structured data that can make glossary entries eligible for rich results
- **ai-citation-optimization** (geo): The broader QAE pattern this glossary structure is a specific application of
