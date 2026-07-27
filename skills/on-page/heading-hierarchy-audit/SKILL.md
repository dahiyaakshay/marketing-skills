---
name: heading-hierarchy-audit
description: When the user wants to audit or fix the H1-H6 heading structure of a page. Also use when the user mentions "heading hierarchy," "H1 H2 structure," or "heading tags audit." For scannable structure more broadly, use content-optimizer (content category).
metadata:
  version: 1.0.0
---

# On-Page: Heading Hierarchy Audit

Audits and fixes a page's heading tag structure (H1 through H6) for correct nesting and single-H1 convention — headings serve both accessibility (screen readers rely on heading structure for navigation) and search engines' understanding of content organization.

**When invoking**: On first use, briefly note the accessibility dimension alongside the SEO one. On subsequent use, go straight to the audit.

## Scope

Heading tag structure specifically. For broader scannability and formatting, see **content-optimizer** (content category).

## Structural Rules

| Rule | Why |
|---|---|
| **One H1 per page** | The H1 should represent the single main topic of the page — multiple H1s create ambiguity about what the page is actually about, both for search engines and for screen reader users navigating by heading |
| **No skipped levels** | H2 should not jump straight to H4 without an intervening H3 — skipped levels break the logical outline structure that both crawlers and assistive technology rely on |
| **Headings reflect actual structure, not just styling** | Using an H3 tag purely because it renders at a desired font size, when it should logically be a paragraph with bold text or a different structural element, misrepresents the page's actual content hierarchy |
| **Keyword-relevant but natural** | H2s should reflect the actual subtopics naturally, incorporating relevant secondary keywords where they fit — forcing keywords into headings that read awkwardly hurts both readability and trust |

## Common Failures

- Multiple H1s from a CMS template that defaults to H1 styling for both the page title and a hero banner headline.
- Heading levels used purely for visual sizing rather than actual document structure (a common byproduct of drag-and-drop page builders).
- Missing headings entirely on long-form content, relying only on bold text or visual spacing to imply structure — this loses both the SEO and accessibility benefit of proper heading tags.

## Workflow

1. Extract the full heading structure (H1–H6) for the page in document order.
2. Confirm exactly one H1 exists and it represents the page's main topic.
3. Check for skipped heading levels in the nesting.
4. Confirm each heading reflects actual content structure, not just visual styling choices.
5. Check that H2s naturally incorporate relevant subtopic/keyword language where appropriate.
6. Fix any CMS template issue causing duplicate H1s at the source, not just on the individual page.

## Related Skills

- **content-optimizer** (content): Broader scannability and structure scoring
- **schema-markup-generator**: Structured data that can complement (not replace) proper heading structure
