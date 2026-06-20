# ADR-007 - Database as Source of Truth

## Status

Accepted for MVP.

## Context

File-based/Markdown workflows are useful as templates/docs, but a full AI Project Manager needs structured, queryable, collaborative persistent state.

## Decision

Cloud database is the source of truth for long-lived project state.

## Consequences

### Positive

- Projects, tasks, runs, approvals, diagrams, and design metadata live in DB.
- Cloud backend owns canonical project state.
- Structured state can support querying, permissions, sync, and collaboration.
- Markdown can exist as exports, templates, or generated docs.

### Negative / Trade-offs

- Data modeling must happen early.
- Migration/versioning strategy is required.
- Documentation exports must not drift from canonical DB state without clear sync rules.

## Notes

Versioning/history should be supported for important entities.
