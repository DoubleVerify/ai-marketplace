# DV AI Agent Plugins Marketplace — Project Template

A GitLab project template for DV teams to publish AI agent plugins
(Claude Code, Claude AI Enterprise, Cursor) to the DV plugin marketplace.

---

## Repo layout

```
your-repo/
├── .gitlab-ci.yml
├── .claude-plugin/
│   └── marketplace.json        # Claude Code / Claude AI catalog
├── .cursor-plugin/
│   └── marketplace.json        # Cursor catalog (delete if not targeting Cursor)
└── agent-plugins/
    └── <plugin-id>/
        ├── .claude-plugin/
        │   └── plugin.json     # plugin manifest
        ├── .mcp.json           # optional — MCP server connections
        ├── skills/             # optional — bundled skills
        ├── agents/             # optional — sub-agent definitions
        ├── commands/           # optional — slash commands
        └── hooks/              # optional — lifecycle hooks
```

---

## marketplace.json

Claude and Cursor use different formats. Both files live at the **repo root**.

**`.claude-plugin/marketplace.json`** — `source` is a relative path, no `pluginRoot`:

```json
{
  "name": "my-team-marketplace",
  "owner": { "name": "My Team", "email": "my.team@doubleverify.com" },
  "metadata": {
    "description": "My team plugin marketplace.",
    "version": "1.0.0"
  },
  "plugins": [
    {
      "name": "my-plugin",
      "source": "./agent-plugins/my-plugin",
      "description": "What this plugin does.",
      "version": "1.0.0",
      "category": "devops"
    }
  ]
}
```

**`.cursor-plugin/marketplace.json`** — `pluginRoot` in `metadata`, `source` is a bare name:

```json
{
  "name": "my-team-marketplace",
  "owner": { "name": "My Team", "email": "my.team@doubleverify.com" },
  "metadata": {
    "description": "My team plugin marketplace.",
    "version": "1.0.0",
    "pluginRoot": "agent-plugins"
  },
  "plugins": [
    {
      "name": "my-plugin",
      "source": "my-plugin",
      "description": "What this plugin does.",
      "version": "1.0.0",
      "category": "devops"
    }
  ]
}
```

---

## plugin.json

Lives at `agent-plugins/<plugin-id>/.claude-plugin/plugin.json`:

```json
{
  "name": "my-plugin",
  "version": "1.0.0",
  "description": "What this plugin does.",
  "author": { "name": "My Team", "email": "my.team@doubleverify.com" },
  "keywords": ["relevant", "tags"]
}
```

---

## Publishing

Commit and push. The `publish|context-hub|plugins` job runs automatically:
- Feature branches → `-dev` version
- `main` → production version, registered in the marketplace catalog

**Claude Code** — users install via CLI:

```
/plugin marketplace add https://gitlab.com/<group>/<your-repo>.git
/plugin install <plugin-id>
```

**Claude Desktop / Claude AI / Cursor** — users add your marketplace and install plugins through their UI.

---

## Removing a plugin

**Full removal:** delete `agent-plugins/<plugin-id>/` AND remove its entry from both `marketplace.json` files. Merge to `main` — the publish job deactivates it.

**Soft-deprecation:** keep the directory, add `"metadata": { "archived": "true" }` to `plugin.json`, AND remove from `marketplace.json`. The pipeline enforces consistency — it fails if a plugin is listed in `marketplace.json` but its directory is missing, or if `archived: true` is set but the entry is still advertised.

---

## Plugin ownership

The first GitLab project to publish a `plugin_id` owns it. To transfer ownership, set `PLUGINS_CHANGE_OWNERSHIP: "true"` in `.gitlab-ci.yml` for one pipeline run.

## More

- Full details: see [`AGENTS.md`](AGENTS.md) and comments in [`.gitlab-ci.yml`](.gitlab-ci.yml).
