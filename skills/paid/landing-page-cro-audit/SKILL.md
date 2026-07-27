---
name: landing-page-cro-audit
description: When the user wants a structural conversion-rate-optimization audit of an existing landing page. Also use when the user mentions "CRO audit," "landing page conversion audit," or "why isn't this page converting." For writing new landing page copy, use landing-page-copywriter (content category). For testing a specific hypothesis this audit generates, use ab-test-planner.
metadata:
  version: 1.0.0
---

# Paid: Landing Page CRO Audit

Audits an existing, live landing page's structure for conversion friction — distinct from writing new copy (see **landing-page-copywriter**, content category), this skill evaluates what's already there against CRO best practice and flags specific structural issues.

**When invoking**: On first use, briefly note the audit-vs-rewrite distinction below. On subsequent use, go straight to the audit.

## Scope

Structural CRO evaluation of a live page. For drafting new copy, see **landing-page-copywriter** (content category). For testing a specific fix hypothesis this audit generates, see **ab-test-planner**.

## Audit Checklist

| Area | What to check |
|---|---|
| **Single conversion goal clarity** | Is there one clear primary action, or does the page have competing CTAs/navigation diluting focus? |
| **Above-the-fold clarity** | Can a visitor understand what's being offered and what to do within the first few seconds, without scrolling? |
| **Page load speed** | Slow load times directly suppress conversion — cross-check **core-web-vitals-audit** (technical category), since even a one-second load delay has been associated with meaningfully reduced conversion in industry studies |
| **Form friction** | Number of fields, unnecessary required fields, and whether the form appears intimidating relative to the value being offered |
| **Trust signals** | Presence and placement of social proof, security badges, or credibility markers near the conversion point, not just elsewhere on the page |
| **Mobile experience** | Whether the conversion path (form, CTA button size/placement) works cleanly on mobile specifically, not just desktop |

## Workflow

1. Review the page against each checklist area, noting specific issues rather than generic impressions.
2. Cross-check page speed via **core-web-vitals-audit** if load time seems to be a factor.
3. Prioritize findings by likely impact — above-the-fold clarity and form friction tend to have outsized effects relative to smaller cosmetic issues.
4. For any finding where the right fix isn't obvious, frame it as a testable hypothesis and hand off to **ab-test-planner** rather than guessing at the fix.
5. For findings requiring a copy rewrite, hand off to **landing-page-copywriter**.

## Related Skills

- **landing-page-copywriter** (content): New copy drafting once this audit identifies what needs to change
- **ab-test-planner**: Structured testing for audit findings without an obvious fix
- **core-web-vitals-audit** (technical): Page speed cross-check
