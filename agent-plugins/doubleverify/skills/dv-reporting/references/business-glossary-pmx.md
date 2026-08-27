# DV Proprietary Media Gardens (PMG) Metrics — PMX for PMG

> DV metric definitions, descriptions, and rate calculations for PMX across PMG platforms.

---

| Measure | Supported Platforms | Description | Rate Calculation |
|---|---|---|---|
| PMX Active Ads⁴ | Netflix, Pinterest, Snapchat, TikTok, X | Count of ads where the PMX service was active. | |
| PMX Authentic Passed Impressions⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | Total Net PMX Measured Impressions meeting PMX standard and also Authentic Impressions. | |
| PMX Authentic Passed Rate⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | Percentage meeting PMX standard and Authentic. | PMX Authentic Passed / Total Net PMX Measured |
| PMX Display Active Ads⁴ | Meta | Count of display ads where PMX service was active. | |
| PMX Display Authentic Passed Impressions⁴ | Meta | Total Net PMX Display Measured meeting PMX standard and Authentic. | |
| Total Net PMX Active Ads⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | Count of non-SIVT ads where PMX service was active. | |
| Total Net PMX Eligible Impressions⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | PMX Active Ads with potential to be measured against PMX standard. | |
| Total Net PMX Measured Impressions⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | Eligible impressions where DV successfully measured the ad. | |
| Total Net PMX Measurement Rate⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | Percentage of eligible impressions successfully measured. | Total Net PMX Measured / Total Net PMX Eligible |
| Total Net PMX Passed Impressions⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | Measured impressions meeting PMX standard requirements. | |
| Total Net PMX Passed Rate⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | Percentage of measured impressions meeting PMX standard. | Total Net PMX Passed / Total Net PMX Measured |
| Total Net PMX Failed Impressions⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | Measured impressions not meeting PMX standard. | |
| Total Net PMX Failed Rate⁴ | Netflix, Pinterest, Reddit, Roblox, Spotify, Snapchat, TikTok, X | Percentage of measured impressions failing PMX standard. | Total Net PMX Failed / Total Net PMX Measured |
| Brand Suitability and Total Net PMX Measured Impressions⁴ | Pinterest, Snapchat, TikTok, Reddit | Impressions with both Suitability and Viewability services enabled and PMX Eligible. | |

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
