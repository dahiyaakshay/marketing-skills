---
name: ppc-ad-copy-writer
description: When the user wants to write PPC ad copy (Google Ads, Bing Ads, or similar search ad platforms). Also use when the user mentions "PPC ad copy," "write search ads," or "responsive search ads." For Quality Score implications of ad copy, use quality-score-optimizer. For the destination page, use landing-page-copywriter (content category).
metadata:
  version: 1.0.0
---

# Paid: PPC Ad Copy Writer

Writes search ad copy structured for tight keyword-to-ad alignment since ad relevance and expected CTR (both Quality Score components) depend directly on how specifically the ad copy speaks to the exact keyword/ad group it's paired with.

**When invoking**: On first use, confirm the target keyword theme for the ad group before drafting. On subsequent use, go straight to drafting.

## Scope

Ad copy for search ad platforms. For the Quality Score mechanics this copy influences, see **quality-score-optimizer**. For the destination landing page, see **landing-page-copywriter** (content category).

## Structural Elements (Responsive Search Ads)

| Element | Guidance |
|---|---|
| **Headlines (multiple, platform pins/rotates)** | Include the primary keyword theme in at least one headline; vary the remaining headlines across benefit, differentiator, and call-to-action angles rather than repeating the same message |
| **Descriptions** | Expand on the value proposition with specificity numbers, guarantees, or concrete outcomes outperform generic claims |
| **Ad group tightness** | Ad copy should speak directly to the specific keyword theme of its ad group a single generic ad spread across a broad, loosely-related ad group underperforms multiple tightly-themed ad groups each with their own matched copy |
| **Extensions (sitelinks, callouts, structured snippets)** | Add relevant extensions where available they increase ad real estate and give additional specific reasons to click, both supporting expected CTR |

## Why Tight Ad Group Structure Matters for Copy

Ad relevance (a Quality Score component) is directly a function of whether the ad's copy addresses the intent behind the specific keyword that triggered it a well-written but generic ad spread across many loosely related keywords will score worse on relevance than a more specifically-written ad matched to a tighter keyword theme, even if the generic ad is objectively well-crafted copy.

## Workflow

1. Confirm the specific keyword theme for the ad group this copy will serve.
2. Draft multiple headline variants covering keyword-inclusion, benefit, differentiator, and CTA angles.
3. Draft description lines with specific, concrete value propositions rather than generic claims.
4. Confirm the copy speaks directly to this ad group's specific keyword theme, not a broader generic message reused across ad groups.
5. Add relevant ad extensions.
6. Route to **quality-score-optimizer** for a relevance/CTR check once live data accumulates.

## Related Skills

- **quality-score-optimizer**: The scoring mechanics this copy directly influences
- **landing-page-copywriter** (content): Destination page that should match this ad's specific promise
- **ab-test-planner**: Testing different ad copy variants systematically
