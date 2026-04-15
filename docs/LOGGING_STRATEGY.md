# Logging Strategy

## Purpose

This repo owns schema governance, migration metadata, and query governance. Any tooling here must produce logs that help humans understand schema-change behavior and risk.

## Core Rules

- use dependency-injected or service-provided loggers where executable tooling or services exist
- use structured logging for migration ids, model names, query ids, and review artifacts
- never log secrets, credentials, or unrestricted data payloads
- log enough detail to explain schema review and migration behavior without leaking sensitive data

## Recommended Log Levels

- `debug` for migration planning, diff generation, and catalog lookups
- `information` for major lifecycle steps such as migration start, completion, and validation
- `warning` for compatibility risks, slow paths, or fallback behavior
- `error` for failed migration operations, invalid schema states, or broken query catalog checks

## Special Considerations

- identify affected model or query ids in logs
- include blast-radius and cost-review references when relevant
- avoid dumping full SQL unless explicitly needed in a controlled diagnostic path
