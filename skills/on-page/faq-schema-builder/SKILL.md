---
name: faq-schema-builder
description: When the user wants to implement FAQPage schema for question-and-answer content. Also use when the user mentions "FAQ schema," "FAQPage markup," or "FAQ rich results." For general schema type selection, use schema-markup-generator. For AI-citation-specific QAE structuring, use ai-citation-optimization (geo category).
metadata:
  version: 1.0.0
---

# On-Page: FAQ Schema Builder

Implements FAQPage schema for genuine question-and-answer content a well-suited pairing with the answer-first content patterns that also help with AI citation, since both reward explicit, self-contained Q&A structure.

**When invoking**: On first use, briefly confirm the content is genuinely FAQ-formatted, not forced. On subsequent use, go straight to implementation.

## Scope

FAQPage schema implementation specifically. For schema type selection more broadly, see **schema-markup-generator**. For the AI-citation angle on question-answer structuring, see **ai-citation-optimization** (geo category).

## Implementation Format

```
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [{
    "@type": "Question",
    "name": "What is the exact question text?",
    "acceptedAnswer": {
      "@type": "Answer",
      "text": "The direct, complete answer text."
    }
  }]
}
```

## Guidance

| Element | Guidance |
|---|---|
| **Genuine Q&A content only** | Every question in the schema must have a corresponding visible question and answer on the page schema for content not actually visible on the page is a policy violation, not just a bad practice |
| **Complete, self-contained answers** | The answer text should make sense on its own, matching the same self-contained-passage principle that helps AI citation (see **ai-citation-optimization**) |
| **Real questions, not keyword-stuffed variants** | Base questions on genuine reader questions (support tickets, sales conversations, "People Also Ask") rather than manufacturing awkward keyword-variant questions purely for schema coverage |
| **Don't overuse** | Reserve FAQPage schema for pages genuinely structured as FAQ content forcing it onto every page dilutes its signal value and risks appearing manipulative |

## Workflow

1. Confirm the page has genuine, visible question-and-answer content.
2. Draft or confirm each question is phrased the way a real user would ask it.
3. Ensure each answer is complete and self-contained.
4. Implement FAQPage schema matching the visible content exactly.
5. Validate with **structured-data-validator** (technical category).

## Related Skills

- **schema-markup-generator**: General schema selection this specializes for FAQ content
- **ai-citation-optimization** (geo): The QAE (question-answer-evidence) content pattern this schema formalizes
- **glossary-page-builder** (content): Related content type that can pair well with FAQ schema
