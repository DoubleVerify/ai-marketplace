# DV Proprietary Media Gardens (PMG) Metrics — LinkedIn

> DV metric definitions, descriptions, and rate calculations for LinkedIn.

---

## LinkedIn Disclosures (Invalid Traffic Details)

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Ads⁴ | All rendered and served ads before GIVT is removed. | |
| GIVT Ads⁴ | Deduplicated count of ads identified as General Invalid Traffic. | |
| GIVT Rate⁴ | The percentage of GIVT Ads over Gross Ads. | GIVT Ads / Gross Ads |
| Net Ads⁴ | Count of ads where GIVT Ads have been removed. Also represents Monitored Ads. | |
| Fraud/SIVT Incidents⁴ | Unique deduplicated count of fraud/SIVT incidents. | |
| Fraud/SIVT Incident Rate⁴ | The percentage of Monitored Ads with any form of Fraud or SIVT incidents. | Fraud/SIVT Incidents / Monitored Ads |
| Total Net Ads⁴ | Count of ads on only valid traffic (GIVT and Fraud/SIVT removed). | |

## LinkedIn Viewability

| Measure | Description | Rate Calculation |
|---|---|---|
| 100% Viewable Impressions⁴ | Count of impressions where 100% of the creative was in the viewport for at least 2 continuous seconds (video) or 1 second (display). | |
| 100% Viewable Rate⁴ | Percentage of measured impressions meeting the 100% viewable standard. | 100% Viewable Impressions / Viewability Measured Impressions |
| Audible Impressions⁴ | Count of impressions where audio was turned on for any time duration. | |
| Audible Rate⁴ | Percentage of impressions with audio turned on. | Audible Impressions / Audible Measured Impressions |
| Audible and In-View on Completion Impressions⁴ | Count of impressions where 50%+ creative was in view and audio enabled at video completion. | |
| Audible and In-View on Completion Rate⁴ | Percentage of impressions meeting AVOC criteria. | AVOC Impressions / Audible Viewable Measured Impressions |
| Authentic Ads⁴ | Impressions free from fraud/SIVT served in a high-quality environment. | |
| Authentic Rate⁴ | Percentage of ads meeting Authentic Ads criteria. | Authentic Ads / Monitored Ads² |
| Authentic Viewable Impressions⁴ | Count of Authentic impressions meeting IAB viewability standards. | |
| Authentic Viewable Rate⁴ | Percentage of Authentic impressions meeting IAB viewability standards. | Authentic Viewable Impressions / Viewability Measured Impressions |
| Viewable Impressions⁴ | Impressions measured as viewable per IAB guidelines. | |
| Viewable Rate⁴ | Percentage of measured impressions that were viewable. | Viewable Impressions / Viewability Measured Impressions |

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
