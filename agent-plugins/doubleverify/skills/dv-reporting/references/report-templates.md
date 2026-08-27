# DV Data API Report Templates Reference

This document lists available report templates by platform. Each template shows its display name, description, dimensions, and metrics. The skill discovers numeric IDs at runtime via `get-datapoint-catalog`, so only display names are listed here.

---

## Standard (Report Type 1)

### Performance Overview
Overview of Key Quality indicators across Viewability, Brand Suitability, Fraud/SIVT and Geo.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Property, Placement Name, Media Type
- **Metrics:** Monitored Ads, Unique Incidents, Measured Impressions, Measurement Rate, Viewable Impressions, Viewable Rate, Authentic Ads, Authentic Rate, Brand Suitability Incidents, Brand Suitability Incident Rate, Fraud/SIVT Incidents, Fraud/SIVT Incident Rate, Out of Geo Incidents, Out of Geo Incident Rate, Requests, Blocks, Block Rate, Brand Suitability Blocks, Brand Suitability Block Rate, Fraud/SIVT Blocks, Fraud/SIVT Block Rate, Out of Geo Blocks, Out of Geo Block Rate, Evaluations, Filters, Filter Rate, Brand Suitability Filters, Brand Suitability Filter Rate, Fraud/SIVT Filters, Fraud/SIVT Filter Rate, Out of Geo Filters, Out of Geo Filter Rate

### Viewability Performance
Detailed Viewability insights, including viewable percent and duration.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Property, Placement Name, Media Type
- **Metrics:** Monitored Ads, Eligible Impressions, Measured Impressions, Measurement Rate, Authentic Ads, Authentic Rate, Authentic Viewable Impressions, Authentic Viewable Rate, Viewable Impressions, Viewable Rate, Authentic Custom Viewable Impressions, Authentic Custom Viewable Rate, Custom Viewable Impressions, Custom Viewable Rate, 100% Display Viewable Impressions, 100% Display Viewable Rate, 50% Display Viewable 1-5 Secs Impressions/Rate, 50% Display Viewable 5-15 Secs Impressions/Rate, 50% Display Viewable >15 Secs Impressions/Rate, Average Time (s) - Viewable Impressions, Total Viewable Time (s)

### Geo Performance
Detailed Geo insights with zip code level granularity.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Placement Name, Media Property, Media Type, Delivery Country, State/Region, Zip Code
- **Metrics:** Monitored Ads, Out of Geo Incidents, Out of Geo Incident Rate, Requests, Out of Geo Blocks, Out of Geo Block Rate, Evaluations, Out of Geo Filters, Out of Geo Filter Rate

### Optimization Opportunities - Monitoring Details
Bi-weekly analysis highlighting Monitoring measurements below set thresholds.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Property, Media Type, Placement Name
- **Metrics:** Monitored Ads, Unique Incidents, Brand Suitability Incidents, UC Incidents, Site & App List Incidents, Language List Incidents, Keyword Incidents, Out of Star Incidents, Out of Age Incidents, App Store Category Incidents, Custom Category Page Incidents, Fraud/SIVT Incidents, Bot Fraud Incidents, Hijacked Devices Incidents, Site Fraud/IVT Incidents, App Fraud/IVT Incidents, Emulator Incidents, Injected Ads Incidents, Data Center Traffic Incidents, Out of Geo Incidents, Measured Impressions, Viewable Impressions, Authentic Viewable Impressions

### Optimization Opportunities - Blocking Details
Bi-weekly analysis highlighting Blocking measurements below set thresholds.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Property, Media Type, Placement Name
- **Metrics:** Requests, Blocks, Brand Suitability Blocks, UC Blocks, Site & App List Blocks, Language List Blocks, Keyword Blocks, Out of Star Blocks, Out of Age Blocks, App Store Category Blocks, Custom Category Page Blocks, New Site Blocks, New App Blocks, No Domain Blocks, Middleware Blocks, Fraud/SIVT Blocks, Bot Fraud Blocks, Hijacked Devices Blocks, Site Fraud/IVT Blocks, App Fraud/IVT Blocks, Emulator Blocks, Injected Ads Blocks, Data Center Traffic Blocks, Out of Geo Blocks

### Optimization Opportunities - Filtering Details
Bi-weekly analysis highlighting Filtering measurements below set thresholds.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Property, Media Type, Placement Name
- **Metrics:** Evaluations, Filters, Brand Suitability Filters, UC Filters, Site & App List Filters, Language List Filters, Keyword Filters, Out of Star Filters, Out of Age Filters, App Store Category Filters, Custom Category Page Filters, New Site Filters, New App Filters, No Domain Filters, Middleware Filters, Fraud/SIVT Filters, Bot Fraud Filters, Hijacked Devices Filters, Site Fraud/IVT Filters, App Fraud/IVT Filters, Emulator Filters, Injected Ads Filters, Data Center Traffic Filters, Out of Geo Filters

