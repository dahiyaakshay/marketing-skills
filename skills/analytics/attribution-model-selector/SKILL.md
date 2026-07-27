---
name: attribution-model-selector
description: When the user wants to choose or evaluate which conversion attribution model to use in GA4 or Google Ads. Also use when the user mentions "attribution model," "data-driven attribution," "last click," "which channel gets credit," "DDA," or "why do my Ads and GA4 numbers not match." For fixing the underlying GA4 setup this depends on, use ga4-audit. For funnel-stage analysis once a model is chosen, use conversion-funnel-analysis.
metadata:
  version: 1.0.0
---

# Analytics: Attribution Model Selector

Helps choose between GA4's attribution model options and diagnose when the selected model isn't actually running as expected. As of 2023, Google removed first-click, linear, time-decay, and position-based attribution from GA4, leaving a binary choice between data-driven attribution (DDA) and last-click — this narrows the decision but raises the stakes, since the only real lever left is data quality feeding the machine-learning model.

**When invoking**: On first use, explain the binary-choice context (models were reduced from five to two) before recommending one. On subsequent use, go straight to the recommendation.

## Scope

Covers model selection and verification within GA4/Google Ads. Does not cover the underlying data-quality prerequisites (see **ga4-audit**) or campaign-level UTM structure (see **utm-tracking-setup**).

## The Two Available Models

| Model | How it assigns credit | Minimum data requirement | Best fit |
|---|---|---|---|
| **Data-driven attribution (DDA)** | Machine learning compares converting vs. non-converting journeys and calculates each touchpoint's probabilistic contribution | Commonly cited thresholds are roughly 400+ conversions for the specific key event and 20,000+ total conversions across all key events within the lookback window — thresholds have been reported inconsistently across sources and should be verified against current GA4 documentation for the property in question | Higher-volume properties with genuine multi-touch customer journeys (e-commerce, longer B2B cycles) |
| **Last-click** | 100% credit to the final non-direct touchpoint before conversion | No minimum | Lower-volume properties, simple single-session conversion paths, or as a sanity-check baseline against DDA |

Both models handle Direct traffic the same way: when a journey includes Direct plus any other channel, all credit goes to the other channel — Direct only receives credit when the entire journey consists solely of Direct visits.

## The Silent Fallback Problem

GA4 does not notify when data-driven attribution falls back to last-click due to insufficient data for a given key event — many marketers believe they're running DDA when they're actually getting last-click results. This makes verification, not just selection, part of this skill's job.

## Decision Framework

| Situation | Recommendation |
|---|---|
| High-volume e-commerce or SaaS with clear multi-touch journeys, meets DDA's data threshold | Use DDA — it's GA4's ML-driven default and generally the more accurate reflection of real contribution |
| Low monthly conversion volume, single-session or single-channel journeys | Last-click is simpler, more transparent, and won't silently degrade since there's no fallback state to worry about |
| Need to sanity-check whether DDA is actually active | Compare the Model Comparison report — if DDA and last-click show identical numbers, DDA isn't functioning for that key event, and the volume threshold likely isn't met |
| Different conversion types have very different sales cycles (e.g. newsletter signup vs. enterprise deal) | Configure attribution and lookback window per-conversion-event rather than property-wide, matching the lookback window to each event's actual sales cycle length |
| Comparing GA4 performance against Meta Ads or another platform | Expect numbers not to reconcile — GA4 uses session-scoped attribution and only credits interactions generating a tracked session, while platforms like Meta count broader ad interactions and view-through conversions; this is a structural difference, not a bug in either system |

## Workflow

1. **Check current model** at Admin → Attribution Settings → Reporting attribution model.
2. **Verify DDA is actually active** (not silently fallen back to last-click) via the Model Comparison report.
3. **Check conversion volume** against the documented thresholds for the specific key event in question.
4. **Recommend per-event configuration** where sales cycles differ meaningfully across conversion types, rather than a single property-wide setting.
5. **Set expectations** for cross-platform comparison — flag to the user that GA4 vs. Ads vs. third-party ad platform numbers are structurally different, not a data error to chase down.

## Related Skills

- **ga4-audit**: Data quality and configuration prerequisites this model choice depends on
- **conversion-funnel-analysis**: Stage-level analysis that complements channel-level attribution
- **utm-tracking-setup**: Consistent campaign tagging needed for attribution to work correctly across channels
- **kpi-dashboard-builder**: Where attribution-adjusted conversion numbers typically get reported
