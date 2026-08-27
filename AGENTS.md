# AGENTS.md

This repo publishes AI agent plugins (Claude Code, Claude AI Enterprise, Cursor) to this marketplace. Every directory under `agent-plugins/` is a plugin — add the manifest, update `marketplace.json`, push, and CI handles publishing.

## Plugin structure

```
agent-plugins/
└── <plugin-id>/
    ├── .claude-plugin/
    │   └── plugin.json     # required for Claude
    ├── .cursor-plugin/
    │   └── plugin.json     # required for Cursor
    ├── .mcp.json           # optional — MCP server connections
    ├── skills/             # optional — bundled skills
    ├── agents/             # optional — sub-agent definitions
    ├── commands/           # optional — slash commands
    └── hooks/              # optional — lifecycle hooks
```

### plugin.json

Same format for both `.claude-plugin/` and `.cursor-plugin/`:

```json
{
  "name": "your-plugin-id",
  "version": "1.0.0",
  "description": "What this plugin does.",
  "author": { "name": "Your Team", "email": "your.team@doubleverify.com" },
  "keywords": ["relevant", "tags"]
}
```

- `name` must equal the plugin directory name
- Component fields (`skills`, `agents`, `commands`, `hooks`) are string paths starting with `./`
- `category` belongs in `marketplace.json`, not here

To remove a plugin, see `README.md` — it requires editing both `plugin.json` and `marketplace.json`.

## marketplace.json

Claude and Cursor use different formats. Both files live at the **repo root**.

**`.claude-plugin/marketplace.json`** — `source` is a relative path, no `pluginRoot`:

```json
{ "name": "your-plugin-id", "source": "./agent-plugins/your-plugin-id", "description": "...", "version": "1.0.0", "category": "devops" }
```

**`.cursor-plugin/marketplace.json`** — `pluginRoot: "agent-plugins"` in metadata, `source` is a bare name:

```json
{ "name": "your-plugin-id", "source": "your-plugin-id", "description": "...", "version": "1.0.0", "category": "devops" }
```

Bump `version` in both `plugin.json` and the marketplace entry on every change.

## CI/CD

- Feature branches → `-dev` version published (safe to iterate)
- `main` → production version, registered in the marketplace catalog
- Pipeline fails if a `marketplace.json` entry has no matching directory, or if a plugin is marked archived but still advertised
- No local build or test step — push and check the pipeline
