# ADR-009 - Approval-Gated Local Execution

## Status

Accepted for MVP.

## Context

The local service can interact with files, Git, shell commands, providers, MCP tools, and potentially sensitive local data. Automated execution must be constrained by clear human approval gates.

## Decision

Risky local actions require explicit approval.

Approval-gated actions:

- modifying files,
- deleting files,
- running shell commands,
- installing dependencies,
- applying patches,
- committing changes,
- pushing to remotes,
- changing Figma/design assets,
- reading sensitive locations,
- accessing secrets/env files.

## Consequences

### Positive

- Every execution produces an audit trail.
- Destructive actions require explicit approval.
- Approval requests describe what will happen.
- The system separates read-only, write, and destructive permissions.

### Negative / Trade-offs

- Approval prompts add friction to execution flows.
- Risk classification must be designed and maintained.
- Providers may need adapters that can pause execution while awaiting approval.

## Notes

Approval requests should be specific, understandable, and tied to concrete files, commands, or external resources.
