# Functional Requirements

## FR-001 - Project Management

The system shall allow users to create and manage software projects.

Projects should include:

- name,
- description,
- status,
- owner,
- repositories,
- requirements,
- use cases,
- backlog items,
- diagrams,
- design artifacts,
- execution history.

## FR-002 - Repository Registration

The local app/local service shall allow users to register local repositories and associate them with cloud projects.

Repository metadata should include:

- local path,
- linked project,
- Git remote,
- branch,
- provider capabilities,
- workspace permissions.

## FR-003 - Provider Management

The local service shall detect and manage available local providers.

Supported provider categories:

- CLI-based coding assistants,
- local model runners,
- MCP tools,
- design tools,
- mock providers.

The system shall expose provider capabilities to the local app and cloud backend.

## FR-004 - Execution Runs

The system shall support execution runs initiated from the local app or cloud project context.

A run should include:

- project ID,
- repository/workspace,
- provider,
- task/instruction,
- status,
- events,
- logs,
- approvals,
- artifacts,
- result summary.

## FR-005 - Live Run Streaming

The local service shall stream live run events to the local app using WebSocket.

Events may include:

- run created,
- provider started,
- log output,
- file change proposed,
- approval required,
- command started,
- command completed,
- test started,
- test completed,
- run completed,
- run failed,
- run cancelled.

## FR-006 - Approval Management

The system shall support approval requests for sensitive actions.

Approvals should include:

- action type,
- target resource,
- proposed command/change,
- risk level,
- explanation,
- approve/reject actions,
- audit timestamp.

## FR-007 - Diagram Management

The system shall support diagrams per project.

Users should be able to:

- manually attach diagrams,
- generate diagrams with AI,
- classify diagrams by type,
- link diagrams to use cases or architecture decisions,
- store diagram files as artifacts,
- version or replace diagrams over time.

## FR-008 - Design Stage

The system shall support a design stage for each project.

The design stage should include:

- product style direction,
- typography,
- fonts,
- color palette,
- design tokens,
- components,
- screens,
- user flows,
- use-case-to-screen mapping,
- Figma references or generated Figma assets.

## FR-009 - Cloud Project Visibility

The cloud web app shall allow users to view and manage projects without requiring direct AI coding execution.

The cloud front should support:

- project overview,
- backlog,
- requirements,
- roadmap,
- diagrams,
- design portfolio,
- execution history,
- documentation,
- approvals/status visibility.

## FR-010 - Local/Cloud Sync

The local service shall sync relevant local execution state with the cloud backend.

Sync should include:

- run status,
- result summaries,
- provider used,
- execution timestamps,
- approval outcomes,
- artifact references,
- error summaries.
