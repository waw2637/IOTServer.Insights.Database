# IOTServer.Insights.Database

First-class database and schema governance repo for the insights platform.

## Purpose

This repo is the authoritative home for:

- approved database models
- schema definitions
- migrations
- query catalog entries
- cost and blast-radius analysis for schema and query changes

The database is a first-class platform component, not just an implementation detail hidden behind services.

## Why This Repo Exists

- Prevent duplicate schema modeling across repos
- Give AI and humans one approved source of truth for DB models
- Track query purpose, ownership, and cost
- Make schema changes reviewable from performance and blast-radius perspectives
- Reduce accidental query breakage during schema evolution

## Core Rules

- AI must reference the approved model registry before proposing schema changes
- New schema work must extend or revise approved models, not recreate them from memory
- Important queries must be documented with purpose, ownership, and cost reasoning
- Non-trivial schema changes must include blast-radius analysis
- Human approval is required for schema and important query changes

## Layout

- `schema/` - canonical schema artifacts and approved structural definitions
- `migrations/` - migration files and migration metadata
- `query-catalog/` - important query definitions and ownership metadata
- `docs/models/` - approved logical and physical model docs
- `docs/migrations/` - migration decision records
- `docs/queries/` - query purpose and reasoning docs
- `docs/cost/` - cost, performance, and blast-radius analyses

## Key Documents

- `docs/DB_REPO_ARCHITECTURE.md` - role of this repo in the wider platform
- `docs/MODEL_REGISTRY_SPEC.md` - approved model registry rules
- `docs/QUERY_CATALOG_SPEC.md` - query documentation and drift-control rules
- `docs/SCHEMA_CHANGE_REVIEW_CHECKLIST.md` - required schema review checklist
- `CODING_PRACTICES.md` - repo-local coding and operational quality requirements
- `docs/LOGGING_STRATEGY.md` - repo logging expectations
- `docs/DATA_ACCESS_STRATEGY.md` - repo data-access boundaries and patterns
- `docs/ERROR_HANDLING_STRATEGY.md` - repo error-handling and recovery expectations

## Notes

This repo should be treated as the canonical persistence reference for the initiative. Other repos should reference this one rather than redefining DB structures ad hoc.
