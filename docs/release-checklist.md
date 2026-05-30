# Release Checklist

## Gemini CLI Gallery Discovery

- [ ] Repository is public on GitHub.
- [ ] Repository has the `gemini-cli-extension` topic.
- [ ] `gemini-extension.json` is at the repository root.
- [ ] Manifest `name` matches the repository/extension directory name: `mcp`.
- [ ] Manifest version matches the Git tag for release builds.
- [ ] Extension installs with `gemini extensions install martini-film/mcp`.
- [ ] Martini MCP server appears in Gemini CLI `/mcp`.
- [ ] First-time OAuth sign-in completes successfully.

## Recommended Validation

- [ ] Run `npx -y @google/gemini-cli extensions validate .`.
- [ ] Run `gemini extensions link .` for local testing.
- [ ] Restart Gemini CLI and verify the extension context loads.
- [ ] Verify `/mcp auth martini`.
- [ ] Verify `/mcp` shows Martini tools.
- [ ] Test project listing.
- [ ] Test one read-only project inspection prompt.
- [ ] Test one write flow in a disposable Martini project.
- [ ] Confirm write/generation prompts ask for confirmation when appropriate.

## Public Docs

- [ ] Client setup docs match current public MCP endpoint.
- [ ] OAuth docs match current Martini sign-in behavior.
- [ ] Tool safety docs match current MCP capabilities.
- [ ] README includes install, auth, uninstall, support, and security notes.
- [ ] Support and security contacts are current.

## Release Flow

```bash
git tag v0.1.1
git push origin v0.1.1
gh release create v0.1.1 --title "v0.1.1" --notes-file CHANGELOG.md
```

The Gemini CLI gallery crawler checks public repositories with the `gemini-cli-extension` topic. Listing is automatic if the repository passes validation. No public SLA is documented beyond the crawler behavior.

