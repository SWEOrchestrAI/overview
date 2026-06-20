# ADR-006 - Design and Diagrams as First-Class Features

## Status

Accepted for MVP.

## Context

SWEOrchestrAI is intended to support the full software delivery lifecycle, not only coding tasks. Architecture diagrams, design decisions, user flows, and visual design artifacts are part of project management and delivery.

## Decision

Diagrams and design stage are first-class project features.

Diagram features:

- AI-generated diagrams,
- manual attachments,
- architecture diagrams,
- sequence diagrams,
- flow diagrams,
- infrastructure diagrams,
- domain/data diagrams,
- links to use cases or architecture decisions.

Design stage features:

- Figma portfolio generation,
- design tokens,
- fonts,
- typography scale,
- color palettes,
- component definitions,
- use-case-driven screens,
- user flows,
- design documentation.

## Consequences

### Positive

- Diagrams have metadata in cloud DB.
- Files/assets are stored in object storage.
- Design artifacts can be linked to use cases.
- Figma/MCP integration can be supported by the local service.

### Negative / Trade-offs

- Additional metadata models are required.
- Artifact storage and access control become more important.
- Generated design/diagram artifacts need versioning and review workflows.

## Notes

The MVP can start with metadata and manual upload flows before deeper generation and Figma integration.
