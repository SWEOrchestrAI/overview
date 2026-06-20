# Local Service Repository

## Purpose

`sweorchestrai-local-service` is the Go local execution service for SWEOrchestrAI.

It connects local repositories, local tools, CLI assistants, MCP tools, Figma integrations, and local models to the SWEOrchestrAI local/cloud workflow.

## Technology

| Area | Technology |
|---|---|
| Service language | Go |
| Local API | REST + WebSocket |
| Execution model | Provider adapters, command executor, approval engine |
| Sync | Authenticated cloud backend client |

## Responsibilities

The local service should provide:

- provider adapters,
- MCP integrations,
- workspace/repository management,
- controlled command execution,
- approval engine,
- local audit log,
- cloud sync client,
- REST API for local app commands and queries,
- WebSocket API for live run events,
- provider capability detection,
- run state management,
- safety boundaries for filesystem, Git, commands, providers, and secrets.

## Non-Responsibilities

The local service should not:

- replace the cloud backend,
- own canonical long-lived project state,
- expose public APIs,
- execute destructive actions without approval,
- silently access repositories outside approved workspaces,
- require one specific AI provider,
- act as the organization documentation hub.

## Key Dependencies

| Dependency | Purpose |
|---|---|
| Local repositories | Execution target and project source context. |
| Provider CLIs/models | AI coding, local model, and assistant execution. |
| MCP tools | Tool and design integrations. |
| Git | Repository status, diffs, branches, and controlled operations. |
| `sweorchestrai-cloud-back` | Sync API, execution records, artifacts, and project context. |

## Initial MVP Scope

- Go service scaffold.
- `GET /health`.
- `GET /capabilities`.
- Provider registry.
- Mock provider.
- Workspace registration.
- Run creation.
- WebSocket run event stream.
- Approval request model.
- Local audit logging.
- Cloud sync client placeholder.
