# DV Proprietary Media Gardens (PMG) Metrics — TikTok

> DV metric definitions, descriptions, and rate calculations for TikTok.

---

## TikTok Brand Suitability

| Measure | Description | Rate Calculation |
|---|---|---|
| Authentic Ads⁴'¹³'¹⁵ | Deduplicated count of ads that were brand suitable, free from fraud/SIVT, and in targeted geographic region. | |
| Authentic Rate⁴'¹³'¹⁵ | Percentage of ads meeting Authentic criteria. | Authentic Ads / Brand Suitability Measured Ads |
| Authentic Viewable Impressions⁴'¹⁵ | Authentic impressions meeting IAB video viewability standard. | |
| Authentic Viewable Rate⁴'¹⁵ | Percentage meeting Authentic and viewability criteria. | Authentic Viewable Impressions / Brand Suitability and Viewability Measured Impressions |
| Brand Risk Floor Free Ads⁴ | Ads served adjacent to content not in Brand Risk Floor. | |
| Brand Suitability Incidents⁴ | Measured ads adjacent to unsuitable content. | |
| Brand Suitability Incident Rate⁴ | Percentage of measured ads with suitability incidents. | Brand Suitability Incidents / Brand Suitability Measured Ads |
| Brand Suitable Ads⁴ | Measured ads not adjacent to unsuitable content. | |
| Brand Suitable Rate⁴ | Percentage of ads not triggering suitability incidents. | Brand Suitable Ads / Brand Suitability Measured Ads |
| Non Pre-bid Brand Suitable Ads⁴ | Non pre-bid measured ads not violating DV TikTok profile. | |
| Non Pre-bid Brand Suitability Incidents⁴ | Non pre-bid impressions triggering Brand Suitability incidents. | |
| Pre-bid Impressions⁴ | Impressions where pre-bid services were activated. | |
| Pre-bid Brand Suitable Ads⁴ | Pre-bid measured ads not violating DV TikTok profile. | |
| Pre-bid Brand Suitability Incidents⁴ | Pre-bid impressions triggering Brand Suitability incidents. | |
| Pre-bid Protected Rate⁴ | Percentage of monitored ads with pre-bid services. | Pre-bid Protected Ads / Brand Suitability Monitored Ads |
| UC Incidents⁴ | Measured impressions triggering UC Incidents. | |
| Unique Incidents⁴ | Deduplicated count of Brand Suitability, Fraud/SIVT and Geo incidents. | |

## TikTok Disclosures

**Viewability Impression Distribution:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Net Impressions⁴ | Count of gross ads where GIVT is removed. | |
| Viewability Eligible Impressions⁴ | Impressions with potential to be measured for viewability. | |
| Viewability Measured Impressions⁴ | Impressions where DV could make viewability decisions. | |
| Viewable Impressions⁴ | Impressions measured as viewable per IAB guidelines. | |
| Non-Viewable Impressions⁴ | Measured Impressions not meeting IAB viewability minimum. | |
| Undetermined Impressions⁴ | Net Impressions where viewability could not be determined. | |

**Invalid Traffic Details:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Impressions⁴ | All impressions before GIVT removal. | |
| GIVT Impressions⁴ | Deduplicated count of GIVT impressions. | |
| GIVT Rate⁴ | Percentage of Gross Impressions identified as GIVT. | GIVT Impressions / Gross Impressions |
| Fraud/SIVT Incidents⁴ | Count of Monitored Ads with Fraud/SIVT incidents. | |
| Fraud/SIVT Incident Rate⁴ | Percentage of Monitored Ads with Fraud/SIVT. | Fraud/SIVT Impressions / Monitored Impressions |
| Total Net Impressions⁴ | Impressions on valid traffic only. | |

## TikTok Viewability

| Measure | Description | Rate Calculation |
|---|---|---|
| 50% In-View for 'n' Continuous Sec Impressions⁴ | Impressions with 50%+ in view for 1-6 continuous seconds (display and video). | |
| Audible and In-View on Completion Impressions⁴ | Impressions where 50%+ was in view with audio enabled at video completion. | |
| Audible Impressions⁴ | Impressions with audio turned on. | |
| Audible Viewable Impressions⁴ | Viewable impressions with audio on. | |
| Authentic Ads⁴'¹³ | Deduplicated count of impressions that were brand suitable, free from fraud/SIVT, and in targeted region. | |
| Authentic Viewable Impressions⁴ | Authentic impressions meeting IAB video viewability standard. | |
| In Geo Ads⁴ | Ads served within targeted geographic area. | |
| In Geo Rate⁴ | Percentage in targeted geography. | In Geo Ads / Monitored Ads |
| Out of Geo Incidents⁴ | Ads served outside designated geographic targeting area. | |
| Viewable Impressions⁴ | Impressions measured as viewable per IAB guidelines. | |
| Viewable Rate⁴ | Percentage of measured impressions that were viewable. | Viewable Impressions / Viewability Measured Impressions |

## TikTok Authentic Attention

**Universal Metrics:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Attention Index⁴ | Combined evaluation of exposure and engagement to quantify user attention. | Total Attention Index / Attention Indexed Impressions |
| Attention Eligible Impressions⁴ | Impressions with potential to be measured for Authentic Attention. | |
| Authentic Attention Monitored Ads⁴ | Monitored Ads with DV Authentic Attention service activated. | |
| Authentic Viewable Impressions⁴ | Authentic Impression® also meeting IAB viewability guideline. | |

**Exposure Metrics:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Exposure Index⁴ | Combined evaluation of multiple data points of ad presentation. | Total Exposure Index / Exposure Indexed Impressions |
| Intensity Index⁴ | Evaluation of time the ad's sight, sound, and motion are presented. | Total Intensity Index / Intensity Indexed Impressions |
| In-View Time⁴ | Average time (in seconds) that an ad had at least one pixel in view. | |
| Prominence Index⁴ | Evaluation of the ad's Share of the Screen. | Total Prominence Index / Prominence Indexed Impressions |

**Engagement Metrics:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Ad Interaction Index⁴ | Combined evaluation to determine if user interacted with the ad while on screen. | Total Ad Interaction Index / Ad Interaction Indexed Impressions |
| Engagement Index⁴ | Combined evaluation of user-initiated engagements and probability user looked at ad. | Total Engagement Index / Engagement Indexed Impressions |
| User Presence Index⁴ | Evaluation of device level indicators to determine if user was present when ad was viewable. | Total User Presence Index / User Presence Indexed Impressions |
| Average In-View Time(s)⁴ | Time (in seconds) that an Ad was able to capture a user's attention. | Total In-View Time (s) / Attention Eligible Impressions |

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
15. **Brand Suitability availability:** Brand Suitability is available globally across 30+ countries for TikTok and six countries for X. Authentic Ads and Authentic Viewable Impressions are only available in those countries.