### Optimization Opportunities - Summary
Bi-weekly analysis across Monitoring, Blocking and Filtering.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Property, Media Type, Placement Name
- **Metrics:** Combines key metrics from Monitoring Details (Monitored Ads, Unique Incidents, Brand Suitability/Fraud/Geo Incidents, Measured/Viewable/Authentic Viewable Impressions), Blocking Details (Requests, Blocks, Brand Suitability/Fraud/Geo Blocks), and Filtering Details (Evaluations, Filters, Brand Suitability/Fraud/Geo Filters)

### Unsuitable Categories Analysis
UC violations analysis across all traffic.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Property, UC Category Name, UC Category Setting, UC Risk Tier, Category Type
- **Metrics:** Brand Suitability Incidents, UC Incidents, Share of UC Incidents, UC Incremental Incidents, UC Site/Page/App Incidents, Brand Suitability Blocks, UC Blocks, Share of UC Blocks, UC Incremental Blocks, UC Site/Page/App Blocks, Brand Suitability Filters, UC Filters, Share of UC Filters, UC Incremental Filters, UC Site/Page/App Filters

### Category Share of Traffic Analysis
Content Categories analysis.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Property, Category Name, Category Type
- **Metrics:** Monitored Ads, Share of Monitored Ads, Authentic Ads, Share of Authentic Ads, Requests, Share of Requests, Allowed Ads, Share of Allowed Ads, Blocks, Share of Blocks, Evaluations, Share of Evaluations, Allowed Evaluations, Share of Allowed Evaluations

### Monthly Usage Report
Monthly traffic volume.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Type
- **Metrics:** Monitored Ads, Blocks, Filters

### Mobile App Performance
App-level insights.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Media Property, Media Type, Placement Name, Device Delivery Type, App Name, App Bundle, App ID, App Store, App Store Category, Mobile OS
- **Metrics:** Monitored Ads, Unique Incidents, Brand Suitability Incidents, UC App Incidents, Site & App List Incidents, Off App IL Incidents, On App EL Incidents, Language/Keyword Incidents, Out of Age/Star Incidents, App Store Category Incidents, Fraud/SIVT Incidents, App Fraud/IVT Incidents, plus Blocks and Filters equivalents

### CTV Performance
CTV insights.
- **Dimensions:** Device Delivery Type, Advertiser Name, Brand Name, Campaign Name, Media Property, Media Type, Placement Name, CTV Device Name, Universal App Name, App Name, App Bundle, Extracted Bundle ID, Delivery Site, FOS Certification Status
- **Metrics:** Monitored Ads, Authentic Ads, Eligible/Measured/Viewable Impressions, Brand Suitability/Fraud/Geo Incidents, Quartile Completions (Q1-Q4), plus Blocking/Filtering equivalents

### Desktop Performance
Desktop insights.
- **Dimensions:** Device Delivery Type, Advertiser Name, Brand Name, Campaign Name, Media Property, Media Type, Placement Name, Delivery Site
- **Metrics:** Monitored Ads, Unique Incidents, Brand Suitability/UC/Site & App List/Language/Keyword Incidents, Fraud/Site Fraud Incidents, plus Blocks/Filters equivalents

### Smart Sentiment with Opened Scale Analysis
Smart Sentiment Categories analysis.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Device Delivery Type, Category Name, Risk Tier, Smart Sentiment Category Name, Smart Sentiment Category Risk Tier
- **Metrics:** Monitored Ads, Share of Monitored Ads, Authentic Ads, Share of Authentic Ads, Unique Incidents, Requests, Share of Requests, Allowed Ads, Share of Allowed Ads, Blocks, Share of Blocks, Evaluations, Share of Evaluations, Allowed Evaluations, Share of Allowed Evaluations

### UC Smart Sentiment Categories Analysis
UC Smart Sentiment violations.
- **Dimensions:** Advertiser Name, Brand Name, Campaign Name, Device Delivery Type, UC Category Setting, UC Category Name, UC Risk Tier, UC Smart Sentiment Category Name, UC Smart Sentiment Category Risk Tier
- **Metrics:** UC Incidents, Share of UC Incidents, UC Incremental Incidents, UC Site/Page/App Incidents, UC Blocks, Share of UC Blocks, UC Incremental Blocks, UC Site/Page/App Blocks, UC Filters, Share of UC Filters, UC Incremental Filters, UC Site/Page/App Filters

---

## YouTube (Report Type 2)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Buying Platform, Platform Inventory Type, Media Type, Platform Ad Group ID, Platform Ad Group Name

