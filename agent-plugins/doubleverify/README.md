# DoubleVerify Agent Plugin

> The `doubleverify` plugin is currently in **Beta**.

Reference for what this plugin contains and how it behaves. For what it does
and how to install it, see the [repository README](../../README.md).

---

## Requirements

- An MCP-capable AI client: Claude Code, Claude Desktop / claude.ai, or Cursor
- A DV account with access to at least one DV program
- Network access to `https://mcp.doubleverify.com/mcp`

## Setup

The plugin bundles a client-specific MCP manifest so the `dv-mcp` server is
easy to register regardless of host:

| Client | Manifest | Notes |
|---|---|---|
| Claude Code | `.mcp.json` | `dv-program-context` can write this into the project's `.mcp.json` or the user's `~/.claude.json` automatically if it is missing. |
| Cursor | `.cursor-plugin/plugin.json` | Declares the MCP server directly; no manual `.mcp.json` editing needed. |

Authentication is OAuth 2.1 / PKCE against DV's authentication gateway
(RFC 9728 protected-resource discovery). The client drives a one-time
"Connect" flow in its own UI; tokens are stored and refreshed automatically.
There is no API key to manage by hand.

Once connected, confirm setup by checking that `list-my-programs` appears in
the client's tool list. If it does not, reload or restart the client rather
than retrying the tool call.

---

## Skills

Skills are loaded by the host agent based on their `description` frontmatter,
and are designed to compose. One skill can delegate to another rather than
every skill re-implementing shared behavior such as program resolution or the
legal disclaimer.

| Skill | Role in the plugin |
|---|---|
| [`dv-reporting`](skills/dv-reporting/README.md) | Required entry point for any DV data question. Routes to a datamart, applies business rules, runs the query and interprets results |
| [`dv-program-context`](skills/dv-program-context/README.md) | Resolves `program_id`, which every data tool call depends on. Can self-configure `dv-mcp` on Claude Code |
| [`dv-feedback`](skills/dv-feedback/README.md) | Records user feedback through `submit-feedback` |

---

## The `dv-mcp` server

The MCP server that connects the plugin to DV's backend services. It is the
single source of live data for every skill, so `dv-reporting`,
`dv-program-context` and `dv-feedback` all call it rather than talking to DV
systems directly.

- **Endpoint:** `https://mcp.doubleverify.com/mcp`
- **Protocol:** MCP over HTTP
- **Auth:** OAuth 2.1 / PKCE, described under [Setup](#setup)

| Tool | Purpose | Called by |
|---|---|---|
| `list-my-programs` | Lists the DV programs the current user can access, with `id`, `name` and `timezone` for each | `dv-reporting`, `dv-program-context` |
| `get-datapoint-catalog` | Returns the metrics and dimensions a given `datamart_id` supports, grouped by tag. The only valid source of field names for a query | `dv-reporting` |
| `run-query` | Runs a query against a datamart using field display names rather than internal semantic IDs, and returns display-name column headers | `dv-reporting` |
| `submit-feedback` | Records verbatim user feedback into DV's analytics logs | `dv-feedback` |

More tools are expected as the plugin grows into other DV products.

### `get-datapoint-catalog`

Requires `datamart_id`. Returns a compact catalog grouped by tag:

```text
[Key Quality Indicators] M: Authentic Rate, Fraud Rate | D: Campaign Name
```

`M:` marks metrics and `D:` marks dimensions. Callers are expected to call this
before `run-query` rather than guessing field names. Anything not in the
catalog is unavailable, not substitutable.

### `run-query`

Requires `program_id`, `datamart_id`, `semantic_model`, `semantic_view`,
`fields` and `date_range`. Optional: `filters`, `sorts`, `limit` (default 500)
and `time_zones`.

Filter syntax is easy to get backwards:

- Equality: `{"Campaign Name": "My Campaign"}`
- Exclude: prefix the value with a dash, `{"Delivery Site": "-NULL,-N/A"}`
- OR: comma-separate values with no dash, `{"Media Property": "RTB 123,RTB 456"}`
- NULL match: `{"Delivery Site": "NULL"}`
- Numeric comparisons go in the **value**, not the key: `{"UC Incidents": ">0"}`, never `{">UC Incidents": "0"}`

`date_range` is a string in `"YYYY/MM/DD HH:mm:ss to YYYY/MM/DD HH:mm:ss"`
format. Sorting does not exclude NULLs, so pair a sort on a numeric field with
a `">0"` filter when nulls and zeros should not appear.

### `submit-feedback`

Requires `feedback`, 1 to 2000 characters, passed verbatim and never
paraphrased. Optional: `category` (`bug`, `feature_request`, `data_quality`,
`praise`, `other`) and `sentiment` (`positive`, `negative`, `neutral`), both
omitted when the caller is not confident. The tool sanitizes input before
logging and returns `logged_text` plus a `redacted` flag; when `redacted` is
true, the caller shows `logged_text` so the user sees what was recorded.

### Conventions across every tool

- **`reason`.** Every tool takes an optional `reason` string for DV's internal analytics. It describes analytical intent in one short sentence, never contains personal data and never changes tool behavior.
- **No fabrication.** Program IDs, datamart IDs and field names must come from a tool call in the current chat, never invented or carried over from memory.
- **Scoped access.** Every call is scoped to the requesting user's own DV permissions. There is no elevated or service-level access path through this server.

---

## Data and privacy

- Every DV skill shows a single, session-scoped legal disclaimer before any other output, covering AI-generated-content risk, third-party LLM use and DV's data-handling terms. It appears once per session regardless of which skill the session enters through.
- All tool calls take an optional `reason` argument DV uses for internal analytics. It never contains personal data and never affects tool behavior.
- Data access is scoped to the requesting user's own DV permissions. `dv-reporting` is read-only today; that is a property of the current skill set rather than a hard constraint of the plugin.
- User-submitted content that flows through a skill, such as `dv-feedback`, is redacted for personal data before being sent anywhere.

---

