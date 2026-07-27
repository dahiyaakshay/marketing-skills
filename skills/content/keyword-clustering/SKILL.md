---
name: keyword-clustering
description: When the user wants to group keywords into clusters that should each map to one page. Also use when the user mentions "keyword clustering," "which keywords belong on the same page," "keyword mapping," or "cluster keywords by intent." For building the pillar/cluster page hierarchy on top of clusters, use topic-cluster-mapping or pillar-page-strategy. For fixing existing overlap, use cannibalization-checker.
metadata:
  version: 1.0.0
---

# Content: Keyword Clustering

Groups keywords by real search-engine-perceived overlap — not just semantic similarity — so each cluster maps cleanly to one page.

**When invoking**: On first use, explain why SERP-based clustering beats pure semantic similarity. On subsequent use, go straight to the clustering output.

## Scope

Keyword-to-page grouping. Not the hub/spoke content architecture built on top of clusters (see **topic-cluster-mapping**, **pillar-page-strategy**) or resolving existing overlap (see **cannibalization-checker**).

## SERP-Based vs. Semantic Clustering

| Method | How it works | Risk |
|---|---|---|
| **SERP-based (preferred)** | Two keywords cluster together if their top-10 ranking URLs overlap by a set threshold — commonly cited thresholds range from 3–4+ shared URLs out of 10 | Most reliable signal of what the search engine itself considers "the same query," since it reflects Google's own judgment rather than a guess |
| **Semantic/embedding-based** | Cluster by cosine similarity between keyword embeddings, typically in the 0.75–0.85 range | Faster to run at scale but risks over-merging keywords that sound related but serve different intents |

The most common clustering mistake is grouping by how similar keywords *sound* rather than checking whether Google already treats them as satisfiable by the same page — semantic-only clustering tends to over-merge.

## Cluster Sizing Guardrails

- **One primary keyword per page**, non-negotiable — this is the foundation that prevents future cannibalization.
- Typical intent-based clusters run **5–15 secondary keywords** alongside the primary; clusters larger than ~15 often actually contain more than one distinct intent and should be split.
- If overlap between two keywords is 0–1 shared top-10 URLs, they very likely warrant **separate pages**, not consolidation.

## Workflow

1. Generate a broad seed list (200–500 keywords is a reasonable range for a new topic area) without filtering aggressively — breadth first, so the clustering has enough signal.
2. Pull top-10 SERP results for each keyword.
3. Group keywords whose top-10 results overlap at or above the chosen threshold.
4. Assign each cluster one primary keyword (highest volume/most central) and list secondaries.
5. Log the primary keyword, target URL, and cluster assignment in a tracking sheet — this single artifact is what prevents cannibalization later.
6. Review the map quarterly, since new content published later can silently create overlap if the map isn't kept current.

## Related Skills

- **topic-cluster-mapping**, **pillar-page-strategy**: Hub/spoke architecture built from these clusters
- **cannibalization-checker**: Detects and resolves overlap that slips past this skill's upfront mapping
- **content-gap-analysis**: Identifies clusters that don't yet have a page at all
