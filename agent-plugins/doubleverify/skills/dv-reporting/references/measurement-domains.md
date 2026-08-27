# DV Measurement Domains

## Overview

DoubleVerify measures digital advertising across four core domains.

## Measurement Domains

### 1. Brand Safety & Suitability

Evaluates whether ad placements appear alongside content that aligns with the advertiser's brand values.

**Key concepts:**
- **Brand Safety** (Open Web/TAG_BASED): Binary — content is safe or has an incident
- **Brand Suitability** (YouTube, social): Graduated scale — unsuitable to fully suitable
- **HSC (High Severity Category)**: Content categories flagged as unsafe (e.g., adult, violence, hate speech)
- **Custom Avoidance**: Advertiser-defined keyword/category blocking rules

**Key metrics:**
- Brand Safety Rate = (monitored - incidents) / monitored x 100
- Brand Safety Incident Rate = incidents / monitored x 100
- Unsuitable Incidents (YouTube/social)

**Key dimensions:** Content category, site/domain, custom avoidance category

### 2. Fraud / Invalid Traffic (IVT)

Detects non-human or fraudulent traffic.

**Key concepts:**
- **GIVT (General Invalid Traffic)**: Known bots, data center traffic — pre-filtered, not billed
- **SIVT (Sophisticated Invalid Traffic)**: Bot traffic mimicking human behavior — flagged post-measurement
- **MRC accredited**: DV's fraud detection is MRC-accredited

**Key metrics:**
- SIVT Rate = sivt_incidents / monitored x 100
- GIVT Rate = givt_impressions / monitored x 100
- Total IVT Rate = (SIVT + GIVT) / monitored x 100

**Key dimensions:** Fraud type, device type, environment

### 3. Viewability & Exposure

Measures whether ads were actually viewable to users per MRC/IAB standards.

**Key concepts:**
- **MRC Standard**: 50% of pixels in view for 1 second (display) or 2 seconds (video)
- **GroupM Standard**: 100% of pixels in view
- **Measured vs Monitored**: "Measured" = DV could determine viewability; "Monitored" = DV saw the impression
- **Video Completion**: Quartile tracking (Q1-Q4) for video ads

**Key metrics:**
- Viewability Rate = viewable / measured x 100
- Video Completion Rate = Q4_completed / Q1_started x 100
- Time in View (seconds)
- AVOC (Audible & Viewable on Completion) for video

**Key dimensions:** Device type, media type (display/video), environment (web/app)

### 4. Authentic Attention

DV's proprietary metric combining exposure and engagement signals.

**Key concepts:**
- **Exposure Index** (0-100): Viewability-based score
- **Engagement Index** (0-100): User interaction signals
- **Attention Index** (0-100): Composite of exposure + engagement
- Only available for AA-eligible impressions (subset of total monitored)

**Key metrics:**
- Authentic Attention Index
- Authentic Exposure Index
- Authentic Engagement Index
- Authentic Rate = authentic_ads / monitored x 100

**Key dimensions:** Device type, media type, creative size

## Pre-Bid vs Post-Bid

| Aspect | Pre-Bid (Blocking/Filtering) | Post-Bid (Monitoring) |
|--------|------------------------------|----------------------|
| When | Before ad serves | After ad serves |
| Action | Block/filter the request | Measure and report |
| Data | Requests, blocks, allowed | Impressions, incidents |
| Purpose | Prevention | Measurement & verification |

## Entity Hierarchy

```
Finance Advertiser (billing rollup)
  └─ Advertiser (brand)
       └─ LOB / Line of Business (Salesforce Account)
            └─ Campaign (measurement unit)
                  └─ Media Property (publisher/platform placement)
```

## Platform Classification

| Platform | Type | Base Monitored Metric |
|----------|------|----------------------|
| Open Web | TAG_BASED (JavaScript tag) | Monitored Ads |
| Facebook/Meta | Social (API) | Net Impressions (= Monitored Impressions) |
| Instacart | Social (API) | Monitored Ads |
| LinkedIn | Social (API) | Monitored Ads |
| Netflix | Social (API) | Monitored Ads |
| Pinterest | Social (API) | Net Ads (= Monitored Ads) |
| Reddit | Social (API) | Net Impressions (= Monitored Ads) |
| Roblox | Social (API) | Net Impressions (= Monitored Impressions) |
| Snapchat | Social (API) | Net Ads (= Monitored Ads) |
| Spotify | Social (API) | Monitored Ads |
| TikTok | Social (API) | Net Impressions (= Monitored Impressions) |
| Twitter/X | Social (API) | Monitored Ads |
| YouTube | Social (API) | Monitored Ads |

## Common Terminology

| Term | Definition |
|------|------------|
| Impression | A single instance of an ad being served |
| Incident | An impression flagged for brand safety/suitability violation |
| CTV | Connected TV |
| OM SDK | Open Measurement SDK |
| DSP | Demand-Side Platform |
| Ad Server | System delivering ads (e.g., Google Campaign Manager, Sizmek) |
