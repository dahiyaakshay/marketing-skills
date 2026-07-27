---
name: changelog-writer
description: When the user wants to write or format a product changelog entry. Also use when the user mentions "changelog," "release notes," or "what's new page." For broader content structure principles, this is a narrow, format-driven skill.
metadata:
  version: 1.0.0
---

# Content: Changelog Writer

Formats product update entries in a consistent, scannable structure a changelog's value comes almost entirely from consistency and scanability across entries, not from any single entry's writing quality.

**When invoking**: On first use, confirm the existing changelog format if one exists, to stay consistent. On subsequent use, go straight to drafting the new entry.

## Scope

Individual changelog/release-note entries. This is a narrow, format-specific skill rather than a broader content strategy one.

## Structural Elements

| Element | Guidance |
|---|---|
| **Date/version** | Clearly labeled at the top of each entry |
| **Category tags** | New, Improved, Fixed categorize each change so readers can scan for what matters to them |
| **One line per change** | Plain-language description of what changed and why it matters to the user, not internal technical framing |
| **Visual/screenshot** | Included for significant UI changes, since a changelog entry describing a visual change is far less useful without showing it |
| **Consistent tense/voice** | Past tense, active voice, applied consistently across every entry ("Added X" not "X has been added") |

## User-Facing, Not Internal Framing

Write each entry from the user's perspective what changed for them and why it matters rather than from an internal engineering perspective (commit messages, ticket numbers, internal system names). "Fixed an issue where reports could show incorrect totals" reads better to a user than "Fixed race condition in report aggregation service."

## Workflow

1. Confirm or establish the standard entry format (date/version, category tags, tense).
2. Draft each change as a single user-facing line, categorized appropriately.
3. Add screenshots for significant visual/UI changes.
4. Maintain consistent tense and voice across all entries, checking against the existing changelog if one exists.

## Related Skills

- **editorial-style-guide**: House style/tense conventions this entry format should follow
