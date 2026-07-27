---
name: content-chunking-for-llms
description: When the user wants to structure content into passage-level chunks that retrieval systems can extract cleanly. Also use when the user mentions "content chunking," "passage-level optimization," or "how do I break this up for AI retrieval." For the broader answer-first structural patterns, use ai-citation-optimization.
metadata:
  version: 1.0.0
---

# GEO: Content Chunking for LLMs

Structures content at the passage level specifically so that retrieval-augmented AI systems which typically process and embed content in chunks, not whole pages can extract clean, complete units of meaning.

**When invoking**: On first use, briefly explain how RAG-based chunking works below. On subsequent use, go straight to restructuring.

## Scope

Passage/chunk-level structuring. This is the mechanical implementation layer beneath the broader structural patterns in **ai-citation-optimization** apply both together.

## How Chunking Works in Retrieval Systems

Most AI answer engines don't retrieve or reason over an entire page at once they split content into smaller passages (often a few hundred words), convert each into a vector embedding, and retrieve individual chunks whose embeddings are most similar to the query. This means a chunk boundary that splits a complete thought in half produces two incomplete, less useful embeddings even if the surrounding page reads perfectly well to a human.

## Chunk-Friendly Structuring Rules

| Rule | Why |
|---|---|
| **One complete idea per section** | A section that requires the previous or following section's context to make sense is likely to be split mid-thought by an automated chunker |
| **Avoid pronoun dependency across sections** | Referring back to "this approach" or "the method above" from a different section breaks if that section is chunked independently restate the referent within the same chunk |
| **Keep supporting evidence with its claim** | Don't separate a statistic or example from the claim it supports by a section boundary chunking may separate them into different embeddings that no longer reinforce each other |
| **Use consistent section length** | Wildly uneven section lengths (one line, then 800 words) can produce inconsistent, less coherent chunks; aim for reasonably even, self-contained blocks |

## Workflow

1. Identify pages targeted for AI citation and review their current section boundaries.
2. Check each section for self-containment read it in isolation and confirm it doesn't rely on other sections for meaning.
3. Rewrite any cross-section pronoun references to restate the referent within the same section.
4. Confirm claims and their supporting evidence stay within the same section.
5. Apply alongside the broader **ai-citation-optimization** patterns (TL;DR blocks, answer-first structure) for full coverage.

## Related Skills

- **ai-citation-optimization**: Broader structural patterns this skill implements at the passage level
- **answer-engine-schema**: Structured data that complements chunk-level content structuring
