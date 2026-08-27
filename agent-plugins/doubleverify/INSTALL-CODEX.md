# Install the DV Pinnacle Agent Plugin into Codex

## Purpose

This is the complete, human-facing entry point for installing the DV
Pinnacle agent plugin into Codex from the downloaded ZIP. This artifact
is Markdown-only: the ZIP ships NO install script. You install either by
asking a coding agent to follow this document (Agent-Assisted Install)
or by following the manual instructions yourself (Manual Install).

The install is file-and-config only. Installing the plugin does NOT call
DV MCP tools, query DV data, list DV programs, or run any smoke test.

## Prerequisites

- The Codex CLI is installed and on your `PATH` (`codex --version`).
- A browser is available for the OAuth consent step.
- You are authorized against the DV MCP gateway this ZIP variant is
  pinned to (the `dv-mcp` OAuth login uses your DV/PIAM identity).
- You have unzipped the artifact. After extraction there is a single
  plugin root directory named `doubleverify-agent-plugin/` containing
  `.codex-plugin/plugin.json`, `.codex-mcp.json`, and `skills/`.

## Agent-Assisted Install

If you have a coding agent available (for example, in your editor), you
can have it perform the install.

If the artifact is already unzipped, ask the agent to read
`./doubleverify-agent-plugin/INSTALL-CODEX.md` and install this plugin
into Codex. Tell it to ask before writing outside the workspace or
running commands that need approval. Tell it not to call DV MCP tools,
query DV data, list DV programs, or run any smoke test.

If you attached or referenced the ZIP directly and have not unzipped it
first, ask the agent to extract the attached ZIP into workspace scratch,
read `doubleverify-agent-plugin/INSTALL-CODEX.md`, and install this
plugin into Codex. Tell it to ask before writing outside the workspace
or running commands that need approval. Tell it not to call DV MCP
tools, query DV data, list DV programs, or run any smoke test.

The agent must perform ONLY these install-time actions, in order:

1. If working from a ZIP, extract it into workspace scratch.
2. Resolve the extracted plugin root (the `doubleverify-agent-plugin/`
   directory produced by unzipping the artifact).
3. Confirm `.codex-plugin/plugin.json`, `.codex-mcp.json`, and `skills/`
   exist under that root. If any is missing, stop and report it.
4. If Codex plugin validation tooling is available, validate the
   extracted plugin before installing it. If validation tooling is not
   available, continue after the required file checks above.
5. Copy/sync the extracted plugin root to
   `~/plugins/doubleverify-agent-plugin`.
6. Create or update `~/.agents/plugins/marketplace.json` (see
   "Personal marketplace file" below).
7. Preserve unrelated marketplace entries and unrelated JSON keys.
8. Register `doubleverify-agent-plugin` in the personal marketplace.
9. Run `codex plugin add doubleverify-agent-plugin@personal`.
10. Run, or ask the user to run, `codex mcp login dv-mcp`.
11. Optionally run `codex plugin list` as the final lightweight
    verification that the plugin is installed and enabled.
12. Tell the user to restart Codex or start a new Codex thread.

The agent must NOT call DV MCP tools, query DV data, list DV programs,
or run any live smoke test. It may run local file/config commands needed
for installation, plus these Codex CLI commands only:
`codex plugin add ...`, `codex mcp login dv-mcp`, and optionally
`codex plugin list`.

### Personal marketplace file

When `~/.agents/plugins/marketplace.json` does NOT exist, create it with
the standard personal marketplace shape:

- Top-level `name` is `personal`.
- Top-level `interface.displayName` is `Personal`.
- Top-level `plugins` is an array.
- The `plugins` array contains one entry named
  `doubleverify-agent-plugin`.
- That entry's `source` is local and its `path` is
  `./plugins/doubleverify-agent-plugin`.
- That entry's `policy.installation` is `AVAILABLE`.
- That entry's `policy.authentication` is `ON_INSTALL`.
- That entry's `category` is `Productivity`.

When the file already EXISTS, merge using this procedure:

