# DoubleVerify

[Beta] The single plugin for all DoubleVerify agentic capabilities, connecting you to DV campaign performance data, insights, recommendations and workflows.

DoubleVerify's agent plugin for AI coding/chat clients — Claude Code, Claude Desktop / claude.ai, and Cursor. It connects an agent to DV's backend services via the `dv-mcp` MCP server and gives it a set of **skills**, each teaching the agent how to carry out one category of DV task safely and correctly.

- **Plugin name:** `doubleverify`
- **License:** MIT
- **Backing service:** [`dv-mcp`](https://mcp.doubleverify.com/mcp), DV's hosted MCP gateway

## What this plugin is

The DoubleVerify plugin — one plugin for all DV capabilities in your AI workflow. It currently provides Pinnacle media-quality reporting and plugin feedback, and is built to grow — new DV products and capabilities will be added over time.

**Reporting example:** Ask *"How are my TikTok campaigns doing on brand suitability?"* — the plugin identifies your program, pulls TikTok data, and provides an analysis with flagged anomalies.

## Install

### Claude Code

```text
/plugin marketplace add doubleverify/ai-marketplace
/plugin install doubleverify@doubleverify
```

Complete the installation prompts. If Claude Code asks you to reload plugins, run `/reload-plugins` before continuing.

### Claude Desktop / claude.ai

Settings > Plugins > Add marketplace, paste the marketplace repository URL ([doubleverify/ai-marketplace](https://github.com/doubleverify/ai-marketplace)), then install **doubleverify**.

### Cursor

Add the marketplace URL in the plugins UI, then install **doubleverify**.

## Skills

Skills are loaded by the host agent based on their `description` frontmatter, and are designed to compose — one skill can delegate to another rather than every skill re-implementing shared behavior (program resolution, the legal disclaimer, etc.).

Currently included:

| Skill | Purpose |
|---|---|
| [`dv-reporting`](skills/dv-reporting/README.md) | Entry point for DV Pinnacle data questions. Routes a question to the right datamart, applies DV's business rules and thresholds, runs the query, and interprets the results. |
| [`dv-program-context`](skills/dv-program-context/README.md) | Resolves which DV program (account) the current chat should operate against, and — on Claude Code — can self-configure the `dv-mcp` connection if it isn't already registered. Any skill that needs a `program_id` delegates here. |
| [`dv-feedback`](skills/dv-feedback/README.md) | Records user-volunteered feedback about the plugin, the data, or a tool's behavior into DV's analytics logs. |

More skills — covering other DV products or actions — are expected to land here over time.

## Requirements

- An MCP-capable AI client: Claude Code, Claude Desktop / claude.ai, or Cursor
- A DoubleVerify account with access to at least one DV program
- Network access to `https://mcp.doubleverify.com/mcp`

## Setup

The plugin bundles a client-specific MCP manifest so the `dv-mcp` server is easy to register regardless of host:

| Client | Manifest | Notes |
|---|---|---|
| Claude Code | `.mcp.json` | `dv-program-context` can write this into the project's `.mcp.json` or the user's `~/.claude.json` automatically if it's missing — see that skill's README. |
| Cursor | `.cursor-plugin/plugin.json` | Declares the MCP server directly; no manual `.mcp.json` editing needed. |

Authentication is OAuth 2.1 / PKCE against DV's authentication gateway (RFC 9728 protected-resource discovery). The client drives a one-time "Connect" flow in its own UI; tokens are stored and refreshed automatically. There is no API key to manage by hand.

Once connected, confirm setup by checking that `list-my-programs` appears in the client's tool list. If it does not, reload or restart the client rather than retrying the tool call.

## Data & privacy notes

These conventions apply across all skills and are expected to extend to future ones:

- Every DV skill shows a single, session-scoped legal disclaimer before any other output, covering AI-generated-content risk, third-party LLM use, and DV's data-handling terms. It's shown once per session regardless of which skill the session enters through.
- All tool calls take an optional `reason` argument DV uses for internal analytics — it should never contain PII and never affects tool behavior.
- Data access is scoped to the requesting user's own DV permissions. `dv-reporting` today is read-only; that is a property of the current skill set, not a hard constraint of the plugin.
- User-submitted content that flows through a skill (e.g. `dv-feedback`) is redacted for PII before being sent anywhere.

## Support

- Questions and issues: **AIMarketplacesupport@doubleverify.com**
- Feedback from inside the agent: just say *"send feedback to DV"*.

## Repository layout

```
.
├── .claude-plugin/plugin.json    # Claude Code plugin manifest
├── .cursor-plugin/plugin.json    # Cursor plugin manifest (inlines dv-mcp config)
├── .mcp.json                     # Claude Code / generic MCP server config
└── skills/
    ├── dv-reporting/             # Pinnacle reporting skill + business-glossary references
    ├── dv-program-context/       # Program resolution + dv-mcp setup
    └── dv-feedback/              # Feedback capture
    # future skills land here as sibling directories
```
