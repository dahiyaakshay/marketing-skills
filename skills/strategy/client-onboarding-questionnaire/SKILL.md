---
name: client-onboarding-questionnaire
description: When the user wants to build an onboarding questionnaire for a new marketing client or project. Also use when the user mentions "client onboarding questionnaire," "new client intake form," or "what should I ask a new client." Feeds directly into project-context.md and client-report-writer (content category).
metadata:
  version: 1.0.0
---

# Strategy: Client Onboarding Questionnaire

Builds the intake questionnaire that establishes what a new client actually values before any strategy or reporting work begins the questions asked here directly shape what **client-report-writer** (content category) should emphasize later, so gaps here become gaps in every subsequent report.

**When invoking**: On first use, briefly note that this feeds forward into reporting emphasis. On subsequent use, go straight to building the questionnaire.

## Scope

Onboarding question design. The output should populate a project-context reference (see the repository's `templates/project-context.md`) and directly inform **client-report-writer**'s later emphasis.

## Core Question Categories

| Category | Sample questions | Why it matters |
|---|---|---|
| **Business context** | What does the business do, who's the ideal customer, what's the sales cycle length | Shapes content, targeting, and attribution-window decisions across nearly every other skill in this library |
| **Success definition** | What specific metric(s) define success for this engagement leads, revenue, rankings for specific terms, traffic | Prevents a later mismatch where the agency reports on vanity metrics the client never cared about (see **client-report-writer**) |
| **Prior history** | Past agencies/efforts, known technical issues, any past penalties or migrations | Avoids repeating past mistakes and surfaces context a fresh technical audit might miss |
| **Competitors** | Who they consider their real competitors (not always who ranks alongside them) | Client-perceived competitors and algorithmically-identified competitors sometimes diverge meaningfully |
| **Brand/style preferences** | Tone, banned phrases, regional spelling, approval process | Feeds directly into **editorial-style-guide** (content category) |
| **Reporting preferences** | Cadence, format, who the audience for reports actually is | Feeds directly into **client-report-writer** and **kpi-dashboard-builder** (analytics category) |

## Workflow

1. Draft the questionnaire covering all core categories above, tailored to the specific engagement type (SEO retainer, one-off project, ongoing paid media management).
2. Send before or at the very start of the engagement, not after initial strategy work has already begun.
3. Populate the responses into a project-context reference document.
4. Flag any unanswered or vague responses (e.g. no clear success metric given) as a risk to resolve before proceeding, rather than assuming a default.
5. Revisit and update the questionnaire responses periodically, since a client's priorities and competitive context can shift over the life of a longer engagement.

## Related Skills

- **client-report-writer** (content): Directly shaped by the success-definition and reporting-preference answers gathered here
- **editorial-style-guide** (content): Populated by the brand/style answers
- **seo-proposal-writer**: Often precedes this questionnaire in the client acquisition sequence
