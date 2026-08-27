# DV Proprietary Media Gardens (PMG) Metrics — YouTube

> DV metric definitions, descriptions, and rate calculations for YouTube.

---

## YouTube Brand Suitability

DV YouTube Brand Suitability provides video-level insight into content suitability. DV offers 47 Brand Suitability categories and three tiers of risk (low, medium, high) across 14 categories.

| Measure | Description | Rate Calculation |
|---|---|---|
| Brand Risk Floor Free Ads⁴ | Ads served adjacent to content not in Brand Risk Floor. | |
| Brand Risk Floor Free Rate⁴ | Percentage of ads not in Brand Risk Floor. | Brand Risk Floor Free Ads / Brand Suitability Measured Ads |
| Brand Risk Floor Incidents⁴ | Ads triggering incidents due to Brand Risk Floor categories. | |
| Brand Risk Floor Incident Rate⁴ | Percentage of ads triggering Brand Risk Floor incidents. | Brand Risk Floor Incidents / Brand Suitability Measured Ads |
| Brand Suitability Incidents⁴ | Impressions triggering incidents based on DV YouTube profile criteria. | |
| Brand Suitability Incident Rate⁴ | Percentage of impressions triggering unsuitable incidents. | Brand Suitability Incidents / Brand Suitability Measured Ads |
| Brand Suitability Measured Ads⁴ | Impressions where DV could determine brand suitability. | |
| Brand Suitability Monitored Ads⁴ | Ads where Brand Suitability services were activated by Google. | |
| Brand Suitability Unmeasured Ads⁴ | Ads where brand suitability classification could not be determined (e.g., removed videos, unsupported languages). | |
| Brand Suitable Ads⁴ | Measured ads not violating DV YouTube Profile criteria. | |
| Brand Suitable Rate⁴ | Percentage of ads not triggering suitability incidents. | Brand Suitable Ads / Brand Suitability Measured Ads |
| Industry Defined Suitability Incidents⁴ | Ads triggering Industry Defined Unsuitable incidents. | |
| Industry Defined Suitability Incident Rate⁴ | Percentage of ads with Industry Defined incidents. | Industry Defined Incidents / Brand Suitability Measured Ads |
| Industry Defined Suitable Ads⁴ | Ads deemed suitable by Industry Defined categories. | |
| Industry Defined Suitable Rate⁴ | Percentage of ads suitable by Industry Defined categories. | Industry Defined Suitable Ads / Brand Suitability Measured Ads |
| UC Incidents⁴ | Measured ads triggering UC Incidents. | |
| UC Incident Rate⁴ | Percentage of measured ads with UC Incidents. | UC Incidents / Brand Suitability Measured Ads |
| Unique Incidents⁴ | Deduplicated count of all fraudulent and Brand Suitability incident impressions. | |
| Unique Incident Rate⁴ | Percentage of Monitored Ads with at least one incident. | Unique Incidents / Monitored Ads² |

## YouTube Disclosures

**Note:** Google restricts data access for privacy compliance. DV works with Google to minimize data redaction impact. Redacted traffic is combined into campaign-level and vendor-client-id-level rows.

**Viewability Impression Distribution:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Net Impressions | Count of gross ads where GIVT is removed. | |
| Viewability Eligible Impressions | Impressions with potential to be measured for viewability. | |
| Viewability Ineligible Impressions⁴ | Net Impressions not meeting eligibility requirements. | |
| Viewability Measured Impressions | Impressions where DV could make viewability decisions. | |
| Viewable Impressions | Impressions measured as viewable per IAB guidelines. | |
| Non-Viewable Impressions | Measured Impressions not meeting IAB minimum. | |
| Undetermined Impressions | Net Impressions where viewability could not be determined. | |

**Invalid Traffic Details:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Impressions | All impressions before GIVT removal. | |
| GIVT Impressions | Deduplicated count of GIVT impressions. | |
| GIVT Rate | Percentage of GIVT over Gross Impressions. | GIVT Impressions / Gross Impressions |
| Fraud/SIVT Incidents⁴ | Count of Monitored Ads with Fraud/SIVT incidents. | |
| Fraud/SIVT Incident Rate⁴ | Percentage of Monitored Ads with Fraud/SIVT. | Fraud/SIVT Impressions / Monitored Impressions |
| Total Net Impressions⁴ | Impressions on valid traffic only. | |

## YouTube Viewability

DV measures across multiple YouTube ad formats: TrueView In-stream, Bumper Ads, Standard In-stream, In-stream Select, and Google Preferred.

| Measure | Description | Rate Calculation |
|---|---|---|
| 100% Display Viewable Impressions⁴ | Impressions where 100% of creative was in viewport for at least 1 second. | |
| 100% Display Viewable Rate⁴ | Percentage meeting 100% display viewable standard. | 100% Display Viewable Impressions / Display Measured Impressions |
| 50% Display Viewable Time Buckets⁴ | Impressions with 50%+ in view for 1-5s, 5-15s, or ≥15s. | |
| 50% In-View for 'n' Continuous Sec Impressions⁴ | Impressions with 50%+ in view for 1-6 continuous seconds (display and video). | |
| Audible and In-View on Completion (AVOC) Impressions⁴ | Impressions with 50%+ in view and audio on at video completion. | |
| Audible Impressions | Impressions with audio turned on. | |
| Audible Rate⁴ | Percentage with audio on. | Audible Impressions / Audible Measured Impressions |
| Audible Viewable Impressions | Viewable impressions with audio on. | |
| Audible Viewable Rate⁴ | Percentage of audible impressions that were also viewable. | Audible Viewable Impressions / Audible Viewable Measured Impressions |
| Authentic Ads®⁴ | Ads served in a brand-suitable, fraud-free, geo-targeted environment. | |
| Authentic Rate⁴ | Percentage meeting Authentic criteria. | Authentic Ads / Monitored Ads² |
| Authentic Viewable Impressions⁴ | Authentic Impression® also meeting IAB viewability guideline. | |
| Authentic Viewable Rate⁴ | Percentage meeting Authentic and viewability criteria. | Authentic Viewable Impressions / Measured Impressions³ |
| Average IAB Pixel Standard In-View Time (s)⁴ | Average time the video ad was at least 50% in-view. | |
| Completion Metrics⁴'⁹ | Count of video impressions completing Q4. | Qx Completed Impressions / Measured Impressions |
| Q1/Q2/Q3 Completed Impressions⁴ | Impressions completing the respective quartile. | |
| Q1/Q2/Q3/Q4 Completed and Viewable Impressions⁴'⁹ | Video impressions completing the quartile and meeting IAB viewability. | |
| Viewable Impressions | Impressions measured as viewable per IAB guidelines (Display: 50%/1s, Video: 50%/2s). | |
| Viewable Rate | Percentage of measured impressions that were viewable. | Viewable Impressions / Viewability Measured Impressions |

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
5. This formula applies only to campaigns using **YouTube Brand Suitability**.
9. The auction inventory includes YouTube TrueView ads that are skippable with a 5-second forced duration.
11. YouTube only — does not apply to tag-based traffic or any other DV-integrated social platform.
