---
name: structured-data-validator
description: When the user wants to validate or troubleshoot structured data (schema.org markup) on a page. Also use when the user mentions "structured data errors," "schema validation," or "rich results not showing." For selecting which schema type to use for a given content type, use schema-markup-generator (on-page category).
metadata:
  version: 1.0.0
---

# Technical: Structured Data Validator

Validates implemented schema.org markup for syntax errors, missing required properties, and mismatches against visible page content the technical QA layer beneath schema selection and strategy.

**When invoking**: On first use, briefly note the consistency requirement below. On subsequent use, go straight to validation.

## Scope

Validating already-implemented markup. For choosing which schema type fits a given content type, see **schema-markup-generator** (on-page category); for local-business-specific schema, see **local-schema-markup** (local category).

## Common Validation Failures

| Failure | Why it happens |
|---|---|
| **Missing required properties** | Each schema type has properties Google treats as required for rich-result eligibility (e.g. Recipe schema needs image, and typically ingredients/instructions) omitting them can disqualify the page from the intended rich result entirely |
| **Mismatched content** | Schema declaring a price, rating, or date that doesn't match what's visibly on the page this is treated as a spam/manipulation signal, not just a technical error, and can lead to manual actions in serious cases |
| **Invalid syntax** | Malformed JSON-LD (trailing commas, unescaped characters) that breaks parsing entirely, silently nullifying the whole block rather than just the broken field |
| **Wrong schema type for the content** | Using a more specific or more generic type than what the content actually is, missing the more accurate match |
| **Duplicate/conflicting schema blocks** | Multiple schema blocks for the same entity on one page providing contradictory information |

## Workflow

1. Extract all structured data blocks present on the target page(s).
2. Run each through a schema validation tool, checking for syntax errors first (a syntax error can invalidate the entire block).
3. Confirm all required and recommended properties for the declared type are present.
4. Cross-check every schema value against the visible page content price, rating, date, author flagging any mismatch as high priority.
5. Confirm only one schema block exists per entity per page, or that multiple blocks are consistent with each other.
6. Re-validate after any content update that would change a schema-declared value (price change, updated rating), since this is a common source of drift.

## Related Skills

- **schema-markup-generator** (on-page): Schema type selection and initial implementation
- **local-schema-markup** (local): Local-business-specific schema validation
- **answer-engine-schema** (geo): AI-citation-specific schema priorities
