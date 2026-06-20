# Cloud Front Repository

## Purpose

`sweorchestrai-cloud-front` is the cloud project management frontend for SWEOrchestrAI.

It provides visibility and management for projects, requirements, backlog, roadmap, diagrams, design stages, documentation, execution history, approvals, and project status.

## Technology

| Area | Technology |
|---|---|
| UI | React |
| Language | TypeScript |
| API communication | Authenticated HTTP APIs |

## Responsibilities

The cloud front should support:

- login and authenticated cloud sessions,
- project list and project detail views,
- project overview/status pages,
- requirements management,
- use case management,
- backlog management,
- roadmap management,
- diagram metadata and artifact browsing,
- design stage and design portfolio metadata,
- execution history visibility,
- approval/status visibility,
- documentation management within cloud project context.

## Non-Responsibilities

The cloud front should not:

- perform AI coding,
- directly access local repositories,
- run local shell commands,
- bypass local approval gates,
- connect directly to provider CLIs,
- own backend persistence or business logic,
- act as the overview/profile documentation hub.

## Key Dependencies

| Dependency | Purpose |
|---|---|
| `sweorchestrai-cloud-back` | Auth, project APIs, requirements, backlog, roadmap, diagrams, design metadata, execution history, artifacts. |
| Object storage URLs | Controlled artifact display and downloads through backend-mediated access. |
| Local execution records | Read-only visibility into runs synced by local service. |

## Initial MVP Scope

- Login screen.
- Project list.
- Project detail.
- Requirements/backlog read and edit flows.
- Roadmap view.
- Diagrams/design placeholder sections.
- Execution history read-only view.
- Artifact browsing through backend metadata.
