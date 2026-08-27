# DV Proprietary Media Gardens (PMG) Metrics — Spotify

> DV metric definitions, descriptions, and rate calculations for Spotify.

---

## Spotify Disclosures (Invalid Traffic Details)

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Ads⁴ | All ads before GIVT removal. | |
| GIVT Ads⁴ | Deduplicated count of GIVT ads. | |
| GIVT Rate⁴ | Percentage of GIVT over Gross Ads. | GIVT Ads / Gross Ads |
| Net Ads⁴ | Ads with GIVT removed. Also represents Monitored Ads. | |
| Fraud/SIVT Incidents⁴ | Deduplicated count of fraud/SIVT incidents. | |
| Fraud/SIVT Incident Rate⁴ | Percentage of Monitored Ads with Fraud/SIVT. | Fraud/SIVT Incidents / Monitored Ads |
| Total Net Ads⁴ | Ads on valid traffic only. | |

## Spotify Viewability

| Measure | Description | Rate Calculation |
|---|---|---|
| 100% Viewable Impressions⁴ | Impressions where 100% of creative was in viewport (Video: 2s, Display: 1s). | |
| 100% Viewable Rate⁴ | Percentage meeting 100% viewable standard. | 100% Viewable Impressions / Viewability Measured Impressions |
| Audible and In-View on Completion Impressions⁴ | Impressions where 50%+ was in view with audio enabled at video completion. | |
| Audible Impressions⁴ | Impressions with audio turned on. | |
| Audible Rate⁴ | Percentage with audio turned on. | Audible Impressions / Audible Measured Impressions |
| Audible Viewable Impressions⁴ | Viewable impressions with audio on. | |
| Authentic Ads⁴ | Impressions free from fraud/SIVT in a brand-suitable environment. | |
| Authentic Rate⁴ | Percentage meeting Authentic criteria. | Authentic Ads / Monitored Ads² |
| Authentic Viewable Impressions⁴ | Authentic impressions meeting IAB viewability standard. | |
| Authentic Viewable Rate⁴ | Percentage of authentic impressions meeting viewability standard. | Authentic Viewable Impressions / Viewability Measured Impressions |
| Autoplay Impressions⁴ | Video ads that began by autoplay. | |
| Click to Play Impressions⁴ | Video ads that began by user initiation. | |
| Unknown Play Impressions⁴ | Video impressions where play method could not be identified. | |
| Viewable Impressions⁴ | Impressions measured as viewable per IAB guidelines. | |
| Viewable Rate⁴ | Percentage of measured impressions that were viewable. | Viewable Impressions / Viewability Measured Impressions |
| Q1/Q2/Q3 Completed Impressions⁴ | Impressions completing the respective quartile. | |
| Q1/Q2/Q3/Q4 Completed and Viewable Impressions⁴ | Video impressions completing the quartile and IAB Viewable. | |

---

## Co-requisite & Compatibility Rules

Platform-specific datamarts generally have fewer field restrictions than the Open Web Standard datamart. However:

1. **UC-family dimensions** (UC Category Name, UC Risk Tier) are only available in platform-specific Brand Suitability datamarts (e.g., YouTube Video Incident Reporting, Meta Brand Suitability) — not in the general platform datamart.
2. **Always discover fields via `get-datapoint-catalog`** before constructing queries. The catalog for each datamart is authoritative for what fields are available and compatible.
3. **Category and Risk Tier dimensions** follow the same co-requisite rules as Open Web: Risk Tier requires Category Name.

For detailed compatibility rules, refer to the Open Web glossary (`business-glossary-openweb.md`) which documents the full restriction patterns. Platform datamarts follow the same general principles with fewer available dimension/metric combinations.

---

## Common Endnotes

1. **Authentic Ads and Authentic Viewable Impressions** are based on customizable campaign-specific settings; therefore, the services that make up these metrics may differ for each campaign. They are accredited for desktop, mobile web, and mobile app environments when the geographic targeting service is not included.
2. This formula applies only to campaigns using at least one of the following services: **Brand Suitability, IQ Fraud Advanced, or Geo-Targeting**.
3. This formula applies to only campaigns using viewability and one of the following services: **Brand Suitability, Fraud Advanced, Viewability Advanced, or Geo-Targeting**.
4. **Not MRC Accredited.** These metrics and methodologies have not been accredited by the Media Rating Council (MRC).
