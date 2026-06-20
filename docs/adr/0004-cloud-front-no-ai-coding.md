# ADR-004 - Cloud Front Does Not Perform AI Coding

## Status

Accepted for MVP.

## Context

AI coding is tied to local repos, credentials, CLIs, MCP servers, and local models.

## Decision

Cloud frontend supports project management, visibility, documentation, design, and collaboration, but does not directly execute AI coding workflows.

## Consequences

### Positive

- Cloud front can request or schedule work.
- Local service performs execution.
- Cloud shows execution status and history.
- AI coding actions require a connected local environment.

### Negative / Trade-offs

- Cloud-only users cannot directly execute coding tasks without local connectivity.
- The product must clearly communicate when local execution is required.
- Cloud and local state must remain synchronized enough for useful visibility.

## Notes

The cloud front is the cloud project management UI. The overview/profile hub remains a separate documentation repository or `.github` profile repository.
