# Cloud Control Plane

The cloud control plane owns persistent project state, collaboration-oriented features, authentication, artifact metadata, and project management logic.

It is composed of:

```text
sweorchestrai-cloud-front
  |
  v
sweorchestrai-cloud-back
  |
  v
Cloud DBs + Object Storage
```

## Components

| Component | Responsibility |
|---|---|
| `sweorchestrai-cloud-front` | Cloud UI for project management and visibility. |
| `sweorchestrai-cloud-back` | Backend monolith for auth, persistence, sync, project logic, and artifact metadata. |
| Cloud DBs | Canonical project state and metadata. |
| Object storage | Images, documents, diagrams, design exports, screenshots, and other binary artifacts. |

## Responsibilities

The cloud side should handle:

- users,
- organizations/workspaces,
- projects,
- project metadata,
- requirements,
- use cases,
- backlog,
- roadmap,
- architecture decisions,
- diagrams,
- design portfolio metadata,
- execution sessions,
- approvals,
- comments,
- audit summaries,
- artifacts,
- sync state.

## Non-Responsibilities

The cloud control plane should not:

- directly run local coding assistants,
- require direct access to local repositories,
- perform local shell commands,
- bypass local approval gates,
- replace the local execution service.
