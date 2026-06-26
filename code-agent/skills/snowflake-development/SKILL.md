# Snowflake Development Skill Overview

This comprehensive skill guide covers Snowflake SQL, data pipelines, Cortex AI, and Snowpark Python development. Here are the key takeaways:

## Core Principles

The guide emphasizes that developers should "Use `snake_case` for all identifiers" and avoid double-quoted names that require constant quoting in queries.

A critical runtime consideration: "In SQL stored procedures (BEGIN...END blocks), variables and parameters **must** use the colon `:` prefix inside SQL statements."

## Pipeline Strategies

Three main approaches are recommended:
- **Dynamic Tables** for declarative transformations (the default choice)
- **Streams + Tasks** for imperative CDC with procedural logic
- **Snowpipe** for continuous cloud storage ingestion

The documentation stresses that Dynamic Tables should use explicit column lists rather than `SELECT *` to prevent schema-change failures.

## AI Integration

Cortex AI provides functions like `AI_CLASSIFY`, `AI_EXTRACT`, `AI_SENTIMENT`, and `AI_PARSE_DOCUMENT`. Importantly, older function names (`CLASSIFY_TEXT`, `SUMMARIZE`) are deprecated and should not be used in new code.

## Key Anti-Patterns to Avoid

- Hardcoding credentials in Snowpark applications
- Using `collect()` on large DataFrames (process server-side instead)
- Running tasks without the `WHEN SYSTEM$STREAM_HAS_DATA` clause
- Nested subqueries rather than CTEs for readability

The skill provides practical workflows, troubleshooting guides, and explicit code templates for common tasks like MERGE upserts and Dynamic Table creation.