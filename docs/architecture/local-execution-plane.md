# Local Execution Plane

The local execution plane is responsible for performing work inside the user's development environment.

It is composed of:

```text
sweorchestrai-local-front
  |
  v
sweorchestrai-local-service
  |
  v
Local providers, repositories, MCP tools, and design integrations
```

## Components

| Component | Responsibility |
|---|---|
| `sweorchestrai-local-front` | Local desktop UI for runs, providers, workspaces, approvals, and live execution status. |
| `sweorchestrai-local-service` | Go local service that executes provider/tool/repository operations. |
| Local providers | Tools such as Claude Code, Codex CLI, Ollama, OpenCode, and future assistants. |
| MCP/tool integrations | Figma, Git, filesystem, test runners, and project-specific tools. |
| Local repositories | User-selected repositories associated with cloud projects. |

## Responsibilities

The local service should:

- connect to local repositories,
- connect to local AI/code assistant tools through real-time streaming integrations,
- execute approved local commands,
- manage provider adapters,
- manage MCP/tool integrations,
- stream execution logs and run status to the local app,
- maintain local audit logs and service state,
- sync relevant execution results with the cloud backend,
- enforce safety boundaries around filesystem, Git, commands, providers, and secrets.

## Non-Responsibilities

The local execution plane should not:

- own canonical long-lived project state,
- replace the cloud project management system,
- expose public APIs outside localhost,
- perform uncontrolled shell execution,
- silently execute destructive actions.
