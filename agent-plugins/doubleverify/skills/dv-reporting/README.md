# dv-reporting

Ask natural-language questions about your DV campaign data — performance, brand
suitability, fraud, viewability, and more.

This is the required entry point for any DV data question. It must be loaded
before any `dv-mcp` tool is called. It covers campaign performance, brand
suitability, fraud/SIVT, viewability, geo-compliance, blocking/filtering and
DV Authentic Attention metrics.

How it works:

1. **Resolve program context.** Delegates to [`dv-program-context`](../dv-program-context/README.md) at the start of every session, and never asks the user to do this manually.
2. **Load channel guidance.** Reads the relevant best-practices, threshold and caveat reference files before building a query. Open Web and Social have different rule sets; Social has no approved benchmarks and is never compared threshold-to-threshold.
3. **Route to a datamart.** Maps the question to a `datamart_id`, then loads the matching business glossary (one file per platform) for metric and dimension definitions and co-requisite rules.
4. **Discover fields.** Calls `get-datapoint-catalog` for the exact field names the datamart supports, and never invents a field or ID.
5. **Construct the query.** Applies co-requisite rules, a default volume floor of 100K Monitored Ads per day scaled to the date range, a default 7-day window and a 100-row limit.
6. **Run the query** via `run-query`, passing `program_id`, the resolved fields, filters and sorts, the timezone and a `reason`.
7. **Interpret results.** Flags anomalies against thresholds on Open Web only, identifies likely sources of issues, and surfaces optional next steps framed as options rather than directives.

Guardrails:

- **Never fabricates** a datamart ID, field name or data point. Anything not in the catalog is reported as unavailable.
- **Program isolation is absolute.** Switching programs clears all prior findings; cross-program comparison in one session is not supported.
- **No cross-platform performance comparisons on Social.** The same metric can mean structurally different things on different platforms, so a rate difference between Meta and TikTok is never presented as one outperforming the other.
- **Rates are never summed** across rows. Only underlying counts are additive.
- **Exact DV terminology only**, for example "Fraud/SIVT Incident Rate" rather than "Fraud Rate", with no internal file, skill or plugin names in chat output.
- **Not professional advice.** Every interpretation is informational, never a guaranteed outcome or a directive.

Reference files under [`references/`](references/):

| File | Purpose |
|---|---|
| `datamart-routing.md` | Maps user intent to a `datamart_id` |
| `business-glossary-*.md` | Per-platform metric and dimension definitions and co-requisite rules (Open Web, YouTube, Meta, TikTok, X, Snapchat, Pinterest, Reddit, Netflix, Instacart, LinkedIn, Spotify, Roblox, GroupM, PMX) |
| `thresholds.md` | Normal ranges and investigation triggers, Open Web only |
| `reporting-optimization-best-practices.md` | Domain-specific recommendations for brand suitability, viewability, geo and fraud/SIVT, Open Web only |
| `inline-caveats.md` | Rules for hedging interpretive language, with no definitive diagnoses or directives |
| `SOCIAL.md` | Core rules for Social platforms, with no cross-platform benchmarking and no severity language on rate changes |
| `measurement-domains.md` | Overview of DV's four core measurement domains |
| `report-templates.md` | Pre-built dimension and metric combinations by platform |

Tools used: `list-my-programs`, `get-datapoint-catalog`, `run-query`.

See the [plugin reference](../../README.md) for setup, the `dv-mcp` tool reference and data handling.