### Performance Overview
- **Metrics:** Monitored Ads, Viewability Measured Impressions, Viewability Measurement Rate, BS Measured Impressions, BS Measurement Rate, Authentic Ads, Authentic Rate, Unique Incidents, Unique Incident Rate, BS Incidents, BS Incident Rate, Brand Risk Floor Incidents, Brand Risk Floor Incident Rate, Fraud Incidents, Fraud Incident Rate, Viewable Impressions, Viewable Rate, Authentic Viewable Impressions, Authentic Viewable Rate

### Brand Suitability Performance
- **Metrics:** BS Monitored Ads, BS Measured Impressions, BS Measurement Rate, BS Incidents, BS Incident Rate, Brand Risk Floor Incidents, Brand Risk Floor Incident Rate, UC Incidents, UC Incident Rate, Industry Defined Suitability Incidents, Industry Defined Suitability Incident Rate

### Viewability Performance
- **Metrics:** Monitored Ads, Viewability Measured Impressions, Viewability Measurement Rate, Viewable Impressions, Viewable Rate, Authentic Viewable Impressions, Authentic Viewable Rate

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Quartile 1/2/3/4 Completions

### Monthly Usage Report
- **Metrics:** Monitored Ads

---

## Pinterest (Report Type 3)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Pinterest Standard Impressions, Pinterest Standard Authentic Ads, Pinterest Standard Authentic Rate, Unique Incidents, Unique Incident Rate, BS Incidents, BS Incident Rate, Viewable Impressions, Viewable Rate

### Brand Suitability Performance
- **Metrics:** Pinterest Standard Impressions, BS Measured Impressions, BS Measurement Rate, BS Incidents, BS Incident Rate

### Viewability Performance
- **Metrics:** Pinterest Standard Impressions, Passthrough Impressions, Passthrough Rate, Viewable Impressions, Viewable Rate

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Quartile Completions

### Monthly Usage Report
- **Metrics:** Pinterest Standard Impressions

---

## Meta (Report Type 4)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Meta Standard Ads - Net, Total Net Ads, Total Net Rate, Viewable Impressions, Viewable Rate, Total Net Viewable Impressions, Total Net Viewable Rate, Passthrough Impressions, Passthrough Rate

### Viewability Performance
- **Metrics:** Meta Standard Ads - Net, Total Net Ads, Total Net Rate, Viewable Impressions, Viewable Rate, Total Net Viewable Impressions, Total Net Viewable Rate

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Quartile Completions

### Monthly Usage Report
- **Metrics:** Meta Standard Ads - Net

---

## X (Report Type 6)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Monitored Ads, Brand Suitability Measured Ads, BS Measurement Rate, Viewability Measured Ads, Authentic Ads, Authentic Rate, Unique Incidents, BS Incidents, BS Incident Rate, Viewable Impressions, Viewable Rate

### Brand Suitability Performance
- **Metrics:** Brand Suitability Measured Ads, BS Measurement Rate, BS Incidents, BS Incident Rate

### Viewability Performance
- **Metrics:** Viewability Measured Ads, Viewable Impressions, Viewable Rate

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Quartile Completions

### Monthly Usage Report
- **Metrics:** Monitored Ads

---

## Snapchat (Report Type 9)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Monitored Ads, Authentic Ads, Authentic Rate, Unique Incidents, BS Incidents, BS Incident Rate, Out of Geo Incidents, Out of Geo Incident Rate, Viewable Impressions, Viewable Rate

### Brand Suitability Performance
- **Metrics:** Monitored Ads, BS Measured Impressions, BS Measurement Rate, BS Incidents, BS Incident Rate

### Viewability Performance
- **Metrics:** Monitored Ads, Viewable Impressions, Viewable Rate, Audible Viewable Measured Impressions

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Quartile Completions

### Monthly Usage Report
- **Metrics:** Monitored Ads

---

## Authentic Attention (Report Type 10)

Common dimensions: Advertiser Name, Brand Name, Campaign Name, Media Property, Placement Name, Media Type

### Attention Overview
- **Metrics:** Attention Index, Engagement Index, Exposure Index, Indexed Impressions, High Exposure High Engagement, High Exposure Low Engagement, Low Exposure High Engagement, Low Exposure Low Engagement

### Mobile App Analysis
- **Metrics:** Attention Index, Engagement Index, Exposure Index, Indexed Impressions (by app-level dimensions)

### Engagement Analysis
- **Metrics:** Engagement Index, Ad Interaction Index, User Presence Index, Screen Engagement, Touch Engagement, Audio Engagement, Playback Engagement

### Exposure Analysis
- **Metrics:** Exposure Index, Intensity Index, Prominence Index, AVOC Impressions, AVOC Rate, Audible Impressions, Audible Rate, Quartile 1/2/3/4 Completions

### Delivery Site Analysis
- **Metrics:** Attention Index, Engagement Index, Exposure Index, Indexed Impressions (by delivery site)

