# ADR-008 - Object Storage for Artifacts

## Status

Accepted for MVP.

## Context

SWEOrchestrAI needs to manage binary and project artifacts that do not belong directly in relational database rows.

## Decision

Use S3-like object storage for binary/project artifacts.

Artifacts:

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

## Consequences

### Positive

- Backend manages artifact metadata.
- Uploads use controlled flows.
- Artifacts can be linked to projects and entities.
- Large files do not bloat the primary database.

### Negative / Trade-offs

- Object storage access control must be enforced.
- Artifact lifecycle and retention policies are required.
- Presigned upload/download flows must be implemented carefully.

## Notes

Access control should be enforced at the metadata/API layer.
