---
name: mobile-first-indexing-check
description: When the user wants to confirm content parity and usability between mobile and desktop versions of a site. Also use when the user mentions "mobile-first indexing," "mobile usability," or "does my mobile site match desktop." For mobile-specific Core Web Vitals, use core-web-vitals-audit.
metadata:
  version: 1.0.0
---

# Technical: Mobile-First Indexing Check

Confirms that the mobile version of a site is what's actually being indexed and ranked — since Google's indexing is mobile-first, any content, structured data, or links present on desktop but missing on mobile are effectively invisible to the index.

**When invoking**: On first use, briefly explain the mobile-first implication below. On subsequent use, go straight to the check.

## Scope

Mobile/desktop content parity and mobile usability. For mobile-specific performance metrics, see **core-web-vitals-audit**, which should be run separately for the mobile device category since mobile typically underperforms desktop due to network and processing constraints.

## The Core Implication of Mobile-First Indexing

Google predominantly uses the mobile version of a page's content for indexing and ranking. This means anything present only on the desktop version — additional text, structured data, internal links, or images hidden or removed on mobile for space — is effectively invisible to Google's index, even though the desktop page looks complete. Content parity isn't optional polish; it's a direct indexing concern.

## Parity Checklist

| Element | What to verify |
|---|---|
| **Text content** | Full body content present on mobile, not truncated or hidden behind interactions that a crawler won't trigger |
| **Structured data** | Schema markup present and identical on both versions — a common oversight when mobile and desktop are built as genuinely separate templates rather than responsively from the same source |
| **Internal links** | Navigation and in-content links present on mobile, not stripped for a simplified mobile menu that loses important link paths |
| **Images and alt text** | Present with the same alt text on mobile, not swapped for a lower-resolution version without equivalent attributes |
| **Meta tags (title, description)** | Identical between versions — divergent meta tags between mobile/desktop create ambiguity about which is authoritative |

## Common Failure Pattern

The most common failure is a separate mobile subdomain (m.example.com) or older adaptive design pattern that was never fully kept in sync with desktop content updates — new content added to desktop over time doesn't automatically propagate, and the gap widens invisibly until a specific audit catches it. Responsive design (single URL, single HTML, CSS-driven layout changes) avoids this failure mode structurally, since there's only one version to update.

## Workflow

1. Confirm whether the site uses responsive design, dynamic serving, or separate mobile URLs — the audit approach differs by architecture.
2. For separate mobile URLs/dynamic serving, directly compare mobile and desktop versions of key templates for content, schema, links, and meta tag parity.
3. Check Search Console's mobile usability report for flagged issues (text too small, clickable elements too close together, content wider than screen).
4. Cross-check with **core-web-vitals-audit** using the mobile device segment specifically.
5. If a gap is found, prioritize fixing the mobile version to match desktop, not the reverse, since mobile is what's actually indexed.

## Related Skills

- **core-web-vitals-audit**: Mobile-specific performance metrics, complementary to this content-parity check
- **technical-seo-audit**: Broader audit this fits into
