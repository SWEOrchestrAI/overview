# Architecture Overview

SWEOrchestrAI follows a hybrid architecture:

- **Cloud Control Plane**
- **Local Execution Plane**

The cloud side owns long-lived project state, collaboration, authentication, artifacts, and project management logic.

The local side owns execution inside the user's development environment.

```mermaid
flowchart TB
    subgraph Local["Local Execution Plane"]
        LF["sweorchestrai-local-front<br/>Electron + React"]
        LS["sweorchestrai-local-service<br/>Go"]
        Providers["Local Providers<br/>Claude Code / Codex CLI / Ollama / OpenCode"]
        MCP["MCP + Tool Integrations<br/>Figma / Git / Filesystem / Test Runners"]
        Repos["Local Repositories"]

        LF -->|REST + WebSocket over localhost| LS
        LS --> Providers
        LS --> MCP
        LS --> Repos
    end

    subgraph Cloud["Cloud Control Plane"]
        CF["sweorchestrai-cloud-front<br/>React"]
        CB["sweorchestrai-cloud-back<br/>Spring Boot Monolith"]
        DB["Cloud DBs<br/>Project State"]
        OBJ["S3-like Object Storage<br/>Images / Documents / Diagrams"]

        CF --> CB
        CB --> DB
        CB --> OBJ
    end

    LS -->|Authenticated Sync APIs| CB
    LF -. optional authenticated APIs .-> CB
```

## Core Principle

```text
Cloud = Control Plane
Local = Execution Plane
```

## Key Rules

- The cloud backend should not directly run local coding assistants.
- The cloud backend should not require direct access to local repositories.
- The local service performs work through local tools and providers.
- The cloud frontend provides project management only, not direct AI coding.
- Long-lived project state belongs in the cloud database.
- Binary/project artifacts belong in object storage.
