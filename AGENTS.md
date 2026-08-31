# AGENTS.md

This repo publishes AI agent plugins (Claude Code, Claude AI Enterprise, Cursor, Codex) to this marketplace. Every directory under `agent-plugins/` is a plugin — add the manifest, update `marketplace.json`, push, and CI handles publishing.

## Plugin structure

```
agent-plugins/
└── <plugin-id>/
    ├── .claude-plugin/
    │   └── plugin.json     # required for Claude
    ├── .cursor-plugin/
    │   └── plugin.json     # required for Cursor
    ├── .codex-plugin/
    │   └── plugin.json     # required for Codex
    ├── .mcp.json           # optional — MCP server connections
    ├── .codex-mcp.json     # optional — MCP server connections for Codex
    ├── skills/             # optional — bundled skills
    ├── agents/             # optional — sub-agent definitions
    ├── commands/           # optional — slash commands
    └── hooks/              # optional — lifecycle hooks
```

### plugin.json

Same format for `.claude-plugin/`, `.cursor-plugin/` and `.codex-plugin/`:

```json
{
  "name": "your-plugin-id",
  "version": "1.0.0",
  "description": "What this plugin does.",
  "author": { "name": "Your Team", "email": "your.team@doubleverify.com" },
  "keywords": ["relevant", "tags"]
}
```

- `name` must equal the plugin directory name, and must match the entry `name` in every `marketplace.json`
- Component fields (`skills`, `agents`, `commands`, `hooks`) are string paths starting with `./`
- `category` belongs in `marketplace.json`, not here
- `.codex-plugin/plugin.json` additionally accepts `mcpServers` (a path to the Codex MCP config) and an `interface` object that drives how Codex presents the plugin at install time

To remove a plugin, see `README.md` — it requires editing both `plugin.json` and `marketplace.json`.

## marketplace.json

Claude, Cursor and Codex use different formats. All three files live at the **repo root**.

**`.claude-plugin/marketplace.json`** — `source` is a relative path, no `pluginRoot`:

```json
{ "name": "your-plugin-id", "source": "./agent-plugins/your-plugin-id", "description": "...", "version": "1.0.0", "category": "devops" }
```

**`.cursor-plugin/marketplace.json`** — `pluginRoot: "agent-plugins"` in metadata, `source` is a bare name:

```json
{ "name": "your-plugin-id", "source": "your-plugin-id", "description": "...", "version": "1.0.0", "category": "devops" }
```

**`.agents/plugins/marketplace.json`** — Codex catalog. `source` is an object; `path` resolves against the **repo root**, not `.agents/plugins/`. No `version` field on the entry:

```json
{ "name": "your-plugin-id", "source": { "type": "local", "path": "./agent-plugins/your-plugin-id" }, "policy": { "installation": "AVAILABLE", "authentication": "ON_INSTALL" }, "category": "Productivity" }
```

Bump `version` in `plugin.json` and in the Claude/Cursor marketplace entries on every change.

## CI/CD

- Feature branches → `-dev` version published (safe to iterate)
- `main` → production version, registered in the marketplace catalog
- Pipeline fails if a `marketplace.json` entry has no matching directory, or if a plugin is marked archived but still advertised
- No local build or test step — push and check the pipeline
