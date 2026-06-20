# ADR-001 - Hybrid Local/Cloud Architecture

## Status

Accepted for MVP.

## Context

SWEOrchestrAI must operate on local repositories, local CLIs, local models, MCP tools, and user-specific development environments. Cloud-hosting all LLM execution would not fit the desired product model.

## Decision

Use a hybrid architecture where cloud acts as the control plane and the local service acts as the execution plane.

## Consequences

### Positive

- Code execution happens locally.
- Project state is persisted in the cloud.
- Cloud does not need direct access to local source code.
- The architecture supports user-specific local tools and credentials.

### Negative / Trade-offs

- The local service must be robust, secure, and auditable.
- Local setup and connectivity become part of the product experience.
- Sync logic is required between local execution state and cloud project state.

## Notes

Sensitive local operations are approval-gated.
