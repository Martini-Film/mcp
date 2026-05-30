# OAuth and Authentication

Martini MCP uses Martini's normal account sign-in flow. Users should authenticate through the MCP client's browser-based OAuth flow.

## User Expectations

- Users sign in with a Martini account.
- Tool calls run with the signed-in user's Martini permissions.
- The MCP client should not ask users to paste Martini tokens.
- This repository does not contain secrets or local credentials.

## Client Behavior

Clients that support remote HTTP MCP with OAuth should discover Martini's authentication metadata and guide the user through sign-in.

If OAuth does not start, the most likely causes are:

- The client does not support remote HTTP MCP auth.
- The client has blocked browser redirects.
- The organization requires admin approval for custom connectors.

