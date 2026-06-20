# Diagram Management

Diagrams are first-class project artifacts in SWEOrchestrAI.

They can be manually attached or AI-generated.

## Diagram Sources

| Source | Description |
|---|---|
| Manual upload | User attaches an existing diagram. |
| AI-generated | System generates a diagram from project context. |
| Tool-generated | Diagram comes from an external tool or integration. |
| Design-linked | Diagram is linked to Figma or design-stage artifacts. |

## Diagram Types

Supported diagram categories may include:

- architecture,
- sequence,
- flow,
- infrastructure,
- domain/data,
- UX/user flow,
- deployment.

## Storage Model

| Layer | Responsibility |
|---|---|
| Cloud database | Diagram metadata, ownership, links, type, version, and project relationships. |
| Object storage | Diagram files, images, exports, and binary assets. |
| Documentation | Human-readable explanation and exported references. |

## Suggested Metadata Model

| Field | Description |
|---|---|
| `id` | Diagram identifier. |
| `projectId` | Linked project. |
| `title` | Human-readable name. |
| `type` | Architecture, sequence, flow, infrastructure, domain/data, UX, deployment, etc. |
| `source` | Manual, AI-generated, tool-generated, design-linked. |
| `artifactId` | Linked artifact stored in object storage. |
| `linkedUseCaseIds` | Use cases reflected by the diagram. |
| `linkedRequirementIds` | Requirements reflected by the diagram. |
| `linkedAdrIds` | Architecture decisions related to the diagram. |
| `version` | Diagram version. |
| `createdAt` | Creation timestamp. |
| `updatedAt` | Last update timestamp. |
