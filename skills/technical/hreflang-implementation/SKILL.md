---
name: hreflang-implementation
description: When the user wants to implement or fix hreflang tags for a multi-language or multi-region site. Also use when the user mentions "hreflang," "international SEO," or "wrong country version showing in search." For the broader technical audit this fits into, use technical-seo-audit.
metadata:
  version: 1.0.0
---

# Technical: Hreflang Implementation

Implements hreflang annotations so search engines serve the correct language/region version of a page to each searcher one of the most error-prone technical SEO implementations because it requires every page in a set to reference every other page consistently.

**When invoking**: On first use, briefly note the reciprocity requirement below. On subsequent use, go straight to implementation.

## Scope

Multi-language/multi-region page targeting. This is one layer of the broader **technical-seo-audit** and is only relevant for sites genuinely serving multiple language or regional versions of the same content.

## Core Requirement: Reciprocity

Every page in a hreflang set must reference every other page in the set, including itself if Page A references Page B but Page B doesn't reference Page A back, search engines will typically disregard the annotation entirely for that pair. This reciprocal, self-inclusive structure is the single most common source of hreflang errors, especially as pages are added or removed from a set over time without updating every other page's tag set.

## Implementation Format

```
<link rel="alternate" hreflang="en-us" href="https://example.com/us/" />
<link rel="alternate" hreflang="en-gb" href="https://example.com/uk/" />
<link rel="alternate" hreflang="fr-fr" href="https://example.com/fr/" />
<link rel="alternate" hreflang="x-default" href="https://example.com/" />
```

| Element | Guidance |
|---|---|
| **Language code** | ISO 639-1, always lowercase |
| **Region code (optional)** | ISO 3166-1 Alpha 2, always uppercase, only include if content genuinely differs by region within the same language |
| **x-default** | The fallback version for users whose language/region doesn't match any specific tag commonly the international or primary-language homepage |
| **Self-reference** | Every page includes a hreflang tag pointing to itself, not just to the other versions |

## Common Mistakes

- **Non-reciprocal tags**: the most frequent error, silently invalidating the whole annotation set for the affected pages.
- **Wrong region/language code casing or format**: language lowercase, region uppercase mixing these up causes the tag to be ignored.
- **Combining hreflang with a mismatched canonical tag**: if a page's canonical tag points to a different language version than what the hreflang set implies, this creates a conflicting signal.
- **Missing x-default**: leaves ambiguity for users who don't match any specific declared version.

## Workflow

1. Map every language/region version of each piece of content.
2. Confirm each version's URL and correct language/region code.
3. Implement the full reciprocal tag set on every page in the group, including self-reference.
4. Add x-default for the appropriate fallback version.
5. Confirm canonical tags don't conflict with the hreflang structure.
6. Validate with a hreflang testing tool, and re-validate whenever a new language/region version is added or removed from the set.

## Related Skills

- **canonical-tag-strategy**: Must be checked for consistency alongside hreflang
- **technical-seo-audit**: Broader audit this fits into
