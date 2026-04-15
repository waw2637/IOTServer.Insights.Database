# Coding Practices

This repo is the first-class database authority for the initiative. Changes here must optimize for correctness, traceability, and operational safety.

## Required Standards

- Adhere to SOLID principles where practical
- Keep persistence responsibilities explicit
- Document intent, caveats, limitations, inputs, and outputs where comments add value
- Accept cancellation or timeout controls where applicable in tooling and automation
- Use non-blocking patterns when appropriate
- Bound loops with cancellation, timeout, or safe recovery behavior
- Catch errors locally when recovery is reasonable and document non-obvious handling
- Propagate errors when local recovery is not appropriate
- Use dependency-injected or service-provided loggers rather than ad hoc static logging where executable tooling or services exist
- Log at useful levels in any executable tooling

## Special Emphasis for This Repo

- never duplicate approved DB models without explicit migration rationale
- always reference the approved model registry before proposing schema changes
- document query purpose, ownership, and cost implications
- include blast-radius reasoning for non-trivial schema and query changes
- ensure migrations, queries, and schema docs stay aligned
