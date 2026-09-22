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

Same format for `.claude-plugin/` and `.cursor-plugin/`:

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

To remove a plugin, see [Removing a plugin](#removing-a-plugin) below. It requires
editing both `plugin.json` and `marketplace.json`.

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

Bump `version` in `plugin.json` and in the Claude/Cursor marketplace entries on every change.

## Removing a plugin

**Full removal:** delete `agent-plugins/<plugin-id>/` and remove its entry from
every `marketplace.json` file. Merge to `main` and the publish job deactivates
it.

**Soft-deprecation:** keep the directory, add `"metadata": { "archived": "true" }`
to `plugin.json`, and remove the entry from every `marketplace.json`.

The pipeline enforces consistency either way. It fails if a plugin is listed in
`marketplace.json` but its directory is missing, or if `archived: true` is set
while the entry is still advertised.

## Plugin ownership

The first GitLab project to publish a `plugin_id` owns it. To transfer
ownership, set `PLUGINS_CHANGE_OWNERSHIP: "true"` in `.gitlab-ci.yml` for one
pipeline run, then remove it.

## CI/CD

- Feature branches → `-dev` version published (safe to iterate)
- `main` → production version, registered in the marketplace catalog
- Pipeline enforces `marketplace.json` consistency, see [Removing a plugin](#removing-a-plugin)
- No local build or test step — push and check the pipeline
