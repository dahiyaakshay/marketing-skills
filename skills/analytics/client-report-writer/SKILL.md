---
name: client-report-writer
description: When the user wants to turn raw performance data into a client-facing narrative report. Also use when the user mentions "client report," "monthly report for a client," "how do I explain these numbers to my client," or "write the executive summary for this report." For designing the underlying dashboard/metrics this reports on, use kpi-dashboard-builder or seo-reporting-dashboard.
metadata:
  version: 1.0.0
---

# Analytics: Client Report Writer

Converts a dashboard's worth of numbers into a narrative a non-technical client stakeholder can act on the report's job is to answer "is this working and what happens next," not to display every available metric.

**When invoking**: On first use, briefly explain the narrative-over-data-dump principle below. On subsequent use, go straight to drafting the report.

## Scope

Covers the narrative writing layer for client communication. Does not cover metric selection or dashboard structure (see **kpi-dashboard-builder**, **seo-reporting-dashboard**) this skill assumes the underlying numbers are already chosen and reliable.

## Report Structure

| Section | Purpose | Length |
|---|---|---|
| **Executive summary** | The one-paragraph answer to "how did we do and what's next" written so a stakeholder who reads only this section still understands the state of the engagement | 3–5 sentences |
| **Wins** | Specific, attributable results tied to the work done this period | Bulleted, concrete, tied to numbers |
| **Challenges / what didn't work** | Honest account of what underperformed and why omitting this erodes trust faster than the bad news itself | Bulleted, non-defensive tone |
| **What's next** | The specific work planned for the coming period, ideally tied to addressing the challenges named above | Bulleted, action-oriented |
| **Data appendix** | Full metric detail for stakeholders who want to dig in | Tables, not prose |

## Principles

- **Lead with outcomes tied to the contract**, not vanity metrics. A client paying for lead generation doesn't need a paragraph about impression growth if leads didn't move.
- **Always contextualize a number** "organic traffic grew 12%" means little without knowing whether that's against a flat market, a declining one, or a target that was set higher.
- **Name what didn't work as directly as what did.** A report that only ever reports wins reads as unreliable over time, especially once a client compares it against their own analytics.
- **Tie "what's next" to "challenges."** A report that names a problem without a corresponding next step invites the question "so what are you doing about it."
- **Match tone to the relationship** a report for a technical in-house marketing lead can use more jargon and raw numbers than one for a non-marketing business owner.

## Workflow

1. **Pull the finalized dashboard data** (from **kpi-dashboard-builder** or **seo-reporting-dashboard**) don't re-derive numbers independently.
2. **Identify 2–4 genuine wins** tied to specific actions taken and specific contract-relevant outcomes.
3. **Identify 1–3 honest challenges**, each paired with a planned next step.
4. **Draft the executive summary last**, once wins/challenges/next-steps are settled, so it accurately compresses the full report rather than anchoring the narrative before the data is reviewed.
5. **Attach the full data appendix** separately so the narrative section stays readable and short.
6. **Match tone and jargon level** to the specific stakeholder receiving the report.

## Related Skills

- **kpi-dashboard-builder**, **seo-reporting-dashboard**: Source of the underlying metrics this skill narrates
- **rank-tracking-summary**: Ranking-specific input often summarized into the "wins/challenges" sections
- **client-onboarding-questionnaire**: Establishes what the client actually values reporting on, which should shape this report's emphasis
