# Martini MCP for Gemini CLI

Use Martini from Gemini CLI through Martini's hosted Model Context Protocol server.

Martini is an AI video production tool for filmmakers. The MCP server lets compatible AI assistants browse and create Martini projects, scenes, subjects, assets, bins, and generation jobs.

## Install

```bash
gemini extensions install martini-film/martini-mcp --auto-update
```

Restart Gemini CLI after installation. On first use, Gemini CLI will connect to Martini's hosted MCP server and open the normal Martini sign-in flow.

Verify the connection inside Gemini CLI:

```text
/mcp
```

You should see a `martini` MCP server.

## Example prompts

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

## Manual MCP setup

If you do not want to install the extension, add the MCP server directly:

```bash
gemini mcp add -s user --transport http martini https://www.martini.film/mcp
```

## What this extension includes

- `gemini-extension.json` with Martini's hosted MCP server configuration.
- `GEMINI.md` with usage guidance for Martini workflows.
- A `/martini:project` command for common project-oriented requests.

The extension does not include local binaries and does not require API keys. Authentication is handled by Martini's OAuth flow.

## Release and gallery listing

Gemini CLI can install extensions from public GitHub repositories. The Gemini CLI extension gallery crawls public repositories with the `gemini-cli-extension` topic and a root-level `gemini-extension.json`.

For this repository:

- Keep `gemini-extension.json` at the repository root.
- Keep the repository public.
- Add the GitHub topic `gemini-cli-extension`.
- Tag releases, for example `v0.1.0`, after validating the manifest.

## Links

- Martini: https://www.martini.film
- MCP docs: https://www.martini.film/docs/mcp
- Terms: https://www.martini.film/terms
- Support: support@martini.film

