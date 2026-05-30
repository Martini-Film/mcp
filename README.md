# Martini MCP

Official client integration and distribution repo for Martini's hosted Model Context Protocol server.

Martini is an AI video production tool for filmmakers. The MCP server lets compatible AI assistants browse and create Martini projects, scenes, subjects, assets, bins, uploads, and generation jobs.

## Server

```text
https://www.martini.film/mcp
```

Authentication is handled by Martini's OAuth flow. This repository does not include local binaries, API keys, or secrets.

## Install

### Gemini CLI

```bash
gemini extensions install https://github.com/Martini-Film/mcp --auto-update
```

Restart Gemini CLI, then verify the connection:

```text
/mcp
```

You should see a `martini` MCP server.

### Claude

In Claude, add Martini as a custom connector with this server URL:

```text
https://www.martini.film/mcp
```

### Claude Code

```bash
claude mcp add --transport http martini https://www.martini.film/mcp
```

### Generic MCP Clients

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

Some clients use `httpUrl` instead of `url`:

```json
{
  "mcpServers": {
    "martini": {
      "httpUrl": "https://www.martini.film/mcp"
    }
  }
}
```

## Gemini CLI Commands

This extension includes prompt-wrapper commands:

- `/martini:connect`
- `/martini:overview`
- `/martini:generate-plan`
- `/martini:upload-check`
- `/martini:project`

## Uninstall

```bash
gemini extensions uninstall mcp
```

## Docs

- [Client setup](docs/clients.md)
- [Gemini CLI extension](docs/gemini-cli.md)
- [OAuth and authentication](docs/oauth.md)
- [Tool safety](docs/tool-safety.md)
- [Where this repo can be used](docs/listing-uses.md)
- [Release checklist](docs/release-checklist.md)
- [Risk mitigation](docs/risk-mitigation.md)

## Example Prompts

```text
List my Martini projects.
```

```text
Open my latest Martini project and summarize its scenes and assets.
```

```text
Create a new Martini project for a 30-second product film about a ceramic coffee dripper.
```

```text
In my current Martini project, create a scene breakdown for a moody tabletop coffee commercial.
```

## Security Notes

- Review tool approval prompts before allowing write, upload, or generation actions.
- Do not paste Martini access tokens into chat.
- Treat signed asset URLs as sensitive while they are active.
- Use disposable projects when testing new automated workflows.

## Support

Email support@martini.film.
