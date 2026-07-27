---
name: traffic-anomaly-detector
description: When the user wants to investigate a sudden traffic spike or drop, or set up ongoing monitoring for unexpected changes. Also use when the user mentions "traffic dropped," "sudden spike," "why did sessions crash," "anomaly detection," or "did we get hit by an algorithm update." For one-time GA4 configuration audits (as opposed to ongoing monitoring), use ga4-audit. For rank-specific drops, use rank-tracking-summary.
metadata:
  version: 1.0.0
---

# Analytics: Traffic Anomaly Detector

Diagnoses a sudden, unexplained change in traffic by working through causes in order of likelihood — tracking/measurement errors first, then external and seasonal explanations, then genuine algorithm or competitive shifts last. Most "traffic crashed overnight" investigations end at a broken tag or a filter change, not a Google update, so the workflow is ordered to catch the boring explanation before chasing the dramatic one.

**When invoking**: On first use, note the diagnostic order (measurement → external → genuine) before running the checklist. On subsequent use, go straight to the diagnosis.

## Scope

Covers diagnosing a specific anomaly after it's been noticed. Does not cover the standing GA4 configuration checklist this depends on (see **ga4-audit**) or keyword-ranking-specific drops (see **rank-tracking-summary**).

## Diagnostic Order

| Step | Check | Rules out |
|---|---|---|
| 1. Measurement | Was there a recent site relaunch, template change, new subdomain, tag manager publish, or CMP/consent-banner change? Is the data stream still "Receiving data"? | Tracking breakage — the single most common cause of an apparent traffic "crash" that isn't a real traffic change at all |
| 2. Segmentation | Does the drop appear across all channels/devices, or is it isolated to one (e.g. only organic, only mobile)? | An isolated drop points to a channel-specific cause (deindexing, ad account pause, referral source change) rather than a site-wide issue |
| 3. Seasonality & calendar | Is there a comparable period last year, last month, or last week showing the same pattern? Holidays, weekends, industry seasonality? | Normal cyclical variation being mistaken for an anomaly |
| 4. External events | Site outage, DNS issue, CDN problem, payment processor down, major news event affecting the industry | Infrastructure or external-world causes unrelated to search/marketing performance |
| 5. Platform-side changes | Search engine algorithm update, ad platform policy change, referral partner change | Only investigate this once 1–4 are ruled out |
| 6. Competitive | A competitor launched something, ran a major campaign, or a new entrant is capturing shared demand | Last resort explanation — hardest to verify, easiest to reach for prematurely |

## Why Order Matters

Jumping straight to "we got hit by an algorithm update" without first checking whether the data stream is even receiving data correctly is the most common analytical mistake in this category — it leads to reactive strategy changes (rewriting content, disavowing links) in response to what was actually a broken tag. Work top-down and don't skip steps even when a platform-side explanation seems obvious.

## Setting Up Ongoing Monitoring

For proactive rather than reactive anomaly detection: define a baseline range per key metric (sessions, conversions, key event count) using recent historical data, segmented by channel and device, and flag any day or week that falls meaningfully outside that range for review — rather than relying on someone noticing a dashboard looks "off." Re-baseline periodically so genuine growth or seasonal shifts don't get flagged as false anomalies indefinitely.

## Workflow

1. **Confirm the anomaly is real** — check the data stream status and recent site/tag changes first (Step 1 above).
2. **Segment the drop or spike** by channel, device, landing page, and geography to localize it.
3. **Check for a comparable prior period** to rule out normal seasonality.
4. **Rule out external/infrastructure causes** before considering platform-side explanations.
5. **Only after 1–4 are exhausted**, investigate algorithm updates or competitive shifts, cross-referencing the date of the anomaly against known update rollout windows.
6. **Document the finding and the fix** (or confirm it was a real, unexplained platform-side shift) so the same anomaly isn't re-investigated from scratch next time.

## Related Skills

- **ga4-audit**: Standing configuration checklist; anomalies are often this skill's symptom of a ga4-audit-level issue
- **rank-tracking-summary**: Ranking-specific drop investigation, a common companion when organic traffic is the affected channel
- **client-report-writer**: Where an anomaly finding typically gets communicated once diagnosed
