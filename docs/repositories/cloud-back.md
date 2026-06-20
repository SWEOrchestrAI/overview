# Cloud Back Repository

## Purpose

`sweorchestrai-cloud-back` is the cloud backend monolith for SWEOrchestrAI.

It owns cloud APIs, authentication, persistence, project management logic, local/cloud sync, artifact metadata, and API surfaces for cloud and local clients.

## Technology

| Area | Technology |
|---|---|
| Backend | Spring Boot |
| Language | Kotlin or Java |
| Persistence | Cloud database |
| Artifact storage | S3-like object storage |
| API style | Authenticated REST APIs, future event APIs where needed |

## Responsibilities

The cloud backend should handle:

- authentication,
- project persistence,
- workspace/team management,
- project management logic,
- backlog,
- roadmap,
- requirements,
- use cases,
- diagram metadata,
- design portfolio metadata,
- execution sessions,
- approvals,
- artifact metadata,
- sync APIs,
- APIs for cloud clients,
- APIs for local clients,
- access control and audit summaries.

## Non-Responsibilities

The cloud backend should not:

- run local coding assistants directly,
- require direct access to local repositories,
- execute local shell commands,
- bypass approval gates owned by the local execution workflow,
- store large binary artifacts directly in relational tables,
- act as the local provider adapter layer.

## Key Dependencies

| Dependency | Purpose |
|---|---|
| Cloud database | Canonical project state and metadata. |
| Object storage | Binary/project artifacts. |
| `sweorchestrai-cloud-front` | Cloud project management client. |
| `sweorchestrai-local-service` | Sync client for execution runs, approvals, events, and artifacts. |
| Auth provider/session system | User and workspace authorization. |

## Initial MVP Scope

- Auth model.
- Project entity.
- Workspace/team concepts.
- Repository metadata.
- Requirement and backlog entities.
- Execution session model.
- Approval records.
- Artifact metadata model.
- Initial REST API.
- Local-service sync endpoints.
