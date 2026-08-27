# DV Proprietary Media Gardens (PMG) Metrics — Snapchat

> DV metric definitions, descriptions, and rate calculations for Snapchat.

---

## Snapchat Brand Suitability

| Measure | Description | Rate Calculation |
|---|---|---|
| Authentic Ads¹³'¹⁵ | Ads served in a brand suitable environment, free from fraud/SIVT. Note: For Snapchat, does not include geographic targeting. | |
| Authentic Rate¹³'¹⁵ | Percentage of ads meeting Authentic criteria. | Authentic Ads / Brand Suitability Measured Ads |
| Authentic Viewable Impressions¹⁵ | Authentic impressions meeting IAB viewability standard. | |
| Authentic Viewable Rate¹⁵ | Percentage meeting Authentic and viewability criteria. | Authentic Viewable Impressions / Brand Suitability and Viewability Measured Impressions |
| Brand Risk Floor Free Ads⁴ | Ads served adjacent to content not in Brand Risk Floor. | |
| Brand Suitability Incidents⁴ | Measured ads adjacent to unsuitable videos. | |
| Brand Suitability Incident Rate⁴ | Percentage of measured ads with suitability incidents. | Brand Suitability Incidents / Brand Suitability Measured Ads |
| Brand Suitable Ads⁴ | Measured ads not adjacent to unsuitable videos. | |
| Brand Suitable Rate⁴ | Percentage of ads not matching Unsuitable Categories. | Brand Suitable Ads / Brand Suitability Measured Ads |
| UC Incidents⁴ | Measured impressions triggering UC Incidents. | |
| Unique Incidents⁴ | Deduplicated count of Brand Suitability and Fraud/SIVT incidents. | |

## Snapchat Disclosures (Invalid Traffic Details)

| Measure | Description | Rate Calculation |
|---|---|---|
| Gross Ads⁴ | All ads before GIVT removal. | |
| GIVT Ads⁴ | Deduplicated count of GIVT ads. | |
| GIVT Rate⁴ | Percentage of GIVT over Gross Ads. | GIVT Ads / Gross Ads |
| Net Ads⁴ | Ads with GIVT removed. Also represents Monitored Ads. | |
| Fraud/SIVT Incidents⁴ | Deduplicated count of fraud/SIVT incidents. | |
| Fraud/SIVT Incident Rate⁴ | Percentage of Monitored Ads with Fraud/SIVT. | Fraud/SIVT Incidents / Monitored Ads |
| Total Net Ads⁴ | Ads on valid traffic only. | |

## Snapchat Viewability

| Measure | Description | Rate Calculation |
|---|---|---|
| 100% Video Viewable Impressions⁴ | Video impressions where 100% of creative was in viewport for at least 2 continuous seconds. | |
| 100% Video Viewable Rate⁴ | Percentage meeting 100% video viewable standard. | 100% Video Viewable Impressions / Measured Impressions |
| Audible and In-View on Completion (AVOC) Impressions⁴ | Impressions with 50%+ in view and audio on at video completion. | |
| Audible Impressions⁴ | Impressions with audio turned on. | |
| Viewable/Engaged Impressions⁴ | Impressions viewable per IAB guidelines or having strong user interactions indicating engagement. | |
| Viewable/Engaged Rate⁴ | Percentage of viewable/engaged impressions. | Viewable/Engaged Impressions / Measured Impressions |
| Viewable Impressions⁴ | Impressions measured as viewable per IAB guidelines (Display: 50%/1s, Video: 50%/2s, capped at 60s). | |
| Viewable Rate⁴ | Percentage of measured impressions that were viewable. | Viewable Impressions / Measured Impressions |
| Video Full Screen Impressions⁴ | Impressions where ad was expanded to full screen. | |
| Video Full Screen Rate | Percentage of impressions expanded to full screen. | Video Full Screen Impressions / Video Measured Impressions |

## Snapchat Authentic Attention

**Interactions captured:** Share, Save, Attachment Open, Camera Swap, Swipe Up, Story Open.

**Universal Metrics:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Attention Index⁴ | Combined evaluation of exposure and engagement to quantify user attention. | Total Attention Index / Attention Indexed Impressions |
| Attention Indexed Impressions⁴ | Impressions for which DV could calculate the Attention Index. | |
| Authentic Attention Monitored Ads⁴ | Monitored Ads with DV Authentic Attention service activated. | |

**Exposure Metrics:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Exposure Index⁴ | Combined evaluation of multiple data points of ad presentation. | Total Exposure Index / Exposure Indexed Impressions |
| Intensity Index⁴ | Evaluation of time the ad's sight, sound, and motion are presented. | Total Intensity Index / Intensity Indexed Impressions |
| Prominence Index⁴ | Evaluation of the ad's Share of Screen. | |

**Engagement Metrics:**

| Measure | Description | Rate Calculation |
|---|---|---|
| Ad Focus Index⁴ | Evaluation of the ad's ability to capture eye gaze. | Total Ad Focus Index / Ad Focus Indexed Impressions |
| Ad Interaction Index⁴ | Combined evaluation of ad's ability to maintain eye gaze and spark interaction. | Total Ad Interaction Index / Ad Interaction Indexed Impressions |
| Average Dwell Time (s)⁴ | Average expected dwell time - ad's ability to maintain user attention. | Total Dwell Time (s) / Ad Interaction Indexed Impressions |
| Average % Viewed⁴ | Likelihood impressions were viewed, based on AI-powered predictive models. | Total % Viewed / Ad Focus Indexed Impressions |
| Engagement Index⁴ | Combined evaluation of user-initiated engagements and probability user looked at ad. | Total Engagement Index / Engagement Indexed Impressions |

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