### Video Analysis
- **Metrics:** Exposure Index, Intensity Index, Prominence Index, AVOC Impressions, AVOC Rate, Audible Impressions, Audible Rate, Quartile 1/2/3/4 Completions

---

## TikTok (Report Type 35)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Monitored Ads, Authentic Ads, Authentic Rate, Unique Incidents, BS Incidents, BS Incident Rate, Viewable Impressions, Viewable Rate

### Brand Suitability Performance
- **Metrics:** Monitored Ads, BS Measured Impressions, BS Measurement Rate, BS Incidents, BS Incident Rate, Pre-Bid BS Incidents, Pre-Bid BS Incident Rate, Non Pre-Bid BS Incidents, Non Pre-Bid BS Incident Rate

### Viewability Performance
- **Metrics:** Monitored Ads, Viewable Impressions, Viewable Rate

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, Audible Viewable Measured Impressions, AVOC Impressions, AVOC Rate, Quartile Completions

### Monthly Usage Report
- **Metrics:** Monitored Ads

### TikTok Prebid Report
- **Metrics:** Pre-Bid BS Incidents, Pre-Bid BS Incident Rate, Non Pre-Bid BS Incidents, Non Pre-Bid BS Incident Rate

---

## Netflix (Report Type 39)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Monitored Ads, Authentic Ads, Authentic Rate, Viewable Impressions, Viewable Rate, 100% Viewable Impressions, 100% Viewable Rate

### Viewability Performance
- **Metrics:** Monitored Ads, Measured Impressions, Measurement Rate, Viewable Impressions, Viewable Rate, 100% Viewable Impressions, 100% Viewable Rate

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Quartile Completions

### Monthly Usage Report
- **Metrics:** Monitored Ads

---

## Reddit (Report Type 47)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Reddit Standard Ads, Monitored Ads, Authentic Ads, Authentic Rate, Unique Incidents, BS Incidents, BS Incident Rate, Viewability Monitored Impressions, Viewable Impressions, Viewable Rate, 100% Viewable Impressions, 100% Viewable Rate

### Brand Suitability Performance
- **Metrics:** Monitored Ads, BS Measured Impressions, BS Measurement Rate, BS Incidents, BS Incident Rate

### Viewability Performance
- **Metrics:** Viewability Monitored Impressions, Measured Impressions, Measurement Rate, Viewable Impressions, Viewable Rate, 100% Viewable Impressions, 100% Viewable Rate

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Quartile Completions

### Monthly Usage Report
- **Metrics:** Reddit Standard Ads, Monitored Ads

---

## Instacart (Report Type 58)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Monitored Ads, Authentic Ads, Authentic Rate, Viewable Impressions, Viewable Rate, 100% Viewable Impressions, 100% Viewable Rate

### Viewability Performance
- **Metrics:** Monitored Ads, Measured Impressions, Measurement Rate, Viewable Impressions, Viewable Rate, 100% Viewable Impressions, 100% Viewable Rate, 50% Display Viewable 1-5 Secs Impressions/Rate, 50% Display Viewable 5-15 Secs Impressions/Rate, 50% Display Viewable >15 Secs Impressions/Rate

### Monthly Usage Report
- **Metrics:** Monitored Ads

---

## LinkedIn (Report Type 63)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Monitored Ads, Authentic Ads, Authentic Rate, Viewable Impressions, Viewable Rate

### Viewability Performance
- **Metrics:** Monitored Ads, Measured Impressions, Measurement Rate, Viewable Impressions, Viewable Rate

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Completed and Viewable Impressions per Quartile (Q1-Q4)

### Monthly Usage Report
- **Metrics:** Monitored Ads

---

## Spotify (Report Type 65)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Monitored Ads, Authentic Ads, Authentic Rate, Viewable Impressions, Viewable Rate

### Viewability Performance
- **Metrics:** Monitored Ads, Measured Impressions, Measurement Rate, Viewable Impressions, Viewable Rate, Audibility Eligible Impressions

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Completed and Viewable Impressions per Quartile (Q1-Q4)

### Monthly Usage Report
- **Metrics:** Monitored Ads

---

## Roblox (Report Type 68)

Common dimensions: Advertiser Name, Brand Name, Vendor Client ID, Platform Account ID, Platform Account Name, Platform Campaign ID, Platform Campaign Name, Media Type

### Performance Overview
- **Metrics:** Monitored Ads, Authentic Ads, Authentic Rate, Viewable Impressions, Viewable Rate

### Viewability Performance
- **Metrics:** Monitored Ads, Measured Impressions, Measurement Rate, Viewable Impressions, Viewable Rate, Audibility Eligible Impressions

### Video Performance
- **Metrics:** Audible Impressions, Audible Rate, AVOC Impressions, AVOC Rate, Completed and Viewable Impressions per Quartile (Q1-Q4)

### Monthly Usage Report
- **Metrics:** Monitored Ads
