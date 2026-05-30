# Client Setup

Martini's hosted MCP server is available at:

```text
https://www.martini.film/mcp
```

## Gemini CLI

Install the extension from GitHub:

```bash
gemini extensions install martini-film/mcp --auto-update
```

Restart Gemini CLI and run:

```text
/mcp
```

See [Gemini CLI extension](gemini-cli.md).

## Claude

Add Martini as a custom connector:

1. Open Claude settings.
2. Go to Connectors.
3. Add a custom connector.
4. Use `https://www.martini.film/mcp` as the server URL.
5. Connect and complete Martini sign-in.

Team and Enterprise workspaces may require an admin or owner to add the connector first.

## Claude Code

```bash
claude mcp add --transport http martini https://www.martini.film/mcp
```

Then run:

```text
/mcp
```

## Cursor and Generic MCP Clients

Use a remote HTTP MCP server named `martini`:

```json
{
  "mcpServers": {
    "martini": {
      "type": "http",
      "url": "https://www.martini.film/mcp"
    }
  }
}
```

If the client expects Gemini-style settings, use:

```json
{
  "mcpServers": {
    "martini": {
      "httpUrl": "https://www.martini.film/mcp"
    }
  }
}
```

## Troubleshooting

- Restart the client after adding Martini.
- Use the client's MCP status command, usually `/mcp`, to confirm the server is connected.
- If sign-in does not open, check whether the client supports remote HTTP MCP servers with OAuth.
- If your organization blocks custom connectors, ask an admin to allow `https://www.martini.film/mcp`.

