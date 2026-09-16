---
name: dv-feedback
description: >
  Record user-volunteered feedback about the DV agent plugin into DV's
  analytics logs. Use whenever the user explicitly asks to leave feedback
  ("send feedback to DV", "log a bug", "tell the team that ..."), or when
  the user expresses clear sentiment about the plugin/data/tools (praise,
  frustration, bug report, data-quality complaint) and accepts an offer
  to log it.
---

# DV Feedback

The `dv-mcp` MCP server exposes a `submit-feedback` tool that writes
user-volunteered feedback into DV's analytics logs. This skill governs
when and how to call it.

(The one-line nudge that advertises this tool to users lives in
`dv-reporting/SKILL.md` Step 0. The legal disclaimer, by contrast, is
gated at the start of *every* DV skill — see Step 0 below — so it shows
regardless of which skill a session enters through.)

## Step 0: Legal Disclaimer (session-scoped, show once)

<!-- DISCLAIMER-INLINE:BEGIN -->
If the disclaimer was already shown this session by **any** DV skill, skip this step. Otherwise, before ANY other output, print the following **verbatim** -- same wording, punctuation, and curly quotes. The gate is session-scoped, not per-skill.

**Beta:** This feature is still being developed. Outputs should be reviewed before use in production decisions. Your feedback during this period directly shapes what ships next.

> **Disclaimer:** This tool provides AI-generated analysis and insights based on DoubleVerify (“DV”) measurement data and methodologies. Outputs are provided for informational purposes only and do not constitute legal, professional, or business advice. AI-generated responses may be incomplete, inaccurate, or based on partial or evolving data and should not be relied upon as the sole basis for decision-making. Users are responsible for independently validating all results against official DV reporting, including the DV Pinnacle dashboard. In the event of any inconsistency between AI-generated output and official DV reporting, the official DV reporting controls. By using this tool, you acknowledge and consent to the use of AI-enabled technologies, including third-party large language model providers, in connection with the functionality of this feature. DV is not responsible for the availability, performance, security, or outputs of third-party AI systems. DV makes no warranties, express or implied, regarding the accuracy, completeness, reliability, or timeliness of the tool, underlying data, or any AI-generated output, and disclaims all implied warranties to the maximum extent permitted by law. All DV data, reporting, and related materials remain subject to the applicable agreement(s) between you and DV, in addition to these terms and any applicable product documentation. Please contact your DV support team for official reporting inquiries. By using this tool, you acknowledge that DV may collect and use usage data, prompts, inputs, outputs, interaction logs, and related technical metadata to operate, secure, support, and improve the functionality and performance of the tool and related DV services. Such data will be handled in accordance with DV’s privacy and data handling policies. Your data will not be shared with third-party advertisers or used for advertising purposes. Users should not submit confidential, regulated, personal, or sensitive information unless expressly permitted under the applicable agreement and product documentation.
<!-- DISCLAIMER-INLINE:END -->

## Prerequisites

`submit-feedback` is provided by `dv-mcp`. If the server is not reachable
(any `dv-mcp` tool call fails), do not invent a recording mechanism. Tell
the user the DV MCP server is not reachable and stop. Do not retry.

## When to call `submit-feedback`

Call the tool in **exactly two** situations:

1. **Explicit request.** The user asks to leave feedback — e.g. "send
   this to DV", "log a complaint", "tell the team that ...".

2. **Offered and accepted.** The user expresses clear, unambiguous
   sentiment **about the plugin, the data, or a tool's behavior** —
   praise, frustration, a bug report, a data-quality complaint — and
   you offer to log it and they accept.

   - Offer once. Ask one short question: *"Want me to log that to the
     DV team?"*
   - If the user declines or ignores it, do not re-offer for the same
     topic in the same session.
   - Do not offer for sentiment that is not about the plugin/data/tools
     (e.g. "I hate Mondays" is not a trigger).
   - Do not offer in the middle of a long answer; offer at the end, as
     a single short follow-up line.

**Do not call the tool on your own initiative** to summarize a session,
log a thank-you, or cap off a conversation. Both paths above require an
affirmative user signal.

## How to call `submit-feedback`

- Pass the user's text in the `feedback` argument, preserving their
  wording as closely as possible — but **first redact any PII or
  sensitive data** that is not related to DV products or services:
  - **Redact:** email addresses, phone numbers, physical addresses,
    Social Security / national ID numbers, dates of birth, full names
    of non-public individuals, passwords, API keys, tokens, medical
    or health information, financial account numbers, and proprietary
    non-DV business data.
  - **Keep:** DV product names, campaign names, advertiser names,
    program names, the user's own DV account context, and any
    information about DV tools, data, or services.
  - Replace each redacted item with `[REDACTED]`.
  - If you redact anything, show the user the redacted version and
    ask them to confirm before sending. Explain that personal or
    sensitive data was removed to protect their privacy.
  - **Redaction cannot be overridden.** If the user insists on
    including PII, explain that DV does not accept personal data
    through this channel and ask them to rephrase.
  - If nothing meaningful remains after redaction, tell the user the
    feedback could not be sent and ask them to rephrase focusing on
    the DV product or service feedback.
- For `category` and `sentiment`: **omit them when unsure**. An absent
  value is more useful than a wrong one. Use them only when the user's
  framing is unambiguous (e.g. "this is a bug" → `category: bug`;
  explicit thanks → `sentiment: positive`).
- Set `reason` to one short sentence describing why you are calling the
  tool (e.g. "User explicitly asked to log a data-quality complaint",
  "User accepted offer to log positive sentiment"). Never include PII
  (names, emails, phone numbers) or sensitive personal data in `reason`.
  Describe the intent, not the person.
- After the tool returns, tell the user their feedback has been
  recorded for DV review and that no ticket or response will follow.
  Do not invent a ticket id.

## What feedback is and is not

- Feedback is recorded in DV's analytics logs. It is not forwarded to
  any upstream system, ticketing system, or email.
- The user does not receive a confirmation email.
- The DV team reads aggregated feedback periodically; there is no
  guarantee of an individual response.
