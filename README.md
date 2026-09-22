# DoubleVerify AI Agent Plugins

The official DoubleVerify plugin marketplace for AI coding and chat agents:
Claude Code, Claude Desktop and Cursor. Install a DV plugin and query
your DV Pinnacle® media quality data in natural language, right inside your agent.

---

## Quick start (Claude Code)

> The `doubleverify` plugin is currently in **Beta**.

**Prerequisites:** Claude Code installed and a DV account with access
to at least one DV Pinnacle program. Data access follows your existing program
permissions. No API keys or manual MCP configuration required.

Run these commands one at a time **inside a Claude Code session**:

```text
/plugin marketplace add doubleverify/ai-marketplace
/plugin install doubleverify@doubleverify
```

Complete the installation prompts. If Claude Code asks you to reload plugins,
run `/reload-plugins` before continuing.

Ask your agent:

```text
List my programs
```

Sign in with your DV account when prompted. Select a program from
the results, then try:

```text
Show campaign health for this program over the last 30 days
```

If sign-in does not appear or the tools are unavailable, run `/mcp`, select
the plugin's `dv-mcp` server and complete authentication. If the server is
missing, check that `doubleverify` is enabled in `/plugin` and restart Claude Code.

### Other agents

Marketplace repository:
[doubleverify/ai-marketplace](https://github.com/doubleverify/ai-marketplace)

| Agent | How to add |
|-------|-----------|
| **Claude Desktop / claude.ai** | Settings > Plugins > Add marketplace, paste the repo URL, then install **doubleverify**. |
| **Cursor** | Add the marketplace URL in the plugins UI, then install **doubleverify**. |

---

## Available plugins

| Plugin | Description | Category |
|--------|-------------|----------|
| **doubleverify** | The single plugin for all DoubleVerify agentic capabilities, connecting you to DV campaign performance data, insights, recommendations and workflows. | data |

### What `doubleverify` does

Connects your agent to the DV MCP service and adds three skills:

| Skill | What it does |
|-------|--------------|
| **dv-reporting** | Ask natural-language questions about your DV campaign data — performance, brand suitability, fraud, viewability, and more. |
| **dv-program-context** | Identifies which DV account to pull from — ask about any program without configuring anything. |
| **dv-feedback** | Send feedback about the plugin, the data, or a specific result straight to the DV team from the chat. |

Reporting covers campaign performance, top campaigns, brand suitability,
fraud/SIVT, viewability, geo-compliance, blocking/filtering and DV Authentic
Attention® metrics on Open Web, YouTube, Meta, TikTok, X, Snapchat,
Pinterest, Reddit, Netflix, Instacart, LinkedIn, Spotify and Roblox.

It currently provides DV Pinnacle media-quality reporting and plugin feedback,
and is built to grow. New DV products and capabilities will be added over time.

**Reporting example:** ask *"How are my TikTok campaigns doing on brand
suitability?"* and the plugin identifies your program, pulls TikTok data, and
provides an analysis with flagged anomalies.

Full plugin reference, covering every skill, the `dv-mcp` tools, setup and
data handling:
[`agent-plugins/doubleverify/README.md`](agent-plugins/doubleverify/README.md).

---

## Repository layout

```
.
├── .claude-plugin/marketplace.json   # Claude Code / Claude catalog
├── .cursor-plugin/marketplace.json   # Cursor catalog
└── agent-plugins/
    └── doubleverify/
        ├── README.md                 # full plugin reference
        ├── .claude-plugin/plugin.json
        ├── .cursor-plugin/plugin.json    # inlines the dv-mcp config
        ├── .mcp.json                     # Claude Code / generic MCP config
        └── skills/
            ├── dv-reporting/             # reporting skill + business-glossary references
            ├── dv-program-context/       # program resolution + dv-mcp setup
            └── dv-feedback/              # feedback capture
```

---

## Support

- Questions and issues: **AIMarketplacesupport@doubleverify.com**
- Feedback from inside the agent: just say *"send feedback to DV"*.

---

## Contributing

Publishing or updating a plugin in this marketplace: see
[`AGENTS.md`](AGENTS.md) and the comments in [`.gitlab-ci.yml`](.gitlab-ci.yml).

---

## License

MIT. See [`LICENSE.txt`](LICENSE.txt).
