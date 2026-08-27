# DV Proprietary Media Gardens (PMG) Metrics — Instacart

> DV metric definitions, descriptions, and rate calculations for Instacart.

---

## Instacart Disclosures (Invalid Traffic Details)

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Ads⁴ | All rendered and served ads before GIVT is removed. A count of ads including those categorized as general invalid traffic, sophisticated invalid traffic, and valid ads. | |
| GIVT Ads⁴ | A total, deduplicated count of ads identified as General Invalid Traffic (GIVT). GIVT is identified by using standardized, industry-wide lists shared across vendors. | |
| GIVT Rate⁴ | The percentage of GIVT Ads over Gross Ads. | GIVT Ads / Gross Ads |
| Net Ads⁴ | A count of ads where GIVT Ads have been removed. Also represents the Monitored Ads count found in all other reports. | |
| Fraud/SIVT Incidents⁴ | The unique deduplicated count of incidents recorded, including bot fraud, site fraud, nonhuman data center traffic, hijacked devices, and injected ads. | |
| Fraud/SIVT Incident Rate⁴ | The percentage of Monitored Ads with any form of Fraud or SIVT incidents. | Fraud/SIVT Incidents / Monitored Ads |
| Total Net Ads⁴ | A count of ads on only valid traffic, i.e., Gross Ads with all types of invalid (GIVT and Fraud/SIVT Ads) traffic removed. | |

## Instacart Viewability

| Measure | Description | Rate Calculation |
|---|---|---|
| 100% Viewable Impressions⁴ | The count of impressions where 100% of the creative was in the viewable portion of a user's device for at least 2 continuous seconds (video) or 1 second (display). | |
| 100% Viewable Rate⁴ | The percentage of viewability measured impressions meeting the 100% viewable standard. | 100% Viewable Impressions / Viewability Measured Impressions |
| 50% Display Viewable 1-5 Secs Impressions⁴ | Impressions for which 50% or more of the ad creative was in view for 1-4.9 seconds. | |
| 50% Display Viewable 1-5 Secs Rate⁴ | The percentage of Display Measured Impressions for which 50% or more was in view for 1-4.9 seconds. | 50% Display Viewable 1-5 Secs Impressions / Viewability Display Measured Impressions |
| Audible Impressions⁴ | The count of impressions where the audio was turned on for any time duration. | |
| Audible Rate⁴ | The percentage of impressions that had audio turned on. | Audible Impressions / Audible Measured Impressions |
| Audible Viewable Impressions⁴ | The count of impressions that are viewable and had audio turned on. | |
| Audible Viewable Rate⁴ | The percentage of impressions that are viewable and had audio turned on. | Audible Viewable Impressions / Audible Viewable Measured Impressions |
| Audible and In-View on Completion Impressions⁴ | The count of impressions where 50% or more of the creative was in view and audio was enabled at the completion of the video. | |
| Audible and In-View on Completion Rate⁴ | The percentage of impressions meeting AVOC criteria. | Audible and In-View on Completion Impressions / Audible Viewable Measured Impressions |
| Authentic Ads⁴ | Impressions free from fraud/SIVT, each DV Authentic Ad® is a distinct ad served in a high-quality environment. | |
| Authentic Rate⁴ | The percentage of ads monitored for fraud/SIVT that meet the criteria for Authentic Ads. | Authentic Ads / Monitored Ads² |
| Authentic Viewable Impressions⁴ | The count of impressions that are identified as authentic and meet the IAB standard for viewability. | |
| Authentic Viewable Rate⁴ | The percentage of impressions that are identified as authentic and meet the IAB standard for viewability. | Authentic Viewable Impressions / Viewability Measured Impressions |
| Completed Impressions⁴ | The count of impressions that completed all quartiles. | |
| Q1/Q2/Q3 Completed Impressions⁴ | The count of impressions that completed the respective quartile. | |
| Q1/Q2/Q3/Q4 Completed and Viewable Impressions⁴ | The count of video impressions that completed the respective quartile and were IAB Viewable. | |
| Viewability Eligible Impressions⁴ | Impressions that had the potential to be measured for viewability. | |
| Viewability Measured Impressions⁴ | Impressions for which DV was able to obtain the information needed to make decisions about viewability. | |
| Viewability Measurement Rate⁴ | The percentage of Measured impressions for which DV was able to make viewability decisions. | Viewability Measured Impressions / Viewability Monitored Impressions |
| Viewable Impressions⁴ | Impressions measured as viewable according to the IAB Viewability Guidelines. | |
| Viewable Rate⁴ | The percentage of measured impressions that were viewable per IAB guidelines. | Viewable Impressions / Viewability Measured Impressions |
| Monitored Ads⁴ | The total count of ads served where DV monitoring services were applied. | |

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
