# DV Proprietary Media Gardens (PMG) Metrics — GroupM for PMG

> DV metric definitions, descriptions, and rate calculations for GroupM across PMG platforms.

---

GroupM metrics are available across multiple PMG platforms. The consolidated GroupM metrics encompass different versions per platform (V4 for Display, Native/Reach Extension for Video).

| Measure | Supported Platforms | Description | Rate Calculation |
|---|---|---|---|
| GroupM Active Ads⁴ | Netflix, Pinterest, Reddit, Roblox, Snapchat, Spotify, TikTok, X | Ads for GroupM agencies on which the GroupM standard service is active and GIVT removed. | |
| GroupM Billable Impressions⁴ | YouTube | Sum of GroupM Passed and Projected Impressions. | |
| GroupM Display Active Ads⁴ | Meta | Display ads with GroupM standard service active and GIVT removed. | |
| GroupM Display Measured Impressions⁴ | Meta, Reddit, Pinterest, Snapchat, X | Display Eligible Impressions successfully measured against GroupM standard. | |
| GroupM Eligible Impressions⁴ | Netflix, Pinterest, Reddit, Roblox, Snapchat, Spotify, TikTok, X | GroupM Active, non-SIVT impressions with potential to be measured. | |
| GroupM Failed Impressions⁴ | Netflix, Reddit, Roblox, Snapchat, Spotify, TikTok, X | Measured Impressions not meeting GroupM standard. | |
| GroupM Failed Rate⁴ | Netflix, Reddit, Roblox, Snapchat, Spotify, TikTok, X | Percentage of measured impressions failing GroupM standard. | GroupM Failed / GroupM Measured |
| GroupM Fraud/SIVT Incidents⁴ | Netflix, Pinterest, Reddit, Roblox, Snapchat, Spotify, TikTok, X | Count of GroupM Active Ads identified as fraudulent/SIVT. | |
| GroupM Measured Impressions⁴ | Netflix, Pinterest, Reddit, Roblox, Snapchat, Spotify, TikTok, X | Eligible Impressions successfully measured against GroupM standard. | |
| GroupM Measurement Rate⁴ | Netflix, Pinterest, Reddit, Roblox, Snapchat, Spotify, TikTok, X | Percentage of eligible impressions successfully measured. | GroupM Measured / GroupM Eligible |
| GroupM Passed Impressions⁴ | Netflix, Reddit, Roblox, Snapchat, Spotify, TikTok, X | Measured Impressions determined SIVT-free and passing GroupM standard. | |
| GroupM Passed Rate⁴ | Netflix, Reddit, Roblox, Snapchat, Spotify, TikTok, X | Percentage of measured impressions passing GroupM standard. | GroupM Passed / GroupM Measured |
| GroupM V3 Display Passed/Failed Impressions⁴ | Meta, Netflix, Pinterest, Reddit, Roblox, Snapchat, X | Display impressions meeting/failing GroupM 3.0 Display standard. | |
| GroupM V4 Display Passed/Failed Impressions⁴ | Meta, Reddit, Roblox, Snapchat, X | Display impressions meeting/failing GroupM 4.0 Display standard. | |
| GroupM Video Native Passed/Failed Impressions⁴ | Pinterest, Reddit, Roblox, Snapchat, Spotify, X | Video impressions meeting/failing GroupM Video Native standard. | |
| GroupM Video Passed and Completed Impressions⁴ | Netflix, Roblox, Snapchat, Spotify, TikTok, YouTube | Video impressions passing GroupM standard and playing to end. | |
| GroupM Video Reach Extension Passed/Failed Impressions⁴ | Pinterest, Roblox, Snapchat, Spotify | Video impressions meeting/failing GroupM Video Reach Extension standard. | |
| GroupM Video TrueView Measured/Viewable Impressions⁴ | YouTube | Video impressions measured/passing GroupM TrueView standard. | |

---

## Co-requisite & Compatibility Rules

Platform-specific datamarts generally have fewer field restrictions than the Open Web Standard datamart. However:

1. **UC-family dimensions** (UC Category Name, UC Risk Tier) are only available in platform-specific Brand Suitability datamarts (e.g., YouTube Video Incident Reporting, Meta Brand Suitability) — not in the general platform datamart.
2. **Always discover fields via `get-datapoint-catalog`** before constructing queries. The catalog for each datamart is authoritative for what fields are available and compatible.
3. **Category and Risk Tier dimensions** follow the same co-requisite rules as Open Web: Risk Tier requires Category Name.

For detailed compatibility rules, refer to the Open Web glossary (`business-glossary-openweb.md`) which documents the full restriction patterns. Platform datamarts follow the same general principles with fewer available dimension/metric combinations.

---

## Common Endnotes

4. **Not MRC Accredited.** These metrics and methodologies have not been accredited by the Media Rating Council (MRC).