1. Parse the file as JSON.
2. Preserve all existing top-level keys.
3. Ensure `name` exists, defaulting to `personal` only if missing.
4. Ensure `interface.displayName` exists, defaulting to `Personal`
   only if missing.
5. Ensure top-level `plugins` is an array.
6. Remove any existing top-level plugin entry whose `name` is
   `doubleverify-agent-plugin`.
7. Append the `doubleverify-agent-plugin` entry shown above.
8. Write the formatted JSON back.

If the file exists but is NOT valid JSON, STOP and ask the user before
overwriting or repairing it.

Do NOT run `codex plugin marketplace add` for the default personal
marketplace. Codex discovers `~/.agents/plugins/marketplace.json`
implicitly.

For the default personal marketplace at
`~/.agents/plugins/marketplace.json`, Codex resolves
`source.path = ./plugins/doubleverify-agent-plugin` to
`~/plugins/doubleverify-agent-plugin`. Do not move the plugin under
`~/.agents/plugins/plugins/` or `~/.codex/plugins/` for this flow.

## Manual Install

If you do not want agent assistance, run these steps yourself from the
directory that contains the extracted `doubleverify-agent-plugin/`
folder.

1. Copy the extracted plugin into the local plugins directory. Create
   `~/plugins/doubleverify-agent-plugin` if it does not exist, then
   sync or copy the extracted `doubleverify-agent-plugin/` folder into
   that destination.

2. Edit `~/.agents/plugins/marketplace.json`. If the file does not
   exist, create it using the personal marketplace shape above. If it
   already exists, merge using the 8-step procedure above, preserving
   any existing entries and keys. Use a JSON-aware editor or generate
   the merge mechanically; do not treat the file as plain text.

3. Add the plugin from the personal marketplace:
   run `codex plugin add doubleverify-agent-plugin@personal`.

4. Log in to the MCP server:
   run `codex mcp login dv-mcp`.

5. Restart Codex or start a new Codex thread.

Do NOT run `codex plugin marketplace add` for the default personal
marketplace; Codex discovers `~/.agents/plugins/marketplace.json`
implicitly.

## OAuth Login Notes

When you run `codex mcp login dv-mcp`, Codex may first report that the
provider rejected the initially discovered OAuth scopes, then retry the
login without scopes. That retry can succeed. If the command ultimately
completes, this is informational and is NOT a plugin install failure.

No static OAuth scopes are added to `.codex-mcp.json` to suppress this
message. Do not add a `scopes` list to work around it.

## Restart or New Thread

After the install commands complete, restart Codex or start a new Codex
thread so the newly registered plugin and `dv-mcp` server are loaded.

## What Not To Do

- Do NOT call DV MCP tools, query DV data, or list DV programs as part
  of installation.
- Do NOT run any smoke test or live DV check during install.
- Do NOT run `codex plugin marketplace add` for the default personal
  marketplace (Codex discovers it implicitly).
- Do NOT add static OAuth `scopes` to `.codex-mcp.json`.
- Do NOT overwrite or repair an existing `marketplace.json` that is not
  valid JSON; stop and ask the user first.
- Do NOT treat `codex plugin list` as a DV data check. It is allowed as
  a final local Codex install verification only.

## Troubleshooting

- `codex: command not found`: the Codex CLI is not installed or not on
  your `PATH`. Install it and confirm with `codex --version`.
- `codex plugin add doubleverify-agent-plugin@personal` cannot find the
  plugin: confirm the plugin was copied to
  `~/plugins/doubleverify-agent-plugin` and that
  `~/.agents/plugins/marketplace.json` contains the
  `doubleverify-agent-plugin` entry with
  `source.path = ./plugins/doubleverify-agent-plugin`.
- No `dv-mcp` tools after install: confirm `codex mcp login dv-mcp`
  completed, then restart Codex or start a new thread.
- `marketplace.json` is not valid JSON: do not let any tool overwrite
  it. Fix the JSON by hand or restore a backup, then re-run the merge.
- OAuth scope rejection message during login: see "OAuth Login Notes";
  if login ultimately completes, this is informational, not a failure.
