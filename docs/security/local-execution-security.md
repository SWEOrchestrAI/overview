# Local Execution Security

The local service has access to local repositories, tools, and potentially sensitive development environments. Security must be treated as a core MVP requirement.

## Minimum Security Rules

- Bind only to `127.0.0.1`.
- Use a local session token.
- Validate request origin where applicable.
- Use a random or controlled local port.
- Do not expose arbitrary command execution endpoints.
- Use workspace-scoped permissions.
- Require approval gates for risky actions.
- Maintain audit logs.
- Classify commands by risk.
- Restrict access to secrets and environment files.
- Separate read, write, and destructive permission levels.

## Threats to Consider

| Threat | Description |
|---|---|
| Malicious website calling localhost | Browser-based attacks may attempt to call local services. |
| Compromised dependency | A dependency may attempt to abuse local execution access. |
| Accidental destructive command | AI/provider output may suggest unsafe shell or Git operations. |
| Prompt/tool injection | Repository content or external instructions may attempt to manipulate agents. |
| Secret exposure | Provider prompts or logs may accidentally include credentials. |
| Unauthorized repository access | Local service execution could access folders beyond approved workspaces. |
| Unsafe provider output | Provider may generate commands or patches that require validation. |

## Approval-Gated Actions

Approval should be required before:

- modifying files,
- deleting files,
- running shell commands,
- installing dependencies,
- applying patches,
- committing changes,
- pushing to remote repositories,
- changing Figma/design assets,
- reading sensitive locations,
- accessing secrets or environment files.

## Audit Trail

Every sensitive action should record:

- timestamp,
- project,
- workspace,
- repository,
- provider,
- requested action,
- approval decision,
- files or commands involved,
- final result.
