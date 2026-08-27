# DV Proprietary Media Gardens (PMG) Metrics — Pinterest

> DV metric definitions, descriptions, and rate calculations for Pinterest.

---

## Pinterest Brand Suitability

| Measure | Description | Rate Calculation |
|---|---|---|
| Pinterest Standard Authentic Ads⁴ | Deduplicated count of Pinterest Standard ads that were brand suitable and free from fraud/SIVT. | |
| Pinterest Standard Authentic Rate⁴ | Percentage of Pinterest Standard ads meeting Authentic criteria. | Pinterest Standard Authentic Ads / Brand Suitability Measured Ads |
| Pinterest Standard Authentic Viewable Impressions⁴ | Pinterest Standard impressions identified as Authentic and meeting Pinterest Standard and IAB viewability. | |
| Brand Risk Floor Free Ads⁴ | Ads served on content not assigned a Brand Risk Floor category. | |
| Brand Risk Floor Free Rate⁴ | Percentage of ads not in Brand Risk Floor. | Brand Risk Floor Free Ads / Brand Suitability Measured Ads |
| Brand Suitability Incidents⁴ | Count of measured ads adjacent to unsuitable pins. | |
| Brand Suitability Incident Rate⁴ | Percentage of measured ads with suitability incidents. | Brand Suitability Incidents / Brand Suitability Measured Ads |
| Brand Suitability Measured Ads⁴ | Count of ads where DV could determine brand suitability. | |
| Brand Suitable Ads⁴ | Measured ads not adjacent to unsuitable pins. | |
| Brand Suitable Rate⁴ | Percentage of ads where pin classification doesn't match Unsuitable Categories. | Brand Suitable Ads / Brand Suitability Measured Ads |
| UC Incidents⁴ | Count of measured ads triggering UC Incidents. | |
| UC Incident Rate⁴ | Percentage of measured ads with UC Incidents. | UC Incidents / Brand Suitability Measured Ads |
| Unique Incidents⁴ | Deduplicated count of Brand Suitability and Fraud/SIVT incidents. | |
| Unique Incident Rate⁴ | Percentage of measured ads with at least one incident. | Unique Incidents / Brand Suitability Measured Ads |

## Pinterest Disclosures (Invalid Traffic Details)

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Ads⁴ | All rendered and served ads before GIVT removal. | |
| GIVT Ads⁴ | Deduplicated count of ads identified as GIVT. | |
| GIVT Rate⁴ | Percentage of GIVT Ads over Gross Ads. | GIVT Ads / Gross Ads |
| Net Ads⁴ | Count of ads with GIVT removed. Also represents Monitored Ads. | |
| Pinterest Standard Fraud/SIVT Incidents⁴ | Deduplicated count of fraud/SIVT incidents. | |
| Pinterest Standard Fraud/SIVT Incident Rate⁴ | Percentage of Pinterest Standard Impressions with Fraud/SIVT incidents. | Fraud/SIVT Incidents / Pinterest Standard Impressions |
| Total Net Ads⁴ | Ads on valid traffic only. | |

## Pinterest Viewability

| Measure | Description | Rate Calculation |
|---|---|---|
| Pinterest Standard Impressions⁴ | Display: Measured Display Impressions with at least 1 pixel in view for 1 continuous second. Video: Measured Video Impressions with at least 1 pixel in view for 1 continuous second while playing. | |
| Pinterest Standard Viewable Impressions⁴ | Pinterest Standard Impressions viewable per IAB guidelines (Display: 50%/1s, Video: 50%/2s). | |
| Pinterest Standard Viewable Rate | Percentage of Pinterest Standard Impressions that were IAB viewable. | Pinterest Standard Viewable Impressions / Pinterest Standard Impressions |
| Pinterest Standard Audible Impressions⁴ | Pinterest Standard Audible Measured impressions with audio turned on. | |
| Pinterest Standard Audible and In-View on Completion Impressions⁴ | Impressions where 50%+ was in view with audio on at video completion. | |
| Pinterest Standard 100% Viewable Impressions⁴ | Impressions where 100% of creative was in viewport (Video: 2s, Display: 1s). | |
| Pinterest Standard Passthrough Impressions⁴ | Impressions where top and bottom of ad appeared on screen while scrolling. | |
| Pinterest Standard Completed Impressions⁴ | Impressions that completed all quartiles. | |
| Pinterest Standard Q1/Q2/Q3 Completed Impressions⁴ | Impressions completing the respective quartile. | |

**Note:** Pinterest videos do not play with 'sound on' on web, so audibility metrics are not available for video on web environments.

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
