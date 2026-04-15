# Error Handling Strategy

## Purpose

Database and schema tooling must fail safely and preserve reviewability.

## Core Rules

- schema inconsistencies and migration risks must be surfaced explicitly
- catch errors locally only when the tooling can add useful context or perform safe rollback
- propagate errors when human review or operator action is required
- never suppress migration or schema validation failures silently

## Preferred Behavior

- classify failures as validation, migration, compatibility, or tooling failures
- include model id, migration id, or query id in error context
- support cancellation or timeout controls for long-running tooling when applicable

## Recovery Expectations

- automated rollback should only happen when the recovery path is explicit and documented
- otherwise fail fast, record diagnostics, and require human review
