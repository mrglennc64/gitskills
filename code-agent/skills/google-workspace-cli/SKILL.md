# Google Workspace CLI Documentation

This page documents the `gws` CLI—an open-source tool (Apache-2.0 licensed) for administering Google Workspace services including Gmail, Drive, Sheets, Calendar, Docs, Chat, and Tasks.

## Key Features

The CLI dynamically generates commands from Google's Discovery Service, covering all supported Workspace APIs plus custom helper commands prefixed with `+`. It includes local Python utilities for diagnostics, authentication setup, recipe templates, security audits, and output analysis.

## Installation Options

Four installation methods are supported:
- **npm** (recommended, requires Node.js 18+)
- **Homebrew** (macOS/Linux)
- **Cargo** (from source)
- **Pre-built binaries** (macOS, Linux, Windows)

## Core Workflows

**Gmail Automation** enables sending, searching, labeling, and filtering emails using both helper commands and discovery-based API calls.

**Drive & Sheets** covers file operations, sharing configuration, and data manipulation through upload, creation, and export functions.

**Calendar & Meetings** manages event scheduling, availability queries, and generates standup reports.

**Security Audit** scans configuration across services, checking for risks like external sharing, auto-forwarding, and insufficient admin verification enforcement.

## Best Practices

The documentation emphasizes: requesting minimal OAuth scopes, storing tokens securely, using `--dry-run` before destructive operations, piping JSON output through the analyzer tool, and preferring helper commands over chained raw API calls for multi-step operations.