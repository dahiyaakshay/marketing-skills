---
name: topic-cluster-mapping
description: When the user wants to structure a set of keyword clusters into a pillar-and-spoke content architecture. Also use when the user mentions "topic clusters," "content architecture," "hub and spoke," or "how should these pages link to each other." For choosing which single cluster becomes the pillar, use pillar-page-strategy. For the upstream keyword grouping, use keyword-clustering.
metadata:
  version: 1.0.0
---

# Content: Topic Cluster Mapping

Turns a set of keyword clusters into an explicit hub-and-spoke architecture: one pillar page, multiple cluster/spoke pages, and a defined internal linking pattern between them.

**When invoking**: On first use, briefly note that the value comes from the explicit linking pattern, not just grouping pages by topic. On subsequent use, go straight to the map.

## Scope

Structuring already-clustered keywords into a site architecture. Not the keyword grouping itself (see **keyword-clustering**) or the single-pillar selection decision in isolation (see **pillar-page-strategy**).

## Why the Linking Pattern Is the Point

Increased interlinking within a cluster has been shown to correlate with improved rankings across the cluster as a whole — the architecture works because it creates a coherent, interlinked body of work rather than a scattering of one-off posts. In 2026 this structure does double duty: the same hub-and-spoke pattern that helps traditional rankings also creates the semantic map AI answer engines use to judge topical authority and brand association.

## The Linking Pattern

| Link direction | Pattern |
|---|---|
| Hub → Spoke | Pillar page links out to every cluster/spoke page under it |
| Spoke → Hub | Every spoke links back to the pillar, typically in the opening or conclusion |
| Spoke ↔ Spoke | Sibling spoke pages cross-link where topics genuinely overlap (e.g. comparison pages linking to related how-tos) |

Add all internal links at launch rather than deferring them to a future sprint — the interlinking is what makes the architecture work, not an optional polish step.

## Sizing Guidance

A topic-based pillar cluster can reasonably contain 10–20 cluster pages under one pillar; a narrower intent-based cluster typically runs smaller. If a cluster is growing well beyond that range, it likely contains more than one pillar topic and should be split into two architectures.

## Workflow

1. Take the keyword clusters from **keyword-clustering** and group related clusters under a shared parent topic.
2. Select the pillar topic — the broadest, highest-aggregate-volume cluster the site can realistically compete for (see **pillar-page-strategy** for the full selection framework).
3. Map every cluster page's relationship to the pillar and to sibling cluster pages explicitly, rather than leaving it implicit.
4. Assign anchor text variety (exact, partial, semantic) across the internal links to avoid monotony.
5. Ship the pillar and its first several spokes together where possible, with all links live at launch.
6. Review the map periodically for pages that have drifted out of their assigned cluster or created overlap (see **cannibalization-checker**).

## Related Skills

- **keyword-clustering**: Upstream keyword grouping this skill structures into an architecture
- **pillar-page-strategy**: Deeper framework for selecting and building the pillar page itself
- **cannibalization-checker**: Catches overlap that emerges after the architecture is live
- **content-calendar-builder**: Sequencing when each spoke gets published
