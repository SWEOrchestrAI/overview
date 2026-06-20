# Local Front Repository

## Purpose

`sweorchestrai-local-front` is the local desktop UI for SWEOrchestrAI.

It gives the user direct visibility and control over local providers, workspaces, execution runs, logs, approvals, and local project/repository status.

## Technology

| Area | Technology |
|---|---|
| Desktop shell | Electron |
| UI | React |
| Language | TypeScript |
| Local communication | Electron main/preload API, REST, WebSocket |

## Responsibilities

The local front should:

- display local service health,
- show available providers and provider status,
- allow workspace/repository registration,
- start and cancel execution runs,
- display live execution logs and run events,
- show pending approvals,
- allow approve/reject decisions,
- show local project and repository status,
- communicate with the local service through Electron main/preload and REST + WebSocket.

## Non-Responsibilities

The local front should not:

- execute provider commands directly,
- perform shell execution directly from the React renderer,
- own canonical project state,
- replace the cloud project management UI,
- expose public network APIs,
- bypass local service approval gates.

## Key Dependencies

| Dependency | Purpose |
|---|---|
| `sweorchestrai-local-service` | Execution, providers, workspace state, approvals, and live events. |
| Electron main/preload | Safe bridge between renderer and local APIs. |
| WebSocket stream | Live run logs and execution events. |
| Cloud backend APIs | Optional authenticated project context and sync visibility. |

## Initial MVP Scope

- Electron + React shell.
- Local service connection and health display.
- Provider list.
- Workspace registration.
- Mock run creation.
- Live event stream.
- Approval inbox.
- Basic project/repository status view.
