# DV Proprietary Media Gardens (PMG) Metrics — Netflix

> DV metric definitions, descriptions, and rate calculations for Netflix.

---

## Netflix Disclosures

**Play Status:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Ads⁴ | Count of all rendered and served ads before GIVT is removed. | |
| Net Ads⁴ | Count of ads where GIVT has been removed. | |
| Total Net Ads⁴ | Count of ads on valid traffic only. | |
| Auto-Play Impressions⁴ | Video impressions that initiate play without user interaction. | |
| Click-to-Play Impressions⁴ | Video impressions initiated by user interaction. | |
| Unknown Play Impressions⁴ | Video impressions where play status could not be determined. | |

**Invalid Traffic Details:**

| Measure | Description | Rate Calculation |
|---|---|---|
| GIVT Ads⁴ | Deduplicated count of ads identified as GIVT. | |
| GIVT Rate⁴ | Percentage of GIVT Ads over Gross Ads. | GIVT Ads / Gross Ads |
| Fraud/SIVT Incidents⁴ | Count of Monitored Ads with Fraud/SIVT incidents. | |
| Fraud/SIVT Incident Rate⁴ | Percentage of Monitored Ads with Fraud/SIVT incidents. | Fraud/SIVT Incidents / Monitored Ads |

## Netflix Viewability

| Measure | Description | Rate Calculation |
|---|---|---|
| 100% Viewable Impressions⁴ | Count of impressions where 100% of creative was in viewport for at least 2 continuous seconds. | |
| 100% Viewable Rate⁴ | Percentage of measured impressions meeting 100% viewable standard. | 100% Viewable Impressions / Measured Impressions |
| Audible and In-View on Completion Impressions⁴ | Impressions where 50%+ was in view and audio enabled at video completion. | |
| Audible Impressions⁴ | Impressions with audio turned on for any duration. | |
| Authentic Ads⁴ | Impressions served in a brand suitable environment, free from fraud/SIVT. | Authentic Ads / Monitored Ads² |
| Authentic Viewable Impressions⁴ | Impressions identified as Authentic and meeting IAB video viewability standard. | |
| Completed Impressions⁴ | Impressions that completed all quartiles. | |
| Q1/Q2/Q3 Completed Impressions⁴ | Impressions that completed the respective quartile. | |
| Q1/Q2/Q3/Q4 Completed and Viewable Impressions⁴ | Video impressions completing the respective quartile and IAB Viewable. | |
| Viewable Impressions⁴ | Impressions measured as viewable per IAB guidelines. | |
| Viewable Rate⁴ | Percentage of measured impressions that were viewable. | Viewable Impressions / Measured Impressions |

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
