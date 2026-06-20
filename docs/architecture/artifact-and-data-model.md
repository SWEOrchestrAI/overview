# Artifact and Data Model

SWEOrchestrAI separates canonical metadata from binary/project artifacts.

## Data Ownership

| Storage | Responsibility |
|---|---|
| Cloud database | Canonical project state and metadata. |
| Object storage | Larger binary/project artifacts. |
| Markdown/docs | Exports, templates, generated documentation, and portfolio documentation. |

The cloud database is the source of truth for long-lived project state.

Markdown files can exist as exports, templates, or generated documentation, but they should not be the canonical source of truth for collaborative project state.

## Entity Concepts

| Entity | Purpose |
|---|---|
| Project | Top-level software project. |
| Repository | Local or remote repository linked to a project. |
| Requirement | Functional or non-functional project requirement. |
| UseCase | User/system interaction scenario. |
| BacklogItem | Work item, feature, bug, task, refactor, or documentation item. |
| ExecutionRun | AI/tool execution session. |
| RunEvent | Event emitted during execution. |
| Approval | Human approval gate for sensitive operations. |
| Provider | Local AI/tool provider available through the local service. |
| Diagram | Project diagram metadata. |
| DesignPortfolio | Design-stage metadata and Figma/design references. |
| Artifact | Binary or document artifact stored in object storage. |
| ArchitectureDecision | ADR-style technical decision. |

## Artifact Examples

Artifacts may include:

- images,
- diagrams,
- screenshots,
- generated documents,
- design exports,
- PDFs,
- run logs if needed,
- uploaded files,
- architecture assets,
- generated reports.
