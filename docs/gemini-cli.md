# Gemini CLI Extension

This repository is a Gemini CLI extension because it includes a root `gemini-extension.json`.

## Install

```bash
gemini extensions install https://github.com/Martini-Film/mcp --auto-update
```

Restart Gemini CLI after installation.

## Verify

Inside Gemini CLI:

```text
/mcp
```

You should see a `martini` MCP server.

If authentication is needed:

```text
/mcp auth martini
```

## Commands

- `/martini:connect` - connection and authentication help.
- `/martini:overview` - read-only project overview.
- `/martini:generate-plan` - plan paid generation work before executing.
- `/martini:upload-check` - check upload/download readiness.
- `/martini:project` - general project-oriented Martini request.

## Included Gemini Files

- `gemini-extension.json` configures the remote Martini MCP server.
- `GEMINI.md` gives Gemini Martini-specific operating guidance.
- `commands/martini/*.toml` adds Martini workflow commands.
- `policies/martini.toml` asks for user confirmation on generation and destructive tool names.

## Manual Setup

If you do not want to install the extension:

```bash
gemini mcp add -s user --transport http martini https://www.martini.film/mcp
```

## Gallery Discovery

For Gemini CLI gallery discovery, keep these in place:

- Public GitHub repo.
- `gemini-cli-extension` GitHub topic.
- `gemini-extension.json` at repository root.
- Valid manifest where `name` matches the installed extension directory name.

Validate before release:

```bash
npx -y @google/gemini-cli extensions validate .
```
