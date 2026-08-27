# DV Proprietary Media Gardens (PMG) Metrics — Reddit

> DV metric definitions, descriptions, and rate calculations for Reddit.

---

## Reddit Brand Suitability

| Measure | Description | Rate Calculation |
|---|---|---|
| Authentic Ads⁴ | Deduplicated count of ads that were brand suitable, free from fraud/SIVT, and in targeted geographic region. | |
| Authentic Rate⁴ | Percentage of impressions meeting Authentic criteria. | Authentic Ads / Brand Suitability Measured Ads |
| Authentic Viewable Impressions⁴ | Impressions identified as Authentic and meeting IAB viewability standard. | |
| Authentic Viewable Rate⁴ | Percentage meeting Authentic and viewability criteria. | Authentic Viewable Impressions / Brand Suitability and Viewability Measured Impressions |
| Brand Risk Floor Free Ads⁴ | Ads served adjacent to content not in Brand Risk Floor. | |
| Brand Suitability Incidents⁴ | Count of measured ads adjacent to unsuitable posts. | |
| Brand Suitability Incident Rate⁴ | Percentage of measured ads with suitability incidents. | Brand Suitability Incidents / Brand Suitability Measured Ads |
| Brand Suitable Ads⁴ | Measured ads not adjacent to unsuitable posts. | |
| Brand Suitable Rate⁴ | Percentage of ads not matching Unsuitable Categories. | Brand Suitable Ads / Brand Suitability Measured Ads |
| UC Incidents⁴ | Count of measured ads triggering UC Incidents. | |
| Unique Incidents⁴ | Deduplicated count of Brand Suitability, Fraud/SIVT and Geo incidents. | |

## Reddit Disclosures (Invalid Traffic Details)

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Impressions⁴ | All rendered and served ads before GIVT removal. | |
| GIVT Impressions⁴ | Deduplicated count of impressions identified as GIVT. | |
| GIVT Rate⁴ | Percentage of GIVT over Gross Impressions. | GIVT Impressions / Gross Impressions |
| Net Impressions⁴ | Impressions with GIVT removed. Also represents Monitored Ads. | |
| Fraud/SIVT Incidents⁴ | Deduplicated count of fraud/SIVT incidents. | |
| Fraud/SIVT Incident Rate⁴ | Percentage of Monitored Ads with Fraud/SIVT incidents. | Fraud/SIVT Incidents / Monitored Ads |
| Total Net Impressions⁴ | Impressions on valid traffic only. | |

## Reddit Viewability

| Measure | Description | Rate Calculation |
|---|---|---|
| 100% Viewable Impressions⁴ | Count of valid impressions where ad surface was 100% on-screen. | |
| Display Viewable Impressions⁴ | Impressions where at least 50% was in-view for at least 1 continuous second. | |
| Video Viewable Impressions⁴ | Impressions where ad played for at least 2 continuous seconds with 50%+ visible. | |
| Viewable Impressions⁴ | Impressions measured as viewable per IAB guidelines. | Viewable Impressions / Viewability Measured Impressions |
| Audible Impressions⁴ | Impressions with audio turned on. | |
| In Geo Ads⁴ | Ads served within targeted geographic area. | |
| In Geo Rate⁴ | Percentage of monitored impressions in targeted geography. | In Geo Ads / Monitored Ads |
| Out of Geo Incidents⁴ | Ads served outside designated geographic targeting area. | |
| Reddit Standard Ads⁴ | Number of times ads were shown on Reddit, excluding invalid traffic. Reddit's billable ads for Brand Awareness and Reach. | |

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
