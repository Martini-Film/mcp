# Risk Mitigation Notes

## Main risks

| Risk | Mitigation |
| --- | --- |
| Users accidentally trigger expensive generation jobs | Keep tool descriptions clear on the MCP server, rely on Gemini CLI confirmation, and use extension instructions to ask before expensive actions. |
| Users accidentally modify or delete production project data | Mark destructive MCP tools accurately server-side and keep extension instructions conservative. |
| OAuth or remote MCP discovery fails in Gemini CLI | Document `/mcp` verification and direct `gemini mcp add` fallback. Keep the hosted MCP endpoint stable at `https://www.martini.film/mcp`. |
| Gemini gallery crawler does not list the repo | Keep repo public, add `gemini-cli-extension` topic, keep `gemini-extension.json` at root, and tag releases. |
| Tool names or schemas are rejected by Gemini | Validate tool schemas against Gemini CLI MCP discovery; keep names simple and schema descriptions short. |
| Users assume this is the Gemini consumer app | README states this is for Gemini CLI only. |

## Server-side approval readiness

The Gemini CLI extension itself is a lightweight wrapper around Martini's hosted MCP server. Most safety and reliability work should happen on the server:

- Use OAuth for user authentication.
- Enforce Martini project permissions on every tool call.
- Make destructive tools explicit in names and descriptions.
- Prefer narrow, task-specific tools over broad arbitrary mutation tools.
- Return clear user-visible summaries for write actions.
- Keep generation tools explicit about cost, duration, and project target.
- Avoid exposing secrets, internal IDs that users do not need, or raw provider responses.

