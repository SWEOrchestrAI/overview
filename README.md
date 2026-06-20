# SWEOrchestrAI

**Cloud-managed software delivery. Locally executed AI engineering.**

SWEOrchestrAI is a hybrid local/cloud AI Project Manager for software engineering workflows. It combines cloud-based project management with local AI agent execution, repository-aware automation, diagrams, design workflows, MCP integrations, and approval-gated coding operations.

## Architecture

SWEOrchestrAI is split into two main planes:

| Plane | Purpose |
|---|---|
| Local Execution Plane | Runs local coding agents, provider adapters, MCP tools, repository operations, and approval-gated commands. |
| Cloud Control Plane | Manages projects, users, requirements, backlog, diagrams, design portfolios, execution history, artifacts, and sync state. |

## Repositories

| Repository | Purpose | Stack |
|---|---|---|
| `sweorchestrai-local-front` | Local desktop UI for provider configuration, workspaces, runs, logs, and approvals. | Electron, React, TypeScript |
| `sweorchestrai-local-service` | Local execution service that connects to providers, MCP tools, local repos, and syncs with cloud. | Go |
| `sweorchestrai-cloud-front` | Cloud web app for project management, visibility, diagrams, design stages, and execution history. | React, TypeScript |
| `sweorchestrai-cloud-back` | Cloud backend monolith for auth, persistence, sync, artifacts, project logic, and APIs. | Spring Boot, Kotlin/Java |
| `sweorchestrai-overview` / `.github` | Documentation, architecture, roadmap, ADRs, and portfolio hub. | Markdown |

## MVP Scope

- Hybrid local/cloud architecture.
- Local desktop app.
- Go local service.
- Cloud project management frontend.
- Cloud backend monolith with DBs and object storage.
- Provider-agnostic local execution.
- REST + WebSocket communication between local front and local service.
- Project diagrams and design stage as first-class features.
- Approval-gated local execution.
- Portfolio-grade documentation and ADRs.

## Documentation

Start here:

- [Vision](./docs/vision.md)
- [Architecture Overview](./docs/architecture/overview.md)
- [Repository Overview](./docs/repositories/overview.md)
- [Functional Requirements](./docs/requirements/functional-requirements.md)
- [Non-Functional Requirements](./docs/requirements/non-functional-requirements.md)
- [MVP Roadmap](./docs/roadmap/mvp-roadmap.md)
- [Architecture Decision Records](./docs/adr/)

## Status

SWEOrchestrAI is currently in MVP architecture and foundation planning.

## License

Copyright (c) 2026.

This repository is currently shared for portfolio and documentation purposes only. No license is granted for reuse, redistribution, or derivative works unless explicitly stated.
