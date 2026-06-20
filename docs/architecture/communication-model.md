# Communication Model

SWEOrchestrAI uses different communication channels depending on the boundary.

## Local Front <-> Local Service

The selected MVP communication model is:

```text
Electron + React
  |
  v
Electron Main / Preload API
  |
  v
REST + WebSocket over localhost
  |
  v
Go Local Service
```

REST is used for command/query operations.

WebSocket is used for real-time execution events.

## Example REST Endpoints

```http
GET  /health
GET  /capabilities
GET  /providers
POST /providers/{providerId}/test

GET  /workspaces
POST /workspaces

POST /runs
GET  /runs/{runId}
POST /runs/{runId}/cancel

GET  /approvals/pending
POST /approvals/{approvalId}/approve
POST /approvals/{approvalId}/reject
```

## Example WebSocket Streams

```text
WS /runs/{runId}/stream
WS /events
```

## Electron Boundary

The React renderer should not directly depend on transport details.

The local app should expose a typed preload API such as:

```ts
window.sweLocalService.startRun(...)
window.sweLocalService.cancelRun(...)
window.sweLocalService.subscribeToRun(...)
window.sweLocalService.approveAction(...)
```

The Electron main process should manage or mediate the local service lifecycle where appropriate.

## Local Service <-> Cloud Backend

The local service syncs with the cloud backend through authenticated API calls.

Example API concepts:

```http
GET  /api/projects/{projectId}/tasks/pending
POST /api/executions
POST /api/executions/{executionId}/events
POST /api/executions/{executionId}/result
POST /api/artifacts/presigned-upload
POST /api/local-nodes/{nodeId}/heartbeat
```

## Cloud Front <-> Cloud Backend

The cloud frontend communicates with the cloud backend through standard authenticated HTTP APIs.

Responsibilities include:

- project CRUD,
- backlog management,
- roadmap management,
- requirements and use case management,
- diagram metadata,
- design portfolio management,
- execution history,
- approval visibility,
- artifact browsing,
- documentation management.
