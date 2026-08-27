---
name: dv-program-context
description: >
  Use whenever a DV data tool requires a `program_id` argument. Establishes
  which PIAM program to use for the current chat by calling
  `list-my-programs` and confirming with the user.
---

# DV Program Context

DV data tools require a PIAM `program_id` on every call. This skill governs how the agent picks that id.

## Terminology

Three layers -- do not collapse them:

| Layer | Meaning | Example |
|---|---|---|
| **Program** | Access container from `list-my-programs`; supplies `program_id` and `timezone` | "PepsiCo Global", "Youtube" |
| **Platform / channel** | Measurement domain; supplies `datamart_id` | See `datamart-routing.md` (e.g. YouTube -> 2) |
| **Campaign** | Ad entity inside a program | `Platform Campaign Name` |

A program name may coincidentally match a platform word from `datamart-routing.md` (known case: program **Youtube** when the user asks about YouTube). That is still one program, not the platform. Platform data can exist across many programs -- never infer program from platform wording alone.

**User-facing language:** Say **program**, never "PIAM" or "PIAM program", in chat output.

## Step 0: Legal Disclaimer (session-scoped, show once)

<!-- DISCLAIMER-INLINE:BEGIN -->
If the disclaimer was already shown this session by **any** DV skill, skip this step. Otherwise, before ANY other output, print the following **verbatim** -- same wording, punctuation, and curly quotes. The gate is session-scoped, not per-skill.

> **Disclaimer:** This tool provides AI-generated analysis and insights based on DoubleVerify (“DV”) measurement data and methodologies. Outputs are provided for informational purposes only and do not constitute legal, professional, or business advice. AI-generated responses may be incomplete, inaccurate, or based on partial or evolving data and should not be relied upon as the sole basis for decision-making. Users are responsible for independently validating all results against official DV reporting, including the DV Pinnacle dashboard. In the event of any inconsistency between AI-generated output and official DV reporting, the official DV reporting controls. By using this tool, you acknowledge and consent to the use of AI-enabled technologies, including third-party large language model providers, in connection with the functionality of this feature. DV is not responsible for the availability, performance, security, or outputs of third-party AI systems. DV makes no warranties, express or implied, regarding the accuracy, completeness, reliability, or timeliness of the tool, underlying data, or any AI-generated output, and disclaims all implied warranties to the maximum extent permitted by law. All DV data, reporting, and related materials remain subject to the applicable agreement(s) between you and DV, in addition to these terms and any applicable product documentation. Please contact your DV support team for official reporting inquiries. By using this tool, you acknowledge that DV may collect and use usage data, prompts, inputs, outputs, interaction logs, and related technical metadata to operate, secure, support, and improve the functionality and performance of the tool and related DV services. Such data will be handled in accordance with DV’s privacy and data handling policies. Your data will not be shared with third-party advertisers or used for advertising purposes. Users should not submit confidential, regulated, personal, or sensitive information unless expressly permitted under the applicable agreement and product documentation.
<!-- DISCLAIMER-INLINE:END -->

## Prerequisites

Before applying the rules below, confirm `list-my-programs` is callable.
If it isn't, the `dv-mcp` MCP server isn't registered with this client.

### Detect the client environment

Determine which agent client is running **before** choosing a recovery
path. Use these signals:

| Signal | Client |
|---|---|
| `.claude-plugin/` directory loaded this skill | **Claude Code** |
| `.cursor-plugin/` directory loaded this skill | **Cursor** |
| `.codex-plugin/` directory loaded this skill | **Codex** |

Only the **Claude Code** path below performs auto-configuration.
All other clients must follow the manual recovery path.

### Claude Code only — auto-configure dv-mcp

> **Skip this section entirely if the client is not Claude Code.**

If `list-my-programs` is not available, create the MCP configuration
automatically using the specification in
[references/dv-mcp-setup.md](references/dv-mcp-setup.md):

1. Read the plugin's bundled `.mcp.json` file (located at the plugin
   root) to obtain the server entry (`type`, `url`, `oauth.clientId`).
2. Pick the target file. Either is acceptable; prefer the one the
   user already uses for other MCP servers:
   - **Project-scope:** `.mcp.json` in the user's project root
     (current working directory). Per-workspace; lives with the repo.
   - **User-scope:** `~/.claude.json`. Global to the user; all
     workspaces see `dv-mcp`.
