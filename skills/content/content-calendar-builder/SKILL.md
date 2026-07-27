---
name: content-calendar-builder
description: When the user wants to schedule and sequence content publication over time. Also use when the user mentions "content calendar," "editorial calendar," or "what should we publish and when." For deciding what topics belong in the calendar in the first place, use content-gap-analysis or topic-cluster-mapping.
metadata:
  version: 1.0.0
---

# Content: Content Calendar Builder

Sequences already-identified content priorities into a publication schedule, weighing pillar/cluster dependencies, seasonality, and resourcing rather than just listing topics in an arbitrary order.

**When invoking**: On first use, briefly note the sequencing principle below. On subsequent use, go straight to building the calendar.

## Scope

Scheduling and sequencing. Not identifying what the content priorities should be in the first place (see **content-gap-analysis**, **topic-cluster-mapping**).

## Sequencing Principles

| Principle | Why |
|---|---|
| **Pillar before spokes** | A cluster's spoke pages get more value linking to a pillar that already exists than the reverse publish the pillar first or alongside the first batch of spokes |
| **Batch by subtheme** | Publishing several related spoke pages together (e.g. all "setup" pages, then all "comparison" pages) creates a stronger topical signal in a shorter window than trickling out one unrelated piece at a time |
| **Seasonality-aware** | Time-sensitive content (see **evergreen-content-identifier**) needs to publish ahead of its relevant window, with enough runway for indexing |
| **Resourcing-realistic** | A calendar that assumes unlimited writer/designer bandwidth gets abandoned; sequence around actual capacity |

## Workflow

1. Pull prioritized topics from **content-gap-analysis** and the cluster architecture from **topic-cluster-mapping**.
2. Sequence pillar pages ahead of or alongside their first spoke batch.
3. Group remaining spokes into subtheme batches rather than scheduling them independently.
4. Slot in time-sensitive content with adequate lead time before its relevant window.
5. Check the sequence against actual writing/design/review capacity before finalizing dates.
6. Review and adjust monthly as new gaps or competitive shifts emerge (see **competitor-content-audit**).

## Related Skills

- **content-gap-analysis**, **topic-cluster-mapping**: Supply the prioritized topic list this skill sequences
- **evergreen-content-identifier**: Informs which content needs seasonal timing vs. can be scheduled flexibly
- **competitor-content-audit**: Ongoing input that can reprioritize the calendar
