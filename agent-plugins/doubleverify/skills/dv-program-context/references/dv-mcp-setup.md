# DV MCP Server Configuration

The `dv-mcp` MCP server connects the agent to DV Pinnacle data services.
It must be registered in the user's MCP configuration before any DV data
tool (`list-my-programs`, `run-query`, `get-datapoint-catalog`, etc.)
can be called.

## Configuration

The canonical `dv-mcp` entry for this artifact lives in the plugin's
bundled `.mcp.json` at the plugin root. **Read that file and use its
`mcpServers["dv-mcp"]` block verbatim** when writing the target MCP
config. Do not synthesize keys or values from memory or from this
document — every field's authoritative content is in the bundled file,
which is env-pinned per artifact by the build script.

### File locations by client

| Client | File | Scope |
|---|---|---|
| Claude Code | `.mcp.json` in the project root, or `~/.claude.json` under `mcpServers` | project / global |
| Codex | Not configured here; use INSTALL-CODEX.md and `codex mcp login dv-mcp` | plugin install/auth |

## Authentication flow

The gateway publishes `/.well-known/oauth-protected-resource` (RFC 9728).
On first tool call, the MCP client drives an OAuth 2.1 / PKCE handshake
against PIAM/Keycloak using its built-in UI. The user clicks **Connect**
once; the client stores and refreshes tokens automatically. No CLI or
manual token management is required.

## Verification

After configuration, confirm the server is available by checking that
`list-my-programs` appears in the tool list. If it does not, ask the
user to reload or restart their client.