3. Apply the entry under `mcpServers["dv-mcp"]` in the chosen file:
   - If a `dv-mcp` entry is already present with the same `url` and
     `oauth.clientId`, skip to step 5.
   - If the file exists, merge the entry into the existing
     `mcpServers` object — **preserve every other entry under
     `mcpServers`** (e.g. `mcpServers["github"]`,
     `mcpServers["sentry"]`, …) and every other top-level field.
   - If the file does not exist (project-scope case), create it
     containing only `mcpServers["dv-mcp"]`.
4. Tell the user which file was written and ask them to **restart
   Claude Code** so the new MCP server is loaded.
5. After restart, confirm `list-my-programs` is now callable.

### All other clients (Cursor / Codex) -- manual recovery only

> **Do NOT run the auto-configure steps above in Cursor, Codex, or any
> other non-Claude-Code client.**

For Cursor, the `.cursor-plugin/plugin.json` manifest declares the MCP
server directly, so auto-configuration is not needed. If
`list-my-programs` is missing, the plugin install or first OAuth
handshake failed. Ask the user to reload the window or reinstall the
plugin, then retry.

For Codex, do not edit `.mcp.json` manually. Ensure the plugin is
installed and enabled, run `codex mcp login dv-mcp`, then restart Codex
or start a new Codex thread. If installing from the zip, follow the
bundled `INSTALL-CODEX.md` instructions first. During login, Codex may
report that the provider rejected the initially discovered scopes and
then retry without scopes; this retry can be successful and should not
be treated as a plugin install failure if the command ultimately
completes.

### Hard stop

Do not attempt to answer the user's data question without `dv-mcp`
available; fabricating a `program_id` or substituting another tool is
not acceptable.

## Rules

1. **Use a name from this chat.** If the user has named a program in the current chat, resolve it to a `program_id` and `timezone` once via `list-my-programs` and use those values for the rest of the chat. If the name is ambiguous, partial, or doesn't match any program exactly, fall back to rule 2.
   - **Platform words are not program selection.** Channel names (YouTube, Meta, TikTok, Open Web, etc.) route to a datamart; they do not pick a program unless the user explicitly chose one from `list-my-programs` or said "select/program <name>".
   - **Never auto-select by name match.** If the user mentions a platform or channel (see `datamart-routing.md`), do not pick a program from `list-my-programs` merely because its **name** matches that platform word -- exact or fuzzy, any casing. Program names are arbitrary labels; a name match is not platform intent. Ask which program unless the user explicitly selected one (e.g. "select PepsiCo" or picked from the list).
   - **"Across programs"** means multiple programs. Cross-program queries are not supported in one session -- ask which single program to start with; do not loop all programs.

2. **Otherwise, list and ask.** Call `list-my-programs`:
   - Exactly one program → use it; store `id`, `name`, and `timezone`; echo the program name in chat output before showing tool results.
   - Multiple programs → ask the user which one. Do not pick arbitrarily. After selection, store `id`, `name`, and `timezone` from the chosen program.
   - Empty → tell the user they have no PIAM program access and stop.

3. **Never fabricate a `program_id`.** UUIDs from memory, from a different chat, or from documentation are not valid context. The only valid sources are: a fresh `list-my-programs` call in this chat, or a verbatim id pasted by the user in this chat.

4. **Echo the program name** in chat output before presenting tool results, e.g. "Querying `<Program Name>` for…". Catches mismatches in the response, not just in the tool-call dialog.

5. **Pass `program_id` on every tool call** that requires it. Selection does not persist across chats — re-establish in each new chat.

6. **Store program `timezone`.** `list-my-programs` returns `timezone` per program. Keep it in session context alongside `program_id` and `name`. `dv-reporting` uses it as the default query timezone for datamarts that allow timezone conversion.

7. **Always set `reason` on every tool call.** Every `dv-mcp` tool accepts an optional `reason: str` argument. Set it to one short sentence describing why you are calling the tool (e.g., "Resolving program for user's fraud-rate question"). Never include PII (names, emails, phone numbers) or sensitive personal data in `reason` — describe the analytical intent, not personal details about the user. DV uses it for analytics and reasoning capture; it is not forwarded to upstream services and does not affect tool behavior. Omitting `reason` is allowed but discouraged.
