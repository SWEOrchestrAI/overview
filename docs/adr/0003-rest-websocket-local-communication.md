# ADR-003 - REST + WebSocket Local Communication

## Status

Accepted for MVP.

## Context

REST is appropriate for commands, queries, approvals, provider listing, and workspace management. WebSocket is appropriate for live logs, execution progress, agent events, and long-running run updates.

## Decision

Use REST + WebSocket over localhost between Electron app and Go local service.

## Consequences

### Positive

- Local service exposes a clear localhost API.
- REST contracts are easy for Electron/React to consume.
- WebSocket supports live execution streams without polling.
- The model can be documented with OpenAPI plus event schemas.

### Negative / Trade-offs

- Local authentication and origin checks are required.
- WebSocket reconnect and event ordering behavior must be designed.
- The localhost API must avoid arbitrary command execution endpoints.

## Notes

Rejected alternatives:

- gRPC: strong but unnecessarily complex for MVP and less natural for Electron/React integration.
- stdio JSON-RPC: simple but less suitable for a service that may evolve into an independent local daemon.
- named pipes / Unix sockets: good for hardened enterprise versions, but cross-platform complexity is higher for MVP.

OpenAPI should document REST contracts. WebSocket events should follow a structured event schema.
