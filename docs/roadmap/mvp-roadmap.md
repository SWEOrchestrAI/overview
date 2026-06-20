# MVP Roadmap

## Phase 1 - Documentation and Repo Setup

- [ ] Create GitHub organization or grouped repositories.
- [ ] Create overview/profile README.
- [ ] Create all MVP repositories.
- [ ] Define repository responsibilities.
- [ ] Add architecture diagrams.
- [ ] Add initial ADRs.
- [ ] Add MVP scope document.

## Phase 2 - Cloud Backend Foundation

- [ ] Implement auth model.
- [ ] Implement project entity.
- [ ] Implement workspace/team concepts.
- [ ] Implement repository metadata.
- [ ] Implement execution session model.
- [ ] Implement artifact metadata model.
- [ ] Implement initial REST API.

## Phase 3 - Cloud Front Foundation

- [ ] Implement login.
- [ ] Implement project list.
- [ ] Implement project detail.
- [ ] Implement backlog/requirements view.
- [ ] Implement diagrams/design placeholder sections.
- [ ] Implement execution history read-only view.

## Phase 4 - Local Service Foundation

- [ ] Create Go service.
- [ ] Add health endpoint.
- [ ] Add capabilities endpoint.
- [ ] Add provider registry.
- [ ] Add mock provider.
- [ ] Add workspace registration.
- [ ] Add run creation.
- [ ] Add WebSocket run event stream.
- [ ] Add local audit logging.

## Phase 5 - Local Front Foundation

- [ ] Create Electron + React app.
- [ ] Launch/connect to local service.
- [ ] Show local-service health.
- [ ] Show available providers.
- [ ] Register local workspace.
- [ ] Start mock execution run.
- [ ] Stream logs/events.
- [ ] Approve/reject requested actions.

## Phase 6 - First Real Provider Integration

- [ ] Add Ollama or CLI-based provider integration.
- [ ] Execute a controlled local task.
- [ ] Stream provider output.
- [ ] Store execution summary locally and in cloud.
- [ ] Add approval gates before file writes.

## Phase 7 - Diagrams and Design Stage

- [ ] Add diagram metadata to cloud backend.
- [ ] Add manual diagram upload.
- [ ] Add generated diagram placeholder flow.
- [ ] Add design stage entity.
- [ ] Add design tokens/typography/color metadata.
- [ ] Link use cases to diagrams and design artifacts.
- [ ] Prepare future Figma/MCP integration.
