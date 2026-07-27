---
name: seo-audit-to-roadmap
description: When the user wants to turn a completed technical/content/GEO audit into a prioritized action roadmap. Also use when the user mentions "audit to roadmap," "prioritize these SEO findings," or "turn this audit into a plan." Sits downstream of technical-seo-audit, content-gap-analysis, and llm-retrievability-audit.
metadata:
  version: 1.0.0
---

# Strategy: SEO Audit to Roadmap

Converts a completed audit's raw findings into a prioritized, sequenced action roadmap an audit alone is a list of problems; a roadmap is a plan for which problems to fix first and why.

**When invoking**: On first use, briefly explain the prioritization framework below. On subsequent use, go straight to building the roadmap.

## Scope

Prioritization and sequencing of already-identified findings. Assumes an underlying audit (**technical-seo-audit**, **content-gap-analysis**, **llm-retrievability-audit**, or a combination) has already produced the raw findings list this skill organizes.

## Prioritization Framework

| Factor | What to weigh |
|---|---|
| **Blocking severity** | Does this finding block everything downstream (e.g. a crawler access issue) or is it a standalone improvement? Blocking issues go first regardless of apparent "size" |
| **Effort required** | Quick technical fixes (a robots.txt correction) vs. sustained content investment (a multi-month content gap program) |
| **Expected impact** | Estimated traffic/conversion/citation value at stake, even if only directional |
| **Dependency order** | Some fixes must precede others (e.g. fixing crawl access before a content restructuring effort can be properly evaluated) |

A simple, useful sequencing heuristic: fix blocking technical issues first (regardless of effort), then high-impact/low-effort items, then high-impact/high-effort items, with low-impact items last regardless of effort.

## Roadmap Structure

| Section | Content |
|---|---|
| **Immediate (this week)** | Blocking technical fixes, quick wins |
| **Short-term (this month)** | High-impact, moderate-effort items |
| **Medium-term (this quarter)** | Larger content or structural investments |
| **Ongoing** | Standing practices (content refresh cadence, backlink monitoring) rather than one-time fixes |

## Workflow

1. Compile the full findings list from the underlying audit(s).
2. Classify each finding by blocking severity, effort, expected impact, and dependency.
3. Sequence findings into the immediate/short-term/medium-term/ongoing structure.
4. Flag any findings with unclear impact as candidates for a smaller test before large investment, rather than guessing.
5. Present the roadmap with clear owners and rough timelines where applicable, not just a prioritized list.

## Related Skills

- **technical-seo-audit**, **content-gap-analysis**, **llm-retrievability-audit**: Common upstream sources of the findings this skill sequences
- **content-calendar-builder** (content): Where content-specific roadmap items get scheduled in detail
- **client-report-writer** (content): Where roadmap progress gets communicated to a client
