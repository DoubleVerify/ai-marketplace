# DV Proprietary Media Gardens (PMG) Metrics — X (Twitter)

> DV metric definitions, descriptions, and rate calculations for X (Twitter).

---

## X Brand Suitability

| Measure | Description | Rate Calculation |
|---|---|---|
| Authentic Ads®¹³'¹⁵ | Count of ads monitored for fraud/SIVT and brand suitability that meet Authentic Ads criteria. | |
| Authentic Rate¹³'¹⁵ | Percentage of ads meeting Authentic Ads criteria. | Authentic Ads / Brand Suitability Measured Ads |
| Authentic Viewable Impressions¹⁴'¹⁵ | Authentic impressions meeting IAB viewability standards. | |
| Authentic Viewable Rate¹⁵ | Percentage meeting Authentic and viewability criteria. | Authentic Viewable Impressions / Brand Suitability and Viewability Measured Impressions |
| Brand Risk Floor Free Ads | Ads served adjacent to content not in Brand Risk Floor. | |
| Brand Suitability Incidents | Measured ads adjacent to unsuitable tweets. | |
| Brand Suitability Incident Rate | Percentage of measured ads with suitability incidents. | Brand Suitability Incidents / Brand Suitability Measured Ads |
| Brand Suitable Ads | Measured ads not adjacent to unsuitable tweets. | |
| Brand Suitable Rate | Percentage of ads not triggering suitability incidents. | Brand Suitable Ads / Brand Suitability Measured Ads |
| UC Incidents | Measured ads triggering UC Incidents. | |
| UC Incident Rate | Percentage of measured ads with UC Incidents. | UC Incidents / Brand Suitability Measured Ads |
| Unique Incidents | Deduplicated count of Brand Suitability and Fraud/SIVT incidents. | |

## X Disclosures (Invalid Traffic Details)

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Ads⁴ | All ads before GIVT removal. | |
| GIVT Ads⁴ | Deduplicated count of GIVT ads. | |
| GIVT Rate⁴ | Percentage of Gross Ads identified as GIVT. | GIVT Ads / Gross Ads |
| Net Ads⁴ | Ads with GIVT removed. Also represents Monitored Ads. | |
| Fraud/SIVT Incidents⁴ | Deduplicated count of all fraud/SIVT types. | |
| Fraud/SIVT Incident Rate⁴ | Percentage of Monitored Ads with Fraud/SIVT. | Fraud/SIVT Incidents / Monitored Ads |
| Total Net Ads⁴ | Ads on valid traffic only. | |

## X Viewability

| Measure | Description | Rate Calculation |
|---|---|---|
| 100% Viewable Impressions | Impressions where 100% of creative was in viewport (Display: 1s, Video: 2s). | |
| 100% Viewable Rate | Percentage meeting 100% viewable standard. | 100% Viewable Impressions / Measured Impressions |
| 2-Second Display Viewable Impressions | Display impressions with 50%+ in view for 2 continuous seconds. | |
| 3-Second Display Viewable Impressions | Display impressions with 50%+ in view for 3 continuous seconds. | |
| Audible and In-View on Completion (AVOC) Impressions | Impressions with 50%+ in view and audio on at video completion. | |
| Audible Impressions | Impressions with audio turned on. | |
| Audible Viewable Impressions | Viewable impressions with audio on. | |
| Audible and 100% In-View for Half Duration Impressions | Impressions audible while ad surface was 100% on-screen for at least half the time. | |
| X Viewable Impressions | Impressions viewable per IAB guidelines. | |
| X Viewable Rate | Percentage of impressions viewable per IAB guidelines. | X Viewable Impressions / Measured Impressions |
| Valid 100% Viewable Impressions | Valid impressions where ad surface was 100% on-screen. | |
| Valid Viewable Impressions | Valid impressions viewable under MRC standard. | |
| Video Full Screen Impressions | Impressions where ad was expanded to full screen in X app. | |
| Video Full Screen Rate | Percentage of impressions expanded to full screen. | Video Full Screen Impressions / Video Measured Impressions |
| Average Time (s) - Display Authentic Viewable Impressions | Average time of viewable display impressions that were brand suitable and fraud/SIVT free. | |
| Average Time (s) - Display Viewable Impressions | Average time, in seconds, of viewable impressions. | |
| Total Time (hr) - Display Authentic Viewable Impressions | Total brand exposure duration for viewable, brand suitable, fraud/SIVT free impressions. | |

**Note:** X does not offer Geo solutions.

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
13. **Authentic Impressions** are calculated on only the impressions where brand suitability is measured, which requires the activation of the Brand Suitability service directly on the social platform in supported regions.
14. Some platforms, such as X, do not offer Geo solutions and are therefore not included in the measurement.
15. **Brand Suitability availability:** Brand Suitability is available globally across 30+ countries for TikTok and six countries for X. Authentic Ads and Authentic Viewable Impressions are only available in those countries.
