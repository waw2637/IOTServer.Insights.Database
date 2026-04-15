# Data Access Strategy

## Purpose

This repo is the authoritative persistence and schema-governance home for the initiative.

## Core Rules

- approved models, schema artifacts, migrations, and query catalogs are managed here
- schema and query tooling must reference the approved model registry first
- do not create parallel sources of truth in application repos

## Preferred Access Patterns

- treat `schema/`, `migrations/`, and `query-catalog/` as governed artifacts
- use explicit tooling boundaries for schema diffing, migration planning, and catalog validation
- isolate any live database access behind clear tooling or service interfaces

## Query Governance

- important queries must be documented with purpose, ownership, and cost reasoning
- schema changes must identify affected queries before approval

## Special Considerations

- production databases should not be changed by undocumented ad hoc scripts
- migration tooling should support dry-run and review-oriented workflows where practical
