# ADR-010 - Transport-Agnostic Runtime Core

## Status

Accepted for MVP.

## Context

REST + WebSocket is MVP transport, but future versions may expose gRPC, named pipes, Unix sockets, or other transports.

## Decision

Go local service core logic remains separate from HTTP/WebSocket transport code.

## Consequences

### Positive

- Core local service capabilities are defined behind interfaces.
- HTTP/WebSocket handlers call internal service interfaces.
- Provider logic does not depend on transport details.
- Architecture remains extensible.

### Negative / Trade-offs

- The service needs internal interfaces before multiple transports exist.
- Over-abstraction should be avoided in early MVP code.
- Tests should cover service logic separately from transport handlers.

## Notes

Keep the first implementation pragmatic: extract clear service boundaries around providers, runs, approvals, workspaces, and sync.
