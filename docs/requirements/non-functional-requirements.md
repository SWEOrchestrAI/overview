# Non-Functional Requirements

## NFR-001 - Security

The local service must bind only to localhost and must not expose APIs publicly.

Minimum rules:

- bind to `127.0.0.1`,
- require local session token,
- validate request origin where applicable,
- avoid arbitrary command execution endpoints,
- approval-gate risky actions,
- log sensitive actions,
- restrict workspace access.

## NFR-002 - Auditability

The system must maintain audit logs for important actions.

Audit events should include:

- who initiated the action,
- where it was initiated,
- provider used,
- command or operation requested,
- files affected,
- approval status,
- timestamps,
- final result.

## NFR-003 - Extensibility

The architecture must allow new providers, tools, and transports to be added without rewriting the core system.

Extension points:

- provider adapters,
- MCP connectors,
- diagram generators,
- design generators,
- local commands,
- cloud sync integrations.

## NFR-004 - Local-First Execution

AI coding and repository operations must execute locally by default.

The cloud should not require source code upload for local coding tasks.

## NFR-005 - Clear Separation of Concerns

Each repository must have a clear responsibility.

The local front handles UX.

The local service handles local execution.

The cloud front handles cloud project management.

The cloud backend handles persistence, auth, business logic, sync, and artifacts.

The overview repo handles documentation and portfolio presentation.

## NFR-006 - Portfolio-Grade Documentation

The project should include documentation that explains:

- architecture,
- repository responsibilities,
- local/cloud split,
- provider abstraction,
- communication protocols,
- security model,
- design stage,
- diagram management,
- roadmap,
- key architecture decisions.
