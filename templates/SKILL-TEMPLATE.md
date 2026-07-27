---
name: skill-name-in-kebab-case
description: When the user wants to [core trigger scenario in plain language]. Also use when the user mentions "[trigger phrase 1]," "[trigger phrase 2]," "[trigger phrase 3]," or "[trigger phrase 4]." For [adjacent scenario A], use [sibling-skill-a]. For [adjacent scenario B], use [sibling-skill-b]. For [broader strategy this skill feeds into], use [parent-skill].
metadata:
  version: 1.0.0
---

# [Category]: [Skill Title]

One or two sentences: what this skill does, and why it matters / what mistake it prevents. If the skill overlaps with a sibling skill, name the boundary here (e.g. "this covers X; for Y, see sibling-skill").

**When invoking**: On first use, [what to do before the main output — e.g. briefly explain a key distinction]. On subsequent use, or when the user asks to skip, go directly to the main output.

## Scope

What this skill covers and, just as importantly, what it explicitly does NOT cover (with pointers to the correct skill for those adjacent cases).

## [Core Concept / Distinction Section]

The single most important framework, distinction, or piece of background knowledge someone needs before they can use this skill correctly. This is often a table.

| Dimension | Option A | Option B |
|---|---|---|
| ... | ... | ... |

## [Reference Table Section]

A concrete reference table of the entities, tools, platforms, or variables this skill deals with — the kind of lookup a practitioner would otherwise have to search for separately.

| Item | Detail 1 | Detail 2 | Recommended posture/action |
|---|---|---|---|
| ... | ... | ... | ... |

## Decision Framework

The questions someone should ask themselves to choose between approaches, followed by a table mapping answers to recommended actions.

| Situation | When to use | What to do |
|---|---|---|
| ... | ... | ... |

## Workflow

Numbered, concrete steps for actually executing the skill — written so an agent could follow them mechanically:

1. Step one — what to gather or check first.
2. Step two — the core analysis or transformation.
3. Step three — how to flag edge cases or risks.
4. Step four — output format.
5. Step five — any calibration/verification loop (compare output against real outcomes and adjust).

## What This Skill Does Not Cover

Explicit callouts of adjacent problems this skill deliberately leaves to other skills, so the boundaries stay clean as the library grows.

## Related Skills

- **sibling-skill-a**: one-line description of the relationship
- **sibling-skill-b**: one-line description of the relationship
- **parent-skill**: the broader strategy this skill's output feeds into
