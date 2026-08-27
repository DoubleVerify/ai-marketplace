# DV Business Glossary: Metrics & Dimensions Reference

> Consolidated reference of all DoubleVerify metrics, dimensions, and rate calculations from the DV Pinnacle Support Portal. Source: [Metrics Landing Page](https://dvpinnaclesupport.doubleverify.com/support/solutions/articles/151000176057-metrics-landing-page)

---

## Table of Contents

1. [General Reporting](#general-reporting)
   - [DV Performance Measures](#dv-performance-measures)
   - [Request, Ad and Impression Counts](#request-ad-and-impression-counts)
2. [Benchmarks Reporting](#benchmarks-reporting)
3. [Brand Suitability Reporting](#brand-suitability-reporting)
   - [Filters, Incidents & Blocks](#brand-suitability-filters-incidents--blocks)
   - [Miscellaneous](#brand-suitability-miscellaneous)
   - [Category Tiering](#category-tiering-reporting-metrics)
4. [DV AI Verification Reporting](#dv-ai-verification-reporting)
5. [DV Authentic Attention Reporting](#dv-authentic-attention-reporting)
   - [Attention Measurement](#attention-measurement-reporting-metrics)
   - [Engagement Measurement](#engagement-measurement-reporting-metrics)
   - [Exposure Measurement](#exposure-measurement-reporting-metrics)
   - [Authentic Attention for Snapchat](#dv-authentic-attention-reporting-metrics-for-snapchat)
   - [Authentic Attention for TikTok](#dv-authentic-attention-reporting-metrics-for-tiktok)
6. [Fraud & SIVT Reporting](#fraud--sivt-reporting)
   - [Fraud/SIVT Metrics](#fraudsivt-reporting-metrics)
   - [GIVT Metrics](#givt-reporting-metrics)
   - [Disclosures Metrics](#open-web-disclosures-reporting-metrics)
7. [Geo Reporting](#geo-reporting)
8. [GroupM Standard Reporting](#groupm-standard-reporting)
   - [GroupM Billable Definitions](#groupm-billable-definitions)
   - [GroupM Impression Counts](#groupm-impression-counts)
9. [Programmatic Analytics Reporting](#programmatic-analytics-reporting)
   - [Auction, IP and User Agent Metrics](#programmatic-analytics-auction-ip-and-user-agent-related-metrics)
   - [Blocking-related Metrics](#programmatic-analytics-blocking-related-metrics)
   - [Disclosures Metrics](#programmatic-analytics-disclosures-metrics)
   - [DV Tag & Media Identifiers](#programmatic-analytics-dv-tag--media-identifiers-metrics)
   - [Monitoring-related Metrics](#programmatic-analytics-monitoring-related-metrics)
10. [Viewability Reporting](#viewability-reporting)
    - [In-App Viewability](#in-app-viewability-reporting-metrics)
    - [Video & CTV Data](#video--ctv-data-reporting-metrics)
    - [Viewability Metrics](#viewability-reporting-metrics)

---

## General Reporting

### DV Performance Measures

The Quality dashboards include several quality measures that demonstrate the performance of campaigns.

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Authentic Ads** | Ads served in a brand-specific, high-quality environment that meets the settings of the DV Digital IQ profile, improving the performance of campaigns. A single, deduplicated measure of ads that were brand-suitable and free from fraud and other forms of SIVT in the targeted geographic region. | Authentic Rate = Authentic Ads / Monitored Ads |
| **Authentic Custom Viewable Impressions** | An Authentic Custom Viewable Impression includes an additional premium layer of analysis that shows when an Authentic Ad was also in view as determined using the Custom Viewability Measurement definition for the profile. | Authentic Custom Viewable Rate = Authentic Custom Viewable Impressions / Measured Impressions |
| **Authentic Viewable Impressions** | An Authentic Viewable Impression includes an additional premium layer of analysis that shows when an Authentic Ad also meets the IAB standard for viewability. DV provides Authentic Display Viewable Impressions and Authentic Video Viewable Impressions. | Authentic Viewable Rate = Authentic Viewable Impressions / Measured Impressions |
| **Brand Suitable Ads** | The unique count of ads that were not served on sites in violation of site lists (Exclusion or Inclusion List) or sites with unsuitable categories. | Brand Suitable Rate = Brand Suitable Ads / Monitored Ads (applies only to campaigns using Brand Suitability services) |
| **Fraud/SIVT Free Ads** | The unique count of ads free from bot fraud, site fraud, nonhuman data center traffic, hijacked devices, and injected ads. | Fraud/SIVT Free Rate = Fraud-SIVT Free Ads / Monitored Ads |
| **In Geo Ads** | The unique count of ads served within the targeted country, designated market areas, state/region, or ZIP code as defined by the Geo Targeting profile. | In Geo Rate = In Geo Ads / Monitored Ads |
| **Media Spend** | Monthly media spend (cost) associated with a DV product. | - |
| **Unique Incidents** | The deduplicated count of all incidents found when ads did not meet the criteria of the DV Digital IQ profile. Represents all ads that did not meet insertion order criteria for fraud/SIVT protection, brand suitability, and geographic targeting. | Unique Incident Rate = Unique Incidents / Monitored Ads |

### Request, Ad and Impression Counts

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Allowed Ads** | A unique count of requests that were allowed because they met the blocking criteria for the DV Digital IQ campaign and had no violations. | Allowed Ad Rate = Allowed Ads / Requests |
| **Allowed Evaluations** | The number of evaluations determined to be compliant based on Brand Suitability, Geo, or Fraud profiles. | Allowed Evaluation Rate = Allowed Evaluations / Evaluations |
| **Blocked Requests** | The unique count of requests blocked because they did not meet the blocking criteria for the DV Digital IQ campaign. A single, deduplicated measure of all incidents prevented through blocking. | - |
| **Evaluations** | The total number of non-GIVT video ad calls that Video Filtering assessed. | - |
| **Filter Rate** | The ratio between Filters and Evaluations. | Filter Rate = Filters / Evaluations |
| **Filters** | The number of evaluations determined to be non-compliant based on Brand Suitability, Geo, or Fraud profiles. The amount of ad calls that were "filtered". | - |
| **Monitored Ads** | The total count of ads served where the DV Monitoring services were applied. | - |
| **Requests** | The count of requests received by the blocking tag when the Blocking service is used. | - |
| **Total Blocking Requests** | The total count of requests received by the blocking tag when the Blocking service is used. | - |

---

## Benchmarks Reporting

### Benchmarks Performance Reporting Metrics

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Authentic Display Viewable Rate** | Percentage of Display Measured Impressions that are identified as Authentic and also met the IAB standard for video viewability. | Authentic Display Viewable Impressions / Display Measured Impressions |
| **Authentic Rate** | Percentage of Measured Impressions that met the criteria for Authentic Ads. | Authentic Ads / Monitored Ads |
| **Authentic Video Viewable Rate** | Percentage of Video Measured Impressions that are identified as Authentic and also met the IAB standard for video viewability. | Authentic Video Viewable Impressions / Video Measured Impressions |
| **Block Rate** | Percentage of blocking requests when the Blocking service is used. | Blocks / Requests |
| **Brand Suitability Violation Rate** | Percentage of Monitored Ads that had a Brand Suitability incident. | (Brand Suitability Incidents + Brand Suitability Blocks) / (Monitored Ads + All Blocks) |
| **Display Viewable Rate** | Percentage of Display Measured Impressions identified as viewable. | Display Viewable Impressions / Display Measured Impressions |
| **Fraud/SIVT Violation Rate** | Percentage of Monitored Ads with any form of Fraud or SIVT incidents. | (Fraud/SIVT Incidents + Brand Suitability Blocks) / (Monitored Ads + All Blocks) |
| **Out of Geo Violation Rate** | Percentage of ads served outside the targeted geographic areas. | (Out of Geo Incidents + Brand Suitability Blocks) / (Monitored Ads + All Blocks) |
| **Video Viewable Rate** | Percentage of Video Measured Impressions measured as viewable according to the IAB viewability guidelines. | Video Viewable Impressions / Video Measured Impressions |

---

## Brand Suitability Reporting

### Brand Suitability Filters, Incidents & Blocks

DV's brand suitability methodology provides property-level protection against categories, languages, app metadata, and URL keywords deemed unsuitable by DV clients at a page, site, and app level.

| Measure | Product | Description | Rate Calculation |
|---------|---------|-------------|-----------------|
| **App Store Category** | Video Filtering, Monitoring & Blocking | Count of filters/incidents/blocks on or from apps categorized with an app store category selected within Brand Suitability settings. | Filter: App Store Category Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Brand Risk Floor Free Ads** | Video Filtering, Monitoring & Blocking | The number of ads served on a page, site, or app that were not assigned a category in the Brand Risk Floor. | Brand Risk Floor Free Rate = Brand Risk Floor Free Ads / Monitored Ads |
| **Brand Risk Floor Blocks/Filters/Incidents** | Blocking/Filtering/Monitoring | Count triggered due to request occurring on a page, site, or app assigned a category in the Brand Risk Floor. | Block Rate = Blocks / Requests; Filter Rate = Filters / Evaluations; Incident Rate = Incidents / Monitored Ads |
| **Brand Suitable Ads** | Monitoring | Ads served on pages, sites, or apps free from Brand Suitability and Brand Risk Floor incidents. | Brand Suitable Ads / Monitored Ads |
| **Brand Suitability** | Video Filtering, Monitoring & Blocking | Count of filters/incidents/blocks from apps, sites, or pages that served or were prevented from being served because they did not meet Brand Suitability settings. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Custom Category Page** | Video Filtering, Monitoring & Blocking | Requests from pages classified with a brand's custom category. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Keyword List Violations** | Video Filtering, Monitoring & Blocking | Count of filters/incidents/blocks from ads served on pages where specific words in the URL match items on the keyword list. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Language List Violations** | Video Filtering, Monitoring & Blocking | Deduplicated count of filters/incidents/blocks in languages on Language Exclusion List or not on Language Inclusion List. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **New App** | Video Filtering, Monitoring & Blocking | Count from apps that do not have an app classification in the system. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Off App List Violations** | Video Filtering, Monitoring & Blocking | Count from apps not on the App Inclusion List. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **On App List Violations** | Video Filtering, Monitoring & Blocking | Count from apps on the App Exclusion List. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Out of Age** | Video Filtering, Monitoring & Blocking | Count where a mobile app ad did not meet brand suitability settings for App Age Rating (Everyone 4+, Tweens 9+, Teens 12+, Mature 17+, Adults Only 18+, Unrated). | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Out of Star** | Video Filtering, Monitoring & Blocking | Count where a mobile app ad did not meet App Star Rating settings (< 4.5, < 4, < 3.5, < 3, < 2.5, < 2, < 1.5 stars). | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Share of Keyword** | Video Filtering, Monitoring & Blocking | Percentage of total keyword violations belonging to a given string in the URL. | Filter: Keyword Filters / Overall Keywords Filters; Incident: Keyword Incidents / Overall Keywords Incidents; Block: Keyword Blocks / Overall Keywords Blocks |
| **Site & App List Violations** | Video Filtering, Monitoring & Blocking | Deduplicated count including On Exclusion List, Off Inclusion List for sites and apps. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Unique Brand Suitability** | Video Filtering, Monitoring & Blocking | Deduplicated count of all desktop, web, and in-app brand suitability filters/incidents/blocks. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Unsuitable Category (UC)** | Video Filtering, Monitoring & Blocking | Aggregated count of UC App, UC Page, and UC Site violations for sites/pages/apps classified with a selected Unsuitable Category. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |

### Brand Suitability Miscellaneous

Brand Suitability Miscellaneous is a deduplicated count of filters or blocks based on sites where DV did not evaluate the content.

| Measure | Product | Description | Rate Calculation |
|---------|---------|-------------|-----------------|
| **Brand Suitability Miscellaneous** | Video Filtering & Blocking | Aggregated count of Middleware Site, New Site, and No Domain filters/blocks on sites where DV did not evaluate content. | Filter: Miscellaneous Filters / Evaluations; Block: Miscellaneous Blocks / Requests |
| **Middleware Site** | Video Filtering & Blocking | Count due to requests from a site identified as an ad server or middleware site. | Filter: Middleware Filters / Evaluations; Block: Middleware Blocks / Requests |
| **New Site** | Video Filtering & Blocking | Count where the domain is a site not yet in the system. All new sites are considered unsuitable by default and classified within hours. | Filter: New Site Filters / Evaluations; Block: New Site Blocks / Requests |
| **No Domain** | Video Filtering & Blocking | Count where the blocking tag was unable to identify the domain because the value was a local path or IP address. | Filter: No Domain Filters / Evaluations; Block: No Domain Blocks / Requests |

### Category Tiering Reporting Metrics

DV offers 90+ unique Brand Suitability category settings including 14 categories with three levels of risk, plus 50 categories without suitability tiers.

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Impact Metric** | Indicates the increase of Block Rate or decrease of Authentic Rate that would likely occur if a category was added to the Unsuitable Category list. | - |
| **Impact on Authentic Rate if Added to UC** | Number of Authentic Ads for a single category divided by total Monitored Ads across all categories. | Authentic Ads / Overall Monitored Ads |
| **Impact on Block Rate if Added to UC** | Number of Allowed Ads for a single category divided by total Requests across all categories. | Allowed Ads / Overall Requests |
| **Impact on Filter Rate if Added to UC** | Number of Allowed Evaluations for a single category divided by total Evaluations across all categories. | Allowed Evaluations / Overall Evaluations |
| **Incremental Metric** | The number of violations triggered exclusively due to an Unsuitable Category setting where there are no other violations outside of UC on the same impression. | - |
| **Share of Metric** | Indicates the share of the corresponding metric belonging to a specific category from the overall deduplicated count. | - |
| **Share of Allowed Ads** | Share of Allowed Ads for a single category divided by total Allowed Ads across all categories. | Allowed Ads / Overall Allowed Ads |
| **Share of Authentic Ads** | Share of Authentic Ads for a single category divided by total Authentic Ads across all categories. | Authentic Ads / Overall Authentic Ads |
| **Share of Blocks** | Share of Blocks for a single category divided by total Blocks across all categories. | Blocks / Overall Blocks |
| **Share of Monitored Ads** | Share of Monitored Ads for a single category divided by total Monitored Ads across all categories. | Monitored Ads / Overall Monitored Ads |
| **Share of UC Blocks/Filters/Incidents** | Share of UC violations for a single category divided by total UC violations across all categories. | UC Blocks / Overall UC Blocks; UC Filters / Overall UC Filters; UC Incidents / Overall UC Incidents |
| **UC Incremental Blocks** | The number of blocks triggered exclusively due to a page, site, or app being assigned an Unsuitable Category setting. | - |
| **UC Incremental Filters** | The number of evaluations filtered but would be allowed if a category were removed from the UC list. | - |
| **UC Incremental Incidents** | The number of impressions that would become Authentic if a category were removed from the UC list. | - |

---

## DV AI Verification Reporting

### AI Verification Reporting Metrics

The AI Verification dashboard helps advertisers identify and manage AI bot interactions and low-quality AI-generated content. Some metrics include GIVT that is filtered from other Pinnacle dashboards.

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **AI Bots and Crawlers Ads** | Invalid traffic generated by AI Bots and Crawlers, including declared AI Bots (GIVT), automated and agentic AI browsing (GIVT), and evasive SIVT scrapers (SIVT). | AI Bots and Crawlers Rate = AI Bots and Crawlers Ads / Gross Monitored Ads |
| **Low-quality GenAI Ads** | Ads served on Low-Quality GenAI websites (sites predominantly comprised of textual content produced by GenAI with minimal human oversight or editing). | Low-Quality GenAI Rate = Low-Quality GenAI Ads / Monitored Ads |
| **Automated and Agentic AI Browsing Ads** | Ads served to bots via automated aspects of AI-driven or scripted browsers, including headless tools and intelligent agents (classified as GIVT). | Rate = Automated and Agentic AI Browsing Ads / Gross Monitored Ads |
| **Declared AI Bots Ads** | Ads delivered to known and transparent AI bots that declare their identity (e.g., GPTBot, GoogleBot). Classified as GIVT. | Rate = Declared AI Bots Ads / Gross Monitored Ads |
| **Evasive AI Bots Ads** | Ads delivered to undeclared or obfuscated AI bots that mask identity or behavior. Classified as SIVT. | Rate = Evasive AI Bots Ads / Gross Monitored Ads |
| **Gross Monitored Ads** | Count of ads served where DV Monitoring services were applied before GIVT is removed. Includes GIVT, SIVT, and valid ads. | - |

---

## DV Authentic Attention Reporting

### Attention Measurement Reporting Metrics

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Attention Index** | Aggregated measure of 50+ data points that quantify attention in a way that correlates to business outcomes. Average of Exposure Index and Engagement Index. | Total Attention / Attention Indexed Impressions |
| **Attention Indexed Impressions** | Count of impressions for which DV was able to calculate the Attention Index. | - |
| **Authentic Attention Monitored Ads** | The number of Monitored Ads (excluding CTV) where the DV Authentic Attention service is activated. Used for billing. | - |
| **Authentic Viewable Impressions** | Deduplicated count of impressions that were brand suitable, free from Fraud/SIVT, in the targeted geographic region, and met the IAB standard for viewability. | Authentic Viewable Rate = Authentic Viewable Impressions / Measured Impressions |
| **Direct-Indexed Impressions** | Based on direct, deterministic signals collected at the impression level. Used to inform all Attention metrics. | Direct-Indexed Rate = Direct-Indexed Impressions / Indexed Impressions |
| **Model-Indexed Impressions** | Generated via an AI model trained by DV's Direct-Indexed Impressions. Used to inform all Attention metrics. | - |
| **High Exposure High Engagement Impressions** | Count of impressions scoring above 100 for both the Exposure and Engagement indices. | - |
| **High Exposure Low Engagement Impressions** | Count of impressions scoring above 100 for Exposure Index and below 100 for Engagement Index. | - |
| **Low Exposure High Engagement Impressions** | Count of impressions scoring below 100 for Exposure Index and above 100 for Engagement Index. | - |
| **Total Attention** | Sum of Attention Index values for all Attention Indexed Impressions. | - |
| **Viewability Weighted Attention** | Calculated as: Attention Index x Authentic Viewable Rate. | - |

### Engagement Measurement Reporting Metrics

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Engagement Index** | Aggregated measure of the User Presence Index and Ad Interaction Index - evaluation of over 20 user-initiated engagements with the device (while ad is viewed) and the ad itself. | Total Engagement / Engagement Indexed Impressions |
| **Ad Interaction Index** | Evaluation to determine if the user interacted with the ad while it was viewable. Benchmarked against all other DV-measured impressions, normalized to 100. | Total Ad Interaction / Ad Interaction Indexed Impressions |
| **User Presence Index** | Evaluation of device level indicators to determine if the user was present when the ad was viewable. Part of Engagement Index. Normalized to 100. | - |
| **Ad Clicked Impressions** | Count of impressions where a user clicked on the ad. | Ad Clicked Rate = Ad Clicked Impressions / Engagement Measured Impressions |
| **Ad Mouse Hover Impressions** | Count of impressions where a user hovered over the ad. | Ad Mouse Hover Rate = Ad Hover Impressions / Engagement Measured Impressions |
| **Ad Muted Impressions (Video)** | Count of video impressions where a user muted the volume. | Ad Muted Rate = Ad Muted Impressions / Engagement Measured Impressions |
| **Ad Paused Impressions (Video)** | Count of video impressions where a user pressed pause. | Ad Paused Rate = Ad Paused Impressions / Engagement Measured Impressions |
| **Ad Resumed Impressions (Video)** | Count of video impressions where a user pressed resume. | Ad Resumed Rate = Ad Resumed Impressions / Engagement Measured Impressions |
| **Ad Skipped Impressions (Video)** | Count of video impressions where a user pressed skip ad. | Ad Skipped Rate = Ad Skipped Impressions / Engagement Measured Impressions |
| **Ad Touched Impressions** | Count of impressions where a user touched the ad using a touch-input device. | Ad Touched Rate = Ad Touched Impressions / Engagement Measured Impressions |
| **Audio Engagement Impressions** | Count of impressions where a user engaged with audio volume controls while the ad was viewable. | Audio Engagement Rate = Audio Engagement Impressions / Engagement Measured Impressions |
| **Device Key Press/Mouse Movement/Scroll Impressions** | Counts of impressions with various device-level interactions. | Rate = Impressions / Engagement Measured Impressions |
| **Screen Engagement Impressions** | Count of impressions where a user engaged with the screen, window, or browser tab impacting the ad's visible presentation. | Screen Engagement Rate = Screen Engagement Impressions / Engagement Measured Impressions |
| **Touch Engagement Impressions** | Count of impressions where a user touched the screen, mouse, or keyboard key while the ad was viewable. | Touch Engagement Rate = Touch Engagement Impressions / Engagement Measured Impressions |
| **Playback Engagement Impressions** | Count of impressions where a user engaged with the playback controls on the ad. | Playback Engagement Rate = Playback Engagement Impressions / Engagement Measured Impressions |
| **Engagement Measured Impressions** | Count of impressions for which DV was able to measure engagement events. | - |

### Exposure Measurement Reporting Metrics

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Exposure Index** | Aggregated measure of Intensity Index and Prominence Index - combined evaluation of multiple data points of the ad presentation. | Total Exposure / Exposure Indexed Impressions |
| **Intensity Index** | For Display: evaluation of the ad's IAB viewable, audible, and fully on screen time. For Video: evaluation of viewability, audibility, quartile completion, and fully on screen time relative to video ad duration. | Total Intensity / Intensity Indexed Impressions |
| **Prominence Index** | Evaluation of the ad's share of screen. Benchmarked against all other DV-measured impressions, normalized to 100. | Total Prominence / Prominence Indexed Impressions |
| **Audible and In-View on Completion (AVOC)** | Percentage of impressions when 50% or more of creative was in view, and audio was enabled at video completion. | AVOC Rate = AVOC Impressions / Completed Impressions |
| **Audible Impressions** | Count of impressions with audio turned on for any duration during playback. | Audible Rate = Audible Impressions / Audible Measured Impressions |
| **Avg. Viewable Time (Sec)** | Average time duration for which an IAB viewable impression satisfied the pixel threshold requirements (capped at 60 seconds). | - |
| **Completed Impressions** | Count of video impressions that completed all four quartiles. | Completed Rate = Completed Impressions / Measured Impressions |
| **Q1-Q4 Completed Impressions** | Count of video impressions that completed the specified quartile. | Qx Completed Rate = Qx Completed Impressions / Measured Impressions |
| **Q1-Q4 Audible Impressions** | Count of impressions where audio was turned on at some point within the specified quartile. | Qx Audible Rate = Qx Audible Impressions / Audible Measured Impressions |
| **Q1-Q4 Viewable Impressions** | Count of impressions meeting IAB video viewability criteria within the specified quartile. | Qx Viewable Rate = Qx Viewable Impressions / Measured Impressions |
| **Q1-Q4 Fully On-Screen Impressions** | Count of impressions where creative was fully within the visible portion of the browser for the entire quartile duration. | Qx Fully On-Screen Rate = Qx Fully On-Screen Impressions / Measured Impressions |
| **Total Time Viewable (Sec)** | Sum of viewable time for which Authentic Viewable impressions satisfied pixel threshold requirements. | - |

### DV Authentic Attention Reporting Metrics for Snapchat

Snapchat-specific interactions captured: Share, Save, Attachment Open, Camera Swap, Swipe Up, Story Open.

**Universal Metrics:**

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Authentic Ads** | Ads served in a brand-suitable environment, free from fraud/SIVT. For Snapchat, does not include geographic targeting. | Authentic Rate = Authentic Ads / Brand Suitability Measured Ads |
| **Attention Index** | Combined evaluation of exposure and engagement to quantify user attention. | Total Attention Index / Attention Indexed Impressions |
| **Viewable Impressions** | Impressions measured as viewable per IAB guidelines: at least 50% of creative in view for 2+ seconds (video) or 1+ second (display). | Viewable Rate = Viewable Impressions / Measured Impressions |

**Exposure Metrics:** Exposure Index, Intensity Index, Prominence Index, AVOC, Audible metrics, Completed/Quartile metrics.

**Engagement Metrics:**

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Ad Focus Index** | Evaluation of the ad's ability to capture eye gaze. | Total Ad Focus Index / Ad Focus Indexed Impressions |
| **Ad Interaction Index** | Combined evaluation of the ad's ability to maintain eye gaze and spark interaction (e.g., Swipe up or Share). | Total Ad Interaction Index / Ad Interaction Indexed Impressions |
| **Average Dwell Time (s)** | Average expected dwell time - the ad's ability to maintain a user's attention. | Total Dwell Time (s) / Ad Interaction Indexed Impressions |
| **Average % Viewed** | Likelihood that impressions were viewed, based on AI-powered predictive models. Probability of capturing user's eye gaze for at least 200ms. | Total % Viewed / Ad Focus Indexed Impressions |

### DV Authentic Attention Reporting Metrics for TikTok

**Universal Metrics:** Attention Index, Attention Indexed Impressions, Authentic Attention Monitored Ads, Authentic Viewable Impressions, Total Attention Index.

**Exposure Metrics:** Exposure Index, Intensity Index, Prominence Index, In-View Time.

**Engagement Metrics:**

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Ad Interaction Index** | Combined evaluation to determine if the user interacted with the ad while on screen. | Total Ad Interaction Index / Ad Interaction Indexed Impressions |
| **Engagement Index** | Combined evaluation of user-initiated engagements and probability that a user looked at the ad. | Total Engagement Index / Engagement Indexed Impressions |
| **User Presence Index** | Evaluation of device level indicators to determine if the user was present when the ad was viewable. | Total User Presence Index / User Presence Indexed Impressions |
| **Average In-View Time (s)** | Time in seconds that an ad was able to capture a user's attention. | Total In-View Time (s) / Attention Eligible Impressions |

---

## Fraud & SIVT Reporting

### Fraud/SIVT Reporting Metrics

Fraud/SIVT metrics provide counts of ads served to sites participating in fraudulent activity, bot fraud, nonhuman data center traffic, and injected ads. Available only for clients with IQ Fraud Advanced service.

| Measure | Product | Description | Rate Calculation |
|---------|---------|-------------|-----------------|
| **Adware/Malware** | Video Filtering, Monitoring & Blocking | Unique count of events identified as Injected Ads and/or Hijacked Devices. Served by machines infected with malicious software. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Bot Fraud** | Video Filtering, Monitoring & Blocking | Events identified as being served to a fraudulent bot. DV uses advanced behavioral modeling analyzing spoofed browser info, irregular machine characteristics, and abnormal browsing patterns. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Data Center Traffic** | Video Filtering, Monitoring & Blocking | Events originating from a nonhuman data center (e.g., cloud-computing centers). Not necessarily fraudulent but considered invalid by IAB as not served to human users. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Emulators** | Monitoring | Events occurring within misrepresented device types. Monitoring only. | Incident: Emulators Incidents / Monitored Ads |
| **Fraud** | Video Filtering, Monitoring & Blocking | Deduplicated count of Filters/Incidents/Blocks with any form of Fraud. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Fraud/SIVT** | Video Filtering, Monitoring & Blocking | Unique count recorded as bot fraud, site fraud, nonhuman data center traffic, and injected ad events. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Fraud/SIVT Free Ads** | Video Filtering, Monitoring & Blocking | Count of impressions free from all forms of Fraud and SIVT. | Fraud/SIVT Free Rate = Free Ads / Monitored Ads |
| **Hijacked Devices** | Video Filtering, Monitoring & Blocking | Events on browsers infected with adware/malware, both injected ads and events originating from the publisher. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Injected Ads** | Video Filtering, Monitoring & Blocking | Events not originating from the publisher's web page or app. Inserted via browser toolbars/extensions, network-level insertion, or adware/malware. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |
| **Site Fraud/IVT and App Fraud/IVT** | Video Filtering, Monitoring & Blocking | Events on sites/apps associated with indications of ad impression fraud or invalid traffic practices including spoofing, laundering, hidden ads, nonhuman bot traffic. | Filter: Filters / Evaluations; Incident: Incidents / Monitored Ads; Block: Blocks / Requests |

### GIVT Reporting Metrics

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **GIVT Ads** | Total, deduplicated count of ads identified as general invalid traffic using standardized, industry-wide lists (IAB known bots/spiders, unknown browsers). | GIVT Rate = GIVT Ads / Gross Impressions |
| **Allowed for GIVT** | Count of all requests that were not blocked for GIVT. | Allowed for GIVT Rate = Allowed for GIVT / Gross Requests |
| **Blocks for GIVT** | Count of all requests that were blocked because of GIVT. | Block Rate for GIVT = Blocks for GIVT / Gross Requests |
| **GIVT Known Bot/Spider Blocks** | Count of requests blocked due to IAB Known Bots and Spiders list. | - |
| **GIVT Known Data Center Traffic Blocks** | Count of requests blocked due to being served to Known Data Center list (identified by TAG). | - |
| **GIVT Other Impressions** | Count of impressions originating from DV internal IP addresses, creative-auditing companies, and other standardized filtration methodologies. | - |
| **GIVT Unknown Browser Impressions/Blocks** | Count of impressions/blocks served to unknown or unidentifiable browsers (identified by IAB). | - |
| **Known Bots/Spiders** | Count of impressions requested by bots or spiders on the IAB Known Bots and Spiders list. | - |

### Open Web Disclosures Reporting Metrics

**Gross, Net and Total Net Metrics - Monitoring:**

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Total Calls** | Count of all served ad calls including pre-rendered, GIVT, Fraud/SIVT, and valid impressions. | - |
| **Prerender Calls** | Served calls that are not rendered (pre-cached but never displayed). Removed from valid counts. | Prerender Rate = Prerender Calls / Total Calls |
| **Gross Impressions** | All rendered and served impressions before GIVT is removed. | - |
| **GIVT Impressions** | Total deduplicated count of ads identified as general invalid traffic. | GIVT Rate = GIVT Impressions / Gross Impressions |
| **Net Impressions** | Count of impressions after GIVT has been filtered and removed. | - |
| **Total Net Impressions** | Count of impressions on only valid traffic (Gross minus all GIVT and Fraud/SIVT). | - |

**Viewability Impression Distribution:**

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Eligible Impressions** | Count of Net Impressions with viewability service capability and activation. | - |
| **Measured Impressions** | Impressions where DV obtained information to make viewability decisions. | Measurement Rate = Measured / Eligible |
| **Viewable Impressions** | Impressions measured as viewable per IAB guidelines. | Viewable Rate = Viewable / Measured |
| **Non-viewable Impressions** | Measured Impressions that do not meet IAB minimum for viewability. | Non-Viewable Dist % = Non-viewable / Net Impressions |
| **Undetermined Impressions** | Net Impressions where viewability could not be determined. | Undetermined % = Undetermined / Net Impressions |

**Playback Start Method Details:**

| Measure | Description |
|---------|-------------|
| **Auto-play Impressions** | Count of impressions where the ad was automatically played. |
| **Click-to-play Impressions** | Count of impressions that play only after user interaction. |
| **Unknown Play Status** | Count where DV was unable to determine the playback initiation method. |

---

## Geo Reporting

### Geo Reporting Metrics

Geo represents the unique count of ads monitored or blocked for falling outside targeted areas. The DV Geo Targeting service is not MRC-accredited. Location is determined using the user's IP address verified by Digital Envoy.

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **In Geo Ads** | Unique count of ads served within the targeted country, DMA, state/region, or ZIP code. | In Geo Rate = In Geo Ads / Monitored Ads |
| **Out of Geo Blocks** | Number of blocks for requests from outside the designated geographic targeting area. | Out of Geo Block Rate = Out of Geo Blocks / Requests |
| **Out of Geo Filters** | Number of evaluations from outside the designated geographic targeting area. | Out of Geo Filter Rate = Out of Geo Filters / Evaluations |
| **Out of Geo Incidents** | Number of ads served outside the designated geographic targeting area. | Out of Geo Incident Rate = Out of Geo Incidents / Monitored Ads |
| **Unmeasurable due to Non-consent Ads** | Sum of Monitored Ads unmeasurable for Geo due to user non-consent. | - |
| **Unmeasurable due to Non-consent Evaluations** | Sum of evaluations unmeasurable for Geo due to user non-consent. | - |
| **Unmeasurable due to Non-consent Requests** | Sum of requests unmeasurable for Geo due to user non-consent. | - |

---

## GroupM Standard Reporting

### GroupM Billable Definitions

GroupM Billable Impressions are the total impressions that GroupM pays its media sellers when they agree to be paid against the GroupM standard.

| Measure | Description |
|---------|-------------|
| **Billable Impressions** | Number of impressions for which GroupM pays. Sum of Passed Impressions and Projected Impressions. |
| **Failed Impressions** | Measured display or video impressions that did not meet the GroupM standard. |
| **Passed Impressions** | Measured display or video impressions determined to be SIVT-free and passed the GroupM standard. |
| **Projected Impressions** | Projected count of Unevaluated Impressions that would have passed if they could have been measured. |
| **Unevaluated Impressions** | Number of Ineligible + Unmeasured Impressions, rolled up into a projection segment. |

### GroupM Impression Counts

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **GroupM Active Ads** | Ads for GroupM agencies on which the GroupM standard service is active with GIVT removed. | - |
| **GroupM Authentic Passed Impressions** | Authentic Ad that also meets the GroupM Display Passed Standard. | GroupM Authentic Passed Rate = Authentic Passed Impressions / GroupM Display Measured Impressions |
| **GroupM Eligible Impressions** | Count of non-SIVT impressions where a JavaScript tag was used. | - |
| **GroupM Measured Impressions** | Count of Eligible Impressions where JS tag successfully measured and reported back to DV. | GroupM Measurement Rate = Measured / Eligible |
| **GroupM Passed Impressions** | Count of SIVT-free Measured Impressions that passed the GroupM standard. | GroupM Passed Rate = Passed / Measured |
| **GroupM Failed Impressions** | GroupM Measured Impressions that did not meet the GroupM standard. | GroupM Failed Rate = Failed / Measured |
| **GroupM Fraud/SIVT Incidents** | Count of Active Ads identified as fraudulent or SIVT. | GroupM Fraud/SIVT Rate = Fraud-SIVT / Active Ads |
| **GroupM V4 Display Passed/Failed Impressions** | Measured display impressions that met/did not meet the GroupM 4.0 Display Standard. | Rate = V4 Display Impressions / Display Measured Impressions |
| **GroupM Video Native Passed/Failed Impressions** | Measured video impressions by GroupM Video Native Partners that met/did not meet the standard. | Rate = Video Native Impressions / Video Measured Impressions |
| **GroupM Video Passed & Completed Impressions** | SIVT-free impressions that passed GroupM standard and played to end at normal speed. | Rate = Passed & Completed / Video Measured |
| **GroupM Video Reach Extension Passed/Failed** | Measured video impressions (non-Native Partner) that met/did not meet the Reach Extension Standard. | Rate = Reach Extension Impressions / Video Measured |

---

## Viewability Reporting

### In-App Viewability Reporting Metrics

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **In-App Viewable Impressions (Display or Video)** | Impressions from in-app delivery measured as viewable per IAB guidelines: at least 50% of creative in view for 1+ second (display) or 2+ seconds (video). | Viewable Rate = Viewable / Measured |
| **In-App Viewable Rate (Certified Imps)** | Percentage of viewable impressions from partners with Measurement Status of Certified. | - |
| **In-App Measured Impressions** | Impressions for which DV could obtain viewability information. | Measurement Rate = Measured / Eligible |
| **In-App Eligible Impressions** | Impressions with potential to be measured for viewability. | - |
| **In-App Viewability by Mobile OS** | Distribution by operating system: iOS, Android, Other. | - |
| **In-App Viewability by Device Delivery Type** | Distribution across: In-App Smartphone/Tablet, Mobile Web Smartphone/Tablet, Desktop, Unknown. | - |

### Video & CTV Data Reporting Metrics

Progress is measured using consecutive events sent to DV at the end of each quartile. Counting stops at the furthest consecutive quartile received.

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Avg. Quartiles Progressed %** | Aggregate of furthest consecutive quartile reached, represented as 0-100%. | (Q1+Q2+Q3+Completed) / (Quartile Measured x 4) |
| **Completed Rate per Quartile** | Percentage of video impressions where the signal at the end of each quartile was received. | Qx Completed Impressions / Quartile Measured |
| **Qx Fully On-Screen Impressions** | Count of impressions where creative was fully in view and the quartile signal was received. | Qx FOS Rate = Qx FOS Impressions / FOS Measured |
| **Fully On-Screen Measured Impressions** | Count where DV could determine if creative was fully in view and quartile completions. | FOS Measurement Rate = FOS Measured / Monitored Ads |
| **CTV App Transparency Measured Ads** | Monitored ads served in a CTV app. | - |
| **CTV App Transparent Ads** | Count where DV identified the CTV app where the ad was served. | CTV App Transparency Rate = Transparent Ads / Measured Ads |
| **Verified Streaming TV Ads** | Count validated as serving in a streaming TV player (TV-like viewing experience). | Verified Streaming TV Rate = Verified Ads / Monitored Ads |
| **Continuous Play Calls** | Count of ad calls in OTT configuration that auto-play the next episode. | - |
| **Timed Out Calls** | Count of ad calls from sessions determined to be inactive. | - |

### Viewability Reporting Metrics

All viewability collection uses consecutive time.

| Measure | Description | Rate Calculation |
|---------|-------------|-----------------|
| **Viewable Impressions** | Impressions across desktop, mobile web, mobile in-app, and CTV delivery measured as viewable per IAB: at least 50% of creative (or 30% for large desktop ads) in view for 1+ second (display) or 2+ seconds (video). | Viewable Rate = Viewable / Measured |
| **Measured Impressions** | Impressions for which DV obtained viewability decision information. | Measurement Rate = Measured / Eligible |
| **Eligible Impressions** | Impressions with potential to be measured (include DV viewability measurement technology). | - |
| **Authentic Viewable Impressions** | Deduplicated count that were brand risk floor free, free from Fraud/SIVT, in geo, and met IAB viewability standard. | Authentic Viewable Rate = Authentic Viewable / Measured |
| **Custom Viewable Impressions** | Desktop impressions in view as determined by Custom Viewability Measurement definition (e.g., 70% of creative viewable for 3 seconds). | Custom Viewable Rate = Custom Viewable / Custom Measured |
| **100% Display Viewable Impressions** | 100% of creative in the viewable portion of the browser for at least 1 second. | Rate = 100% Display Viewable / Duration Measured |
| **100% Viewable Through Quartile** | Creative 100% in view for the entire duration of specified quartile(s). | Rate = 100% Viewable Through Qx / Video Measured |
| **50% In-View for n Continuous Sec Impressions** | 50%+ of creative in view for 1-6 continuous seconds (display and video). | Rate = Impressions / Viewability Measured |
| **Audible and In-View on Completion (AVOC)** | 50%+ of creative in view with audio on at video completion. | AVOC Rate = AVOC / Audible Viewable Measured |
| **Audible Impressions** | Impressions with audio turned on for any duration. | Audible Rate = Audible / Audible Measured |
| **Audible Viewable Impressions** | Impressions viewable and with audio on. | Audible Viewable Rate = Audible Viewable / Audible Viewable Measured |
| **Q1-Q4 Viewable/Audible/Audible Viewable Impressions** | Quartile-level breakdowns for viewability, audibility, and combined metrics. | Rate = Qx Impressions / Respective Measured |
| **Average Time (s) - Viewable Impressions** | Average time in seconds of Viewable Impressions. | Avg Time = Total Viewable Time / Viewable Impressions |
| **Average IAB Pixel Standard In-View Time (s)** | Average time the ad was at least 50% in-view (or 30% for large display ads). | - |
| **Display Viewable Time-Based Metrics** | Count at 50% viewable for 1-5, 5-15, or >15 seconds. | Rate = Impressions / Duration Measured |
| **Duration Measured Impressions** | Count for which DV could determine exposure time. | - |
| **Player Size per Quartile** | Width and height of the player at each quartile end, aggregated into size groupings. | - |
| **Quartile Completion Measured Impressions** | Count for which DV could determine quartile completions. | Measurement Rate = Measured / Monitored Ads (Video) |
| **Total Viewable Time (s)** | Total time of viewable impressions. | - |

---

## Co-requisite & Compatibility Rules

These rules govern which dimensions and metrics can be queried together. Violating these rules will cause the query to fail.

### Restricted Dimensions

The following dimensions are restricted to specific metric families. They cannot be combined with general metrics like Monitored Ads, Viewable Impressions, or Authentic Ads.

#### Keyword String
- **Compatible metrics only:** Keyword Incidents, Keyword Blocks, Keyword Filters, Share of Keyword Incidents, Share of Keyword Blocks, Share of Keyword Filters, Keyword Incident Rate, Keyword Block Rate, Keyword Filter Rate, Blocks
- **Incompatible with:** All other metrics (Monitored Ads, Viewable Impressions, rates, etc.)

#### UC Category Name / UC Category Setting / UC Risk Tier
- **Compatible metrics only:** UC-family metrics (UC Incidents, UC Blocks, UC Filters, Share of UC Incidents/Blocks/Filters, UC Incremental Incidents/Blocks/Filters, UC Site/Page/App Incidents/Blocks/Filters), Brand Suitability Incidents/Blocks/Filters, and related keyword/language/site list incident counts
- **Incompatible with:** General metrics (Monitored Ads, Viewable Impressions, Authentic Ads, general rates)

### Co-requisite Dimensions

#### Risk Tier → requires Category Name
Selecting Risk Tier automatically requires Category Name. Choosing Risk Tier without Category Name leads to duplicated data. To deselect Category Name, first deselect Risk Tier.

#### Smart Sentiment Category Risk Tier → requires Smart Sentiment Category Name
Same rule as Risk Tier / Category Name.

### Category-Group Dimensions
Category Name, Smart Sentiment Category Name, and Dynamic Suitability Category Name are compatible with a restricted metric set focused on share-of-traffic analysis: Share of Monitored Ads, Share of Authentic Ads, Share of Requests, Share of Allowed Ads, Share of Blocks, Share of Evaluations, Share of Allowed Evaluations, plus corresponding count metrics (Monitored Ads, Authentic Ads, Requests, Allowed Ads, Blocks, Evaluations, Allowed Evaluations).

### General Dimensions (No Restrictions)
The following dimensions are fully compatible with all metrics: Campaign Name, Advertiser Name, Brand Name, Media Property, Placement Name, Media Type, Device Delivery Type, Delivery Site, Delivery Country, Date, and all Calendar dimensions (Hour, Week, Month, Quarter, Year).

---

## Common Endnotes

1. **Authentic Ads and Authentic Viewable Impressions** are based on customizable campaign-specific settings; services may differ per campaign. Accredited for desktop, mobile web, and mobile app when geographic targeting is not included.
2. **Rate formulas** apply only to campaigns using at least one of: Brand Suitability, IQ Fraud Advanced, or Geo-Targeting.
3. **Viewability rate formulas** apply only to campaigns using viewability and one of: Brand Suitability, Fraud Advanced, Viewability Advanced, or Geo-Targeting.
4. **Not MRC-accredited** metrics are marked with superscript 4. DV undergoes annual audits for re-accreditation.
5. **Geo Targeting** is not MRC-accredited. Location determined using IP address verified by Digital Envoy.
6. **Site & App Fraud/IVT** classification is based on advertising ads served and is not an assessment that the site/app knowingly participated in fraud.
7. **Proprietary Media Gardens** (social platform) metrics are covered in a separate reference.
