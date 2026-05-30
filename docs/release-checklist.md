# Gemini CLI Release Checklist

## Required for gallery discovery

- [ ] Repository is public on GitHub.
- [ ] Repository has the `gemini-cli-extension` topic.
- [ ] `gemini-extension.json` is at the repository root.
- [ ] Manifest `name` matches the repository/extension directory name: `martini-mcp`.
- [ ] Manifest version matches the Git tag for release builds.
- [ ] Extension installs with `gemini extensions install martini-film/martini-mcp`.
- [ ] Martini MCP server appears in Gemini CLI `/mcp`.
- [ ] First-time OAuth sign-in completes successfully.

## Recommended validation

- [ ] Run `gemini extensions validate .` if available in the installed Gemini CLI version.
- [ ] Run `gemini extensions link .` for local testing.
- [ ] Restart Gemini CLI and verify the extension context loads.
- [ ] Test project listing.
- [ ] Test one read-only project inspection prompt.
- [ ] Test one write flow in a disposable Martini project.
- [ ] Confirm write/generation prompts ask for confirmation when appropriate.

## Release flow

```bash
git tag v0.1.0
git push origin v0.1.0
```

The Gemini CLI gallery crawler checks public repositories with the `gemini-cli-extension` topic. Listing is automatic if the repository passes validation.

