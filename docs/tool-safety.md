# Tool Safety

Martini MCP can expose user-visible project operations. Some actions may create or modify project data, start generation jobs, upload files, or change asset organization.

## User-Safe Defaults

MCP clients should:

- Ask before destructive, expensive, or broad write actions.
- Confirm the target project before creating or modifying production data.
- Avoid inventing project IDs, asset IDs, scene IDs, or generation IDs.
- Include Martini links returned by tools so users can inspect results.
- Treat signed URLs as sensitive while active.

## Capability Classes

| Class | Examples | Expected handling |
| --- | --- | --- |
| Read-only | Project listing, board overview, asset inspection | Safe to run when relevant. |
| Project writes | Create scenes, bins, nodes, or metadata | Confirm target project and summarize change. |
| Upload/download | Upload completion, asset URL handling | Check reachability and avoid exposing unnecessary signed URLs. |
| Paid generation | Image or video generation jobs | Present a plan and ask for confirmation before starting. |
| Destructive actions | Deletes or irreversible mutations, if exposed | Ask for explicit confirmation every time. |

## Server-Side Requirements

The Martini server should:

- Enforce user and project permissions on every tool call.
- Keep tool names and descriptions narrow and accurate.
- Mark read-only and destructive tools with the appropriate MCP annotations where supported.
- Return clear summaries for write actions.
- Avoid exposing secrets, internal-only provider payloads, or unnecessary raw IDs.

