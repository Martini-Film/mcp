# Martini MCP Extension

Martini is an AI video production tool for filmmakers. This extension connects Gemini CLI to Martini's hosted MCP server at `https://www.martini.film/mcp`.

When the user asks to work with Martini projects, scenes, subjects, assets, bins, uploads, image generation, or video generation, prefer the Martini MCP tools exposed by the `martini` server.

Operational guidance:

- If the user has not provided a Martini project, first list or inspect available projects before taking action.
- Treat project, scene, asset, bin, upload, and generation changes as user-visible production actions.
- Before destructive, expensive, or broad actions, briefly restate the intended action and ask for explicit confirmation.
- Do not invent Martini project IDs, asset IDs, or generation IDs. Discover them through the MCP tools or ask the user.
- Keep prompts for image and video generation concrete: include subject, action, camera, setting, style, duration, and constraints when available.
- When a tool returns a Martini URL or resource, include it in the response so the user can open the result.
- Do not request, print, or store authentication tokens. Martini sign-in should happen through the MCP client's OAuth browser flow.
- If the MCP server is not connected, tell the user to restart Gemini CLI and run `/mcp` to verify the `martini` server.

