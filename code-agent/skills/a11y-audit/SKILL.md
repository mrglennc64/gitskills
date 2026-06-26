# Accessibility Audit Skill Overview

The **a11y-audit** skill provides a comprehensive accessibility scanning and remediation pipeline for modern web applications, supporting React, Next.js, Vue, Angular, Svelte, and plain HTML codebases.

## Core Capabilities

The skill implements a three-phase workflow:

1. **Scan** - Detects WCAG 2.2 Level A and AA violations across your codebase, categorized by severity
2. **Fix** - Generates framework-specific before/after code patterns for each issue
3. **Verify** - Re-scans to confirm fixes and check for regressions

## Key Features

- Full WCAG 2.2 compliance checking with automatic framework detection
- Severity classification: Critical (blocks access), Major (significant barrier), Minor (friction)
- Color contrast validation against AA and AAA standards
- Keyboard navigation and ARIA attribute auditing
- Stakeholder-ready compliance reporting
- CI/CD pipeline integration support

## Common Issues Addressed

The skill prevents frequent accessibility pitfalls such as:

- Missing alt text on images
- Non-keyboard-accessible interactive elements
- Insufficient color contrast ratios
- Improper ARIA attribute usage
- Missing form labels and focus indicators
- Heading hierarchy violations

## Tools Provided

**a11y_scanner.py** - Main scanning tool with JSON/CSV/table output, framework detection, and baseline comparison capabilities.

**contrast_checker.py** - Dedicated color contrast validation with suggestions for accessible alternatives.

Both tools support CI/CD integration with configurable exit codes and formatted output for automation workflows.