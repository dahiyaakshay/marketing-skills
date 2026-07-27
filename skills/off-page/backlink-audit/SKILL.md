---
name: backlink-audit
description: When the user wants to audit a site's backlink profile for quality and toxic links. Also use when the user mentions "backlink audit," "toxic links," or "disavow file." For competitor comparison specifically, use competitor-backlink-gap. For proactive link building, use link-prospecting.
metadata:
  version: 1.0.0
---

# Off-Page: Backlink Audit

Audits a site's existing backlink profile to identify toxic or low-quality links and assess overall link health distinct from competitor comparison (see **competitor-backlink-gap**) or new link acquisition (see **link-prospecting**).

**When invoking**: On first use, briefly note that disavowing is a last resort, not a default action. On subsequent use, go straight to the audit.

## Scope

Existing backlink profile health. Not competitor comparison (see **competitor-backlink-gap**) or new link building (see **link-prospecting**, **guest-post-outreach**, **broken-link-building**, **digital-pr-pitch-writer**).

## Quality Signals to Assess

| Signal | What it indicates |
|---|---|
| **Linking domain relevance** | A link from a topically related, legitimate site carries more value than one from an unrelated or low-quality domain |
| **Linking domain authority/trust** | Established sites with their own legitimate traffic and reputation pass more meaningful signal |
| **Anchor text pattern** | A large share of exact-match commercial anchor text across many links is a common pattern in manipulative link schemes, not organic link building |
| **Link velocity** | A sudden, unnatural spike in new links (especially low-quality ones) can look like a manipulative campaign rather than organic growth |
| **Link placement context** | Links buried in footer link farms, unrelated comment sections, or clearly paid/sponsored placements without proper nofollow/sponsored attribution are red flags |

## When to Disavow (Last Resort)

Disavowing links should be reserved for clear cases of toxic, manipulative, or spam links that could plausibly trigger a manual action or algorithmic devaluation not simply low-authority but otherwise legitimate links. Over-aggressive disavowing of merely low-value (but not spammy) links can remove link equity unnecessarily. Google's own systems are generally capable of ignoring low-quality links without a disavow file in most cases; disavowing is appropriate mainly when there's a specific concern (negative SEO attack, past manipulative link building the site wants to clean up before a manual action review).

## Workflow

1. Pull the full backlink profile from a backlink data source.
2. Score linking domains for relevance, apparent legitimacy, and anchor text pattern.
3. Flag clearly toxic/spam links (link farms, clearly paid unattributed links, irrelevant foreign-language spam domains).
4. Distinguish "toxic, disavow-worthy" from "simply low-value but harmless" only the former needs action.
5. If disavowing, compile the file conservatively, erring toward keeping ambiguous links rather than removing them unnecessarily.
6. Re-audit periodically, especially after any unexpected ranking drop, to rule out a negative SEO link attack as a contributing factor.

## Related Skills

- **competitor-backlink-gap**: Comparative analysis, distinct from this skill's own-site health check
- **link-prospecting**, **guest-post-outreach**, **broken-link-building**, **digital-pr-pitch-writer**: New link acquisition, the counterpart to this audit
