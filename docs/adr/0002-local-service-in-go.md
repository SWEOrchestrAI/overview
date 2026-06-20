# ADR-002 - Local Service in Go

## Status

Accepted for MVP.

## Context

The local service behaves like a local daemon/orchestrator. It needs process execution, streaming logs, long-running runs, local API support, concurrency, and simple packaging.

## Decision

Use Go for the local service.

## Consequences

### Positive

- Electron remains focused on UI.
- Go owns local orchestration and execution.
- Go provides strong support for concurrency, process control, and long-running services.
- A compiled service is straightforward to package with a desktop application.

### Negative / Trade-offs

- Service APIs must be explicitly defined.
- Shared contracts should be generated or documented clearly.
- Frontend and service teams must coordinate TypeScript and Go models.

## Notes

The MVP should document REST and WebSocket contracts early to keep local front and local service work aligned.
