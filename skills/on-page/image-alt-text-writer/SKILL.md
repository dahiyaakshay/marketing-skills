---
name: image-alt-text-writer
description: When the user wants to write alt text for images. Also use when the user mentions "alt text," "image alt attributes," or "accessibility for images." For product image alt text specifically, cross-reference product-page-optimizer (content category).
metadata:
  version: 1.0.0
---

# On-Page: Image Alt Text Writer

Writes alt text serving its primary purpose — describing the image for screen reader users and when images fail to load — with SEO benefit as a secondary, natural byproduct rather than the primary goal.

**When invoking**: On first use, briefly note the accessibility-first framing below. On subsequent use, go straight to drafting.

## Scope

Alt text content for images generally. For product-specific image alt text conventions, see **product-page-optimizer** (content category).

## Core Principle: Accessibility First

Alt text exists primarily to describe an image to someone who can't see it — a screen reader reads the alt text aloud, and browsers display it when an image fails to load. Writing alt text as if it were a keyword-stuffing opportunity ("shoes buy cheap shoes online shoe sale") fails the accessibility purpose entirely and reads as spam to search engines, which can suppress rather than help the page's ranking.

## Guidance by Image Type

| Image type | Alt text approach |
|---|---|
| **Informative image** (illustrates content) | Describe what's visually shown, relevant to the surrounding content — specific enough to convey the same information a sighted reader gets |
| **Decorative image** (visual flourish, no informational content) | Use an empty alt attribute (`alt=""`) rather than a forced description — this tells screen readers to skip it, which is the correct accessible behavior for purely decorative images |
| **Functional image** (e.g. an image used as a button/link) | Describe the function/destination, not the visual appearance — "Submit form" not "blue arrow icon" |
| **Complex image** (chart, infographic, diagram) | A concise alt text plus a longer text description elsewhere on the page (or a `longdesc`/adjacent caption) for the full data |

## Workflow

1. Determine the image's purpose: informative, decorative, or functional.
2. For decorative images, use an empty alt attribute rather than forcing a description.
3. For informative/functional images, write a concise, specific description of what's shown or what the image does — not a keyword list.
4. Naturally incorporate the target keyword only where it genuinely describes the image accurately, never forced.
5. Avoid phrases like "image of" or "picture of" — screen readers already announce that it's an image.

## Related Skills

- **product-page-optimizer** (content): Product-specific alt text conventions
- **content-optimizer** (content): Broader on-page scoring alt text quality feeds into
