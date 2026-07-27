---
name: ad-fatigue-detector
description: When the user wants to detect whether ad performance is declining due to audience fatigue (overexposure to the same creative). Also use when the user mentions "ad fatigue," "frequency capping," or "why is CTR dropping on this ad." For building fresh audiences to rotate in, use remarketing-audience-builder.
metadata:
  version: 1.0.0
---

# Paid: Ad Fatigue Detector

Distinguishes genuine ad fatigue (audience overexposure to the same creative, causing declining engagement) from other causes of declining ad performance — the fix differs substantially depending on which is actually happening.

**When invoking**: On first use, briefly note the diagnostic distinction below. On subsequent use, go straight to the diagnosis.

## Scope

Diagnosing ad fatigue specifically. For refreshing the audience pool once fatigue is confirmed, see **remarketing-audience-builder**.

## Signals of Genuine Ad Fatigue

| Signal | What it indicates |
|---|---|
| **CTR declining over time on the same creative, same audience, stable everything else** | The classic fatigue pattern — the same people seeing the same ad repeatedly, with engagement wearing off |
| **Frequency metric climbing alongside declining CTR** | A rising frequency (average number of times a single user has seen the ad) correlating with declining CTR is the clearest confirming signal |
| **Performance recovers on the same audience when a new creative is introduced** | The strongest confirmation — if a fresh creative to the identical audience immediately performs better, fatigue (not audience quality) was the cause |

## What Looks Like Fatigue But Isn't

- **Seasonal or day-of-week effects**: a broader decline across all creatives and audiences simultaneously points to external factors, not creative-specific fatigue.
- **Audience saturation** (distinct from fatigue): if the addressable audience pool itself has been exhausted (everyone who could plausibly convert already has), a new creative won't fix a fundamentally too-small audience — this needs **remarketing-audience-builder** or broader audience expansion, not just fresh ad copy.
- **A genuine relevance/targeting problem**: if CTR was never strong even on the initial creative, the problem may be targeting or ad relevance (see **quality-score-optimizer**), not fatigue from overexposure.

## Workflow

1. Pull frequency and CTR trend data for the specific ad/audience combination in question.
2. Check whether CTR decline correlates with rising frequency specifically, isolated to this creative/audience pairing.
3. Rule out broader, simultaneous declines across all creatives (seasonal/external factors) and check whether the underlying audience pool itself may be exhausted.
4. If fatigue is confirmed, refresh the creative and/or rotate in a refreshed audience (see **remarketing-audience-builder**).
5. Confirm recovery by monitoring the same audience's response to the new creative.

## Related Skills

- **remarketing-audience-builder**: Refreshing the audience pool once fatigue (or audience exhaustion) is confirmed
- **quality-score-optimizer**: Relevant if the underlying issue is ad relevance rather than fatigue
