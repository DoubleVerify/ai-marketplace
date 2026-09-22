# dv-program-context

Identifies which DV account to pull from — ask about any program without
configuring anything.

It resolves which DV **program**, the account that scopes a user's data, the
current chat should operate against, and keeps the `dv-mcp` connection working.
Any skill that calls a `dv-mcp` tool requiring a `program_id` delegates here
first, so this skill is infrastructure other skills build on rather than
something a user invokes directly.

It keeps three layers separate on purpose:

| Layer | Meaning | Source |
|---|---|---|
| **Program** | Access container, supplying `program_id` and `timezone` | `list-my-programs` |
| **Platform / channel** | Measurement domain such as YouTube or Meta, supplying `datamart_id` | `datamart-routing.md`, used by `dv-reporting` |
| **Campaign** | Ad entity inside a program | Query results |

A program's name can coincidentally match a platform word, such as a program
literally named "Youtube". The skill never infers program selection from
platform wording, and never selects a program on a name match alone unless the
user explicitly chose it.

Behavior:

1. If the user has already named a program this chat, resolve it via `list-my-programs` and reuse it for the rest of the chat.
2. Otherwise call `list-my-programs`, auto-selecting if there is exactly one, asking the user to choose among multiple, or stopping if there are none.
3. Never fabricates a `program_id`. The only valid sources are a fresh `list-my-programs` call in this chat, or an ID pasted verbatim by the user.
4. Echoes the selected program name in chat output before showing any tool results, so a mismatch is visible immediately.
5. Selection does not persist across chats. It is re-resolved at the start of every new one.

On Claude Code only, if `list-my-programs` is unavailable the skill can register
the bundled `dv-mcp` server automatically. It reads the plugin's bundled
`.mcp.json`, writes the `dv-mcp` entry into the project's `.mcp.json` or the
user's `~/.claude.json`, merging with rather than overwriting any existing
`mcpServers` entries, then asks the user to restart. Cursor never
auto-configures, because `.cursor-plugin/plugin.json` already declares the
server; if the tool is missing there, the fix is reloading the window or
reinstalling the plugin. The full config spec is in
[`references/dv-mcp-setup.md`](references/dv-mcp-setup.md).

Tools used: `list-my-programs`.

See the [plugin reference](../../README.md) for setup, the `dv-mcp` tool reference and data handling.
