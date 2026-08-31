# DV AI Agent Plugins Marketplace — Project Template

A GitLab project template for DV teams to publish AI agent plugins
(Claude Code, Claude AI Enterprise, Cursor, Codex) to the DV plugin marketplace.

---

## Repo layout

```
your-repo/
├── .gitlab-ci.yml
├── .claude-plugin/
│   └── marketplace.json        # Claude Code / Claude AI catalog
├── .cursor-plugin/
│   └── marketplace.json        # Cursor catalog (delete if not targeting Cursor)
├── .agents/plugins/
│   └── marketplace.json        # Codex catalog (delete if not targeting Codex)
└── agent-plugins/
    └── <plugin-id>/
        ├── .claude-plugin/
        │   └── plugin.json     # plugin manifest
        ├── .codex-plugin/
        │   └── plugin.json     # optional — Codex-native manifest
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

**`.agents/plugins/marketplace.json`** — Codex catalog. Local `path` resolves
against the **repo root**, not against `.agents/plugins/`:

```json
{
  "name": "my-team-marketplace",
  "interface": { "displayName": "My Team" },
  "plugins": [
    {
      "name": "my-plugin",
      "source": { "type": "local", "path": "./agent-plugins/my-plugin" },
      "policy": { "installation": "AVAILABLE", "authentication": "ON_INSTALL" },
      "category": "Productivity"
    }
  ]
}
```

`policy.installation` is one of `AVAILABLE`, `INSTALLED_BY_DEFAULT`,
`NOT_AVAILABLE`. `policy.authentication` is `ON_INSTALL` or `ON_USE`.
Codex falls back to `.claude-plugin/marketplace.json` when this file is
absent, but only the native catalog carries policy and category.

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

**Codex** — users install via CLI:

```
codex plugin marketplace add https://gitlab.com/<group>/<your-repo>.git --ref main
codex plugin add <plugin-id>@<marketplace-name>
```

Then browse with `/plugins` inside Codex, and restart Codex (or start a new
thread) so bundled skills and MCP tools load. If the plugin declares an MCP
server, users also run `codex mcp login <server-name>`.

Codex workspace admins can import a marketplace under **Admin > Plugins >
Add > Import marketplace**, but that path **only supports GitHub
repositories** — a GitHub mirror of this repo is required for
admin-managed distribution. Import does not carry over `policy` values;
admins set those per plugin. Plugins that declare MCP servers become
Desktop-only after import.

---

## Removing a plugin

**Full removal:** delete `agent-plugins/<plugin-id>/` AND remove its entry from every `marketplace.json` file. Merge to `main` — the publish job deactivates it.

**Soft-deprecation:** keep the directory, add `"metadata": { "archived": "true" }` to `plugin.json`, AND remove from `marketplace.json`. The pipeline enforces consistency — it fails if a plugin is listed in `marketplace.json` but its directory is missing, or if `archived: true` is set but the entry is still advertised.

---

## Plugin ownership

The first GitLab project to publish a `plugin_id` owns it. To transfer ownership, set `PLUGINS_CHANGE_OWNERSHIP: "true"` in `.gitlab-ci.yml` for one pipeline run.

## More

- Full details: see [`AGENTS.md`](AGENTS.md) and comments in [`.gitlab-ci.yml`](.gitlab-ci.yml).
