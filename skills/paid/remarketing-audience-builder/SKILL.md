---
name: remarketing-audience-builder
description: When the user wants to build or segment remarketing/retargeting audiences. Also use when the user mentions "remarketing audience," "retargeting segments," or "who should we retarget." For detecting when an existing audience needs refreshing due to fatigue, use ad-fatigue-detector.
metadata:
  version: 1.0.0
---

# Paid: Remarketing Audience Builder

Segments remarketing audiences by behavior and funnel stage rather than treating "everyone who visited the site" as a single undifferentiated audience different behaviors warrant meaningfully different messaging and, often, different bids.

**When invoking**: On first use, briefly note the segmentation principle below. On subsequent use, go straight to building the audience structure.

## Scope

Audience construction and segmentation. For detecting when an existing audience has become fatigued and needs refreshing, see **ad-fatigue-detector**.

## Segmentation Framework

| Segment | Behavior | Messaging approach |
|---|---|---|
| **General site visitors** | Visited any page, no specific high-intent action | Broad brand awareness / soft re-engagement messaging |
| **Product/category viewers** | Viewed specific product or category pages without adding to cart | Highlight the specific product category viewed, address common objections |
| **Cart abandoners** | Added to cart, didn't complete checkout | Direct, urgency-appropriate messaging addressing likely abandonment reasons (shipping cost, payment options) this segment typically converts at a meaningfully higher rate than general visitors given proximity to purchase |
| **Past customers** | Completed a prior purchase | Upsell/cross-sell or replenishment messaging, distinct from acquisition-focused messaging for new visitors |

## Recency and Duration Considerations

Segment lookback windows by how the buying cycle actually behaves for the product a short-consideration-cycle product warrants a shorter remarketing window (recent visitors are far more likely to convert than someone who visited months ago), while a longer-consideration B2B purchase may warrant a longer window matched to the realistic sales cycle length.

## Workflow

1. Define segments based on actual behavioral distinctions (page type visited, cart status, past purchase), not just "visited the site."
2. Set lookback windows appropriate to the product's realistic consideration cycle.
3. Match messaging and offer intensity to each segment's proximity to conversion cart abandoners warrant more direct, urgency-oriented messaging than general visitors.
4. Exclude converted customers from acquisition-focused segments to avoid wasted spend re-pitching people who already bought.
5. Monitor each segment for fatigue separately (see **ad-fatigue-detector**), since different segments will fatigue at different rates depending on audience size and frequency.

## Related Skills

- **ad-fatigue-detector**: Detects when a segment's creative needs refreshing
- **conversion-funnel-analysis** (analytics): Informs which funnel-stage segments are worth building
