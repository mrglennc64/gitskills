# Code → PRD: A Technical Overview

## Core Purpose

This skill transforms existing codebases into comprehensive Product Requirements Documents by analyzing architecture, routes, components, and APIs. It serves dual audiences: product managers seeking business context and engineers needing reconstruction details.

## Key Capabilities

The tool processes **frontend frameworks** (React, Vue, Next.js, Nuxt, Svelte), **backend systems** (NestJS, Django, Express, FastAPI), and **fullstack applications**. It distinguishes between genuine API integrations and mock data implementations—a critical detail for understanding system maturity.

## Workflow Structure

Analysis follows three sequential phases:

**Phase 1** establishes global context through project structure identification, route inventory creation, and shared component mapping. This prevents analyzing pages in isolation.

**Phase 2** examines each page individually across dimensions including layout regions, field specifications, interaction sequences, API dependencies, and cross-page relationships. Documentation captures "user action → system response" patterns exhaustively.

**Phase 3** generates organized output with per-page markdown files, enum dictionaries, and navigation mappings positioned for both stakeholder comprehension and technical reconstruction.

## Critical Distinctions

The documentation emphasizes "business language first"—avoiding implementation details unless they directly affect user experience. Simultaneously, it captures hidden logic: conditional field visibility, validation rules, default sort orders, and permission controls that code contains but stakeholders might miss.

Documentation must remain **self-contained and uncertain**—marking ambiguous business logic as `[TBC]` rather than fabricating meaning from abbreviated variable names.