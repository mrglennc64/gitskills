# Schema Markup Implementation Guide

This document outlines a comprehensive system for implementing, auditing, and validating structured data (schema.org markup) to earn rich results in Google and improve AI search visibility.

## Core Framework

The skill activates when users mention schema.org, JSON-LD, rich snippets, structured data errors, or AI search visibility challenges. It operates in three primary modes:

1. **Audit existing markup** — extract current schema, identify errors, score completeness
2. **Implement new schema** — generate copy-paste-ready JSON-LD for specific page types
3. **Validate & fix** — correct broken schema using Google's validators

## Schema Selection

Different page types require different schema types:

- **Blog posts/articles:** Article + BreadcrumbList + Person (author)
- **FAQ pages:** FAQPage
- **Product pages:** Product + Offer + AggregateRating
- **Local businesses:** LocalBusiness + OpeningHoursSpecification
- **How-to guides:** HowTo + Article + BreadcrumbList
- **Homepages:** Organization + WebSite (with SearchAction)

"Always add `BreadcrumbList` to any non-homepage if breadcrumbs exist on the page."

## Critical Implementation Rules

**Use JSON-LD exclusively** — it's Google-recommended and easiest to maintain. Place schema blocks in `<head>` tags using separate `<script type="application/ld+json">` tags.

**Common failure points:**
- Missing `@context: "https://schema.org"`
- Empty or generic `name` fields
- Relative image URLs (must be absolute HTTPS)
- Markup that doesn't match visible page content
- Incorrect date formatting (use ISO 8601)

## AI Search & Testing

Schema markup increasingly matters for AI search systems (Google AI Overviews, Perplexity, ChatGPT Search). Structured data helps these systems identify content type and assess authority faster.

**Always validate using:**
- Google Rich Results Test
- Schema.org Validator
- Google Search Console (post-deployment)

---

*MIT Licensed | v1.0.0 | Last updated: 2026-03-06*