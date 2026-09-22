# dv-feedback

Send feedback about the plugin, the data, or a specific result straight to the
DV team from the chat.

It fires on exactly two triggers, never on its own initiative:

1. **Explicit request.** The user asks directly, for example "send this to DV", "log a bug" or "tell the team that...".
2. **Offered and accepted.** The user expresses clear sentiment about the plugin, the data or a tool's behavior, the skill offers once to log it, and the user accepts. A decline is not re-offered for the same topic in the same session, and sentiment unrelated to DV's plugin, data or tools never triggers the offer.

Before anything is sent, the skill redacts email addresses, phone numbers,
physical addresses, national IDs, dates of birth, full names of non-public
individuals, credentials and tokens, medical or health information, financial
account numbers and non-DV proprietary business data. DV product names,
campaign, advertiser and program names and the user's own DV account context
are preserved. The redaction is shown to the user for confirmation before
sending and cannot be overridden; if the user insists on including personal
data, the skill explains that DV does not accept it through this channel and
asks them to rephrase. If nothing meaningful survives redaction, the skill says
the feedback could not be sent rather than submitting a gutted message.

Submitted feedback is recorded in DV's analytics logs only. It is not forwarded
to any ticketing system, upstream system or email, no confirmation or ticket ID
is generated, and the DV team reads it periodically in aggregate, so there is no
guarantee of an individual response.

Tools used: `submit-feedback`.

---

See the [plugin reference](../../README.md) for setup, the `dv-mcp` tool reference and data handling.
