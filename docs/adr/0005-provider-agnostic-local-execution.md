# ADR-005 - Provider-Agnostic Local Execution

## Status

Accepted for MVP.

## Context

SWEOrchestrAI should support different AI tools and local execution approaches instead of assuming all users use the same assistant or model provider.

## Decision

Local service supports provider adapters instead of hardcoding one AI tool.

Target providers:

- Claude Code,
- Codex CLI,
- Ollama,
- OpenCode,
- Mock provider,
- future providers.

## Consequences

### Positive

- Provider capabilities must be discoverable.
- Provider availability should be testable.
- Runs should record which provider executed the work.
- Provider-specific logic is isolated behind adapters.

### Negative / Trade-offs

- Provider capability modeling is required.
- Each provider may have different streaming, auth, and command semantics.
- The MVP needs at least one mock provider to validate orchestration before real integrations are complete.

## Notes

Provider adapters should expose a stable internal interface to the run engine.
