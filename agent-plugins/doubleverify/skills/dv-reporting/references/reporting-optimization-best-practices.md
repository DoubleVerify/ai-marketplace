# Reporting and Optimization Best Practices

> Guidelines that advertisers and partners can implement to improve campaign performance for standard tag-based campaigns.

---

## Table of Contents

1. [Reporting Overview](#reporting-overview)
2. [Brand Suitability Best Practices](#brand-suitability-best-practices)
   - [High Blocks/Filters and Incidents Due to Unsuitable Categories](#high-blocksfilters-and-incidents-due-to-unsuitable-categories)
   - [High Blocks/Filters and Incidents Due to Site or App List Violations](#high-blocksfilters-and-incidents-due-to-site-or-app-list-violations)
   - [High Blocks/Filters and Incidents Due to Language](#high-blocksfilters-and-incidents-due-to-language)
   - [High Blocks/Filters and Incidents Due to Keywords](#high-blocksfilters-and-incidents-due-to-keywords)
   - [High Blocks/Filters and Incidents Due to Out-of-Star/Out-of-Age/App Store Category](#high-blocksfilters-and-incidents-due-to-out-of-starout-of-ageapp-store-category)
3. [Viewability Best Practices](#viewability-best-practices)
4. [Geo Best Practices](#geo-best-practices)
5. [Fraud/SIVT Best Practices](#fraudsivt-best-practices)
   - [High Blocks/Filters and Incidents Due to Site/App Fraud](#high-blocksfilters-and-incidents-due-to-siteapp-fraud)
   - [High Blocks/Filters and Incidents Due to Bot Fraud](#high-blocksfilters-and-incidents-due-to-bot-fraud)
   - [High Blocks/Filters and Incidents Due to Data Center Traffic](#high-blocksfilters-and-incidents-due-to-data-center-traffic)
   - [High Blocks/Filters and Incidents Due to Injected Ads](#high-blocksfilters-and-incidents-due-to-injected-ads)
   - [High Incidents Due to Emulators](#high-incidents-due-to-emulators)
   - [High Blocks/Filters and Incidents Due to Hijacked Devices](#high-blocksfilters-and-incidents-due-to-hijacked-devices)

---

## Reporting Overview

Advertisers, agencies, and partners can access their campaign reporting under the **Analytics** section within DV's Pinnacle platform:

- **Quality tab** — Evaluates the quality of each DV-tagged ad in easy-to-read data visualizations and views.
- **Report Builder tab** — Allows you to create customized reports with all the data points you need to evaluate campaign performance and schedule them to be delivered at your chosen cadence.

**Best practices:**

- Review reporting frequently (daily or weekly) to investigate performance outside of performance recaps sent by your DV Support Team. This allows you to anticipate potential troubleshooting scenarios and proactively implement optimizations.
- Throughout the campaign flight, set up automated reporting to be sent on a daily or weekly basis to partners for optimizations that align with your brand suitability, fraud, geo, and viewability benchmarks.

### Optimization Overview

When reviewing Quality and Report Builder reporting, it is important to identify areas where the majority of blocks, filters, and incidents are occurring. By narrowing down the sources of these issues, advertisers and partners can more effectively target their optimization efforts and improve campaign performance.

---

## Brand Suitability Best Practices

For standard tag-based campaigns, advertisers and partners can perform the following actions to improve campaign performance.

### High Blocks/Filters and Incidents Due to Unsuitable Categories

**What happens:** Pages, sites, or apps get flagged, blocked, and/or filtered when they fail to meet the campaign's category settings. DV's brand suitability solution assesses both the content type and topic, analyzing the theme and context in which it appears to determine overall risk effectively.

**Best practices:**

- **Avoiding Page URL Optimization** — Reviewing thousands of URLs is not an effective approach when pages are constantly refreshed and moving in and out of the news cycle. Reviewing URL data after the fact may not be the most efficient method, as the flagged pages may have minimal traffic and new pages may have surfaced.
- **Review your campaign settings** — When discussing campaign settings with partners, the desired outcome is that the partner either targets away from the content or that the client agrees to modify their settings to better align with their brand preferences and specific partner's campaign.
- **Partner to align targeting with client settings** — Once the client confirms their settings are accurate, the partner should make the necessary changes within their targeting systems. If the client needs to adjust their settings, there are DV settings that they can customize to their unique needs.
- **Educate the partner on the type of content being flagged** — Providing definitions and insights into what type of content would fall into those unsuitable categories would help the partner with their investigations and targeting adjustments.

**DV recommendations:**

- **For Open Web programmatic buys through DSPs** (e.g., The Trade Desk, Amazon DSP, DV360), the first step is to review whether **ABS pre-bid segments are already applied** on campaigns showing elevated Brand Suitability Incident Rates. If ABS is not yet active, enabling it is the highest-impact lever for reducing post-bid incidents. If ABS is already active, the elevated rate may indicate a need to review category settings or investigate specific content categories driving the incidents.
- For programmatic campaigns without ABS, implement **Authentic Brand Suitability (ABS)** which deploys brand suitability settings across multiple DSPs via a single pre-bid avoidance segment. This ensures that any ad that might get flagged, prevented, or blocked in post-bid for a brand suitability infraction can be avoided in pre-bid.
- Add a page to a **page exceptions list** where DV will no longer flag unsuitable categories at a page level. Commonly used to override DV's classification on a trusted partner's homepages or section pages.
- Add a site to a **site exceptions list** where DV will no longer flag unsuitable categories at a site and page level. Keyword monitoring, blocking, and filtering will still apply.
- Add an app to an **app exceptions list** where DV will allow apps you deem appropriate even if they would be considered unsuitable based on your app content settings.
- Optimizing away from the sites, pages, and apps requires no action on your blueprint settings but can eliminate scale and intended audience.
- Create a **specific brand suitability profile** for the partner in question that allows them to run partner-specific settings.
- Partners can review if there are specific sections of their site or app that are more prone to Brand Suitability violations and target campaigns away from those sections.
- Partners can also identify if they have article-level contextual tagging that they can use to target campaigns based on the advertiser's avoidance settings.

### High Blocks/Filters and Incidents Due to Site or App List Violations

**What happens:** Ads get flagged, blocked, and/or filtered for serving on sites or apps that are on your exclusion list or off your inclusion list.

**Best practices:**

- Review your inclusion or exclusion list regularly to ensure it aligns with the advertisers' brand suitability goals.

**DV recommendations:**

- Implement **Authentic Brand Suitability (ABS)** for programmatic campaigns to deploy pre-bid avoidance.
- Partners can optimize away from the flagged, blocked, and/or filtered sites or apps.
- Clients can update their inclusion/exclusion list if they decide that a site or app is no longer required to be on the list.

### High Blocks/Filters and Incidents Due to Language

**What happens:** Ads get flagged, blocked, and/or filtered for serving in languages listed in your language exclusion list or not on your language inclusion list.

**Best practices:**

- Review your language inclusion or exclusion list regularly to ensure it aligns with the advertisers' brand suitability goals.

**DV recommendations:**

- Implement **Authentic Brand Suitability (ABS)** for programmatic campaigns.
- Partners can optimize away from inventory across languages that do not meet your language exclusion/inclusion list.

### High Blocks/Filters and Incidents Due to Keywords

**What happens:** Ads get flagged, blocked, and/or filtered from serving on pages whose URLs contain keyword strings on your keyword list.

**Best practices:**

- Custom keyword lists should be specific to your brand and contain words or phrases that have a negative association with your advertiser (such as scandals, negative world news, recalls, etc.). Swear words and other generally undesirable terms do not need to be included as they can be captured by DV's Inappropriate Content Categories.
- Use extra caution in selecting keywords that could be interpreted in many different ways. Since this solution functions by analyzing keywords within a page URL, the context of keyword matches is not taken into account. Instead, consider brand-specific terms, names of personnel, or past spokespeople.

**DV recommendations:**

- Implement **Authentic Brand Suitability (ABS)** for programmatic campaigns.
- Review keyword lists and ensure they are in the correct format, terms, and intentions:
  - **Broad match** (default) — Will flag, block, and/or filter URLs containing any match of the words in the keyword string in any order.
  - **Exact match** — Uses quotes at the beginning and end of the keyword string and will flag, block and/or filter URLs containing an exact match based on the order of the words.
    - **Note:** If spaces are left out of the quotes at the beginning or end of the keyword string, the first word can match a partial word within a URL.
- Consider limiting the use of keywords that contain **four or fewer characters**. These terms can result in elevated incident, block, and/or filter rates unless you include quotes and spaces around the word. For example, the word `war` can be found in hundreds of words (e.g., warehouse, housewarming). To flag it as an exact match, use `" war "`.
- Partners can optimize away from flagged pages by pulling keyword reports and cross-referencing them with their internal reporting to see where the keywords are showing up within URLs.

### High Blocks/Filters and Incidents Due to Out-of-Star/Out-of-Age/App Store Category

**What happens:** A mobile app ad does not meet the app star rating/app age rating/app store category settings in your brand suitability settings.

**Best practices:**

- **Review your campaign settings** — The desired outcome is that the partner either targets away from the app content or the client agrees to modify their settings.
- **Partners to align targeting with clients' settings** — Once clients confirm their settings are accurate, partners should make necessary changes within their targeting systems.
- **Educate the partner on the type of app being flagged** — Providing definitions and insights into what type of app falls under each app store category can help partners with investigations and targeting adjustments.

**DV recommendations:**

- Implement **Authentic Brand Suitability (ABS)** for programmatic campaigns.
- Add an app to an **App Exceptions List** which overrides apps that have an App Star Review or Age Rating that clients elected for monitoring or blocking.
  - **Note:** This works with App Star Reviews and App Age Ratings services only.
- Optimizing away from apps requires no action on your blueprint settings but can eliminate scale and intended audience.
- Create a **specific brand suitability profile** for the partner in question.

---

## Viewability Best Practices

### Low Viewability Rate

**What happens:** Ads are not viewable based on IAB standards or a custom threshold.

- **IAB Standard Display Viewability:** 50% of ad pixels viewed for 1 consecutive second.
- **IAB Standard Video Viewability:** 50% of pixels in view for 2 consecutive seconds or more.

**DV recommendations:**

- Review viewability performance by device environment and optimize towards devices with higher viewability.
- Review viewability performance by sites or apps and optimize towards top sites or apps with higher viewability and volume.
- Review viewability performance at a placement level and optimize away from low viewability placements.
- Implement pre-bid viewability segments on programmatic campaigns to optimize toward a certain viewability threshold.

### CTV Viewability Recommendations

- Ensure the CTV partner is providing the app bundle on 100% of the impressions being served. If you are experiencing low app bundle transparency, reach out to your DV Support team to modify your tags to pass through the app bundle via the macro.
- Ensure the CTV buy is serving on **Fully On Screen-certified** inventory.
- Review the viewability performance by CTV app name and app bundle, then optimize towards CTV inventory with higher viewability.
- Review app performance by looking at the app transparency rate and **Verified Streaming TV** rate to further troubleshoot and optimize viewability.
- Investigate the **Fully On-Screen Status Distribution** chart in the Video & CTV Dashboard for further troubleshooting.
- Reach out to your DV Support team for further assistance in troubleshooting viewability on your CTV buys.

---

## Geo Best Practices

### High Blocks/Filters and Incidents Due to Out-of-Geo

**What happens:** Ads are served outside of the designated geo-targeting area.

**Best practices:**

- Ensure partners are targeting within the designated geo parameters.
- It is normal to see around **7% geo-targeting variance** due to different geo methodologies utilized by each partner.

**DV recommendations:**

- DV's reporting tools can provide insights into which Internet Service Providers (ISPs) have the highest out-of-geo rates. This information can be used to optimize away from these ISPs. Reach out to your DV Support Team for more information.
- When using **Server-Side Ad Delivery**, the Publisher/SSAI partner can enable DV to accurately measure the end user's location instead of the server's location by passing the end user's IP address via the **X-Forwarded-For (XFF)** field on all traffic.
- Partners can review DV's performance reporting and make adjustments to their backend suppliers and targeting attributes.

---

## Fraud/SIVT Best Practices

### High Blocks/Filters and Incidents Due to Site/App Fraud

**What happens:** Ads get served on sites or apps that DV has classified as fraudulent. Sites and Apps Fraud/IVT are sites and/or apps that are currently or historically associated with indications of ad impression fraud or invalid traffic practices, such as spoofing, laundering, hidden ads, nonhuman bot traffic, or other forms of IVTs.

**DV recommendations:**

- Implement **site or app-based IVT avoidance segments** where the declared auction domains (site fraud) and auction bundle IDs (app fraud) are compared against the Site and App Fraud Lists and avoid classified inventory.
- If monitoring only, enabling **filtering** can prevent site or app fraud based on detected domains (site fraud) and bundle IDs (app fraud).
- If monitoring only, enabling **blocking** can block site or app fraud based on detected domains and bundle IDs.
- DV can segment performance data, identify infected supply source line items, and perform supply optimizations to eliminate IVT inventory. This is the primary form of prevention.
- DV provides insight into sites or app bundle IDs with the highest site or app fraud. Optimizing away from them is essential to minimize wasted spend and maximize campaign effectiveness.

### High Blocks/Filters and Incidents Due to Bot Fraud

**What happens:** Ads get served to a fraudulent bot which involves spoofing of BundleID, IP address, User-Agent, etc.

**DV recommendations:**

- Implement **device-based IVT avoidance segments** which can avoid bot fraud. (Exceptions: Session-Based Bot Fraud and Bot Fraud where the Auction IP or User-Agent is spoofed.)
- If monitoring only, enabling **filtering** can prevent several bot fraud schemes. However, some schemes may require data telemetries for detection confirmation that are not provided in filtration data gathering.
- If monitoring only, enabling **blocking** can block mostly all bot fraud schemes.
- DV can segment performance data, identify infected supply source line items, and perform supply optimizations to eliminate IVT inventory.
- DV's **Fraud Lab** can identify specific bot fraud schemes impacting the inventory and provide a POV.

### High Blocks/Filters and Incidents Due to Data Center Traffic

**What happens:** Ads originate from data center traffic fraud. Non-human data center traffic ads originate from facilities used for housing computers and server systems, such as traffic originating from a cloud computing center. While non-human data center traffic is not necessarily fraudulent or malicious traffic, it is considered invalid by the IAB because it represents ads that are not served to a human user. DV detects non-human data center traffic by capturing the IP address and comparing it to the DV list of data centers generating non-human traffic (using a combination of third-party sources along with proprietary algorithms).

**DV recommendations:**

- Implement **device-based IVT pre-bid avoidance segments** to avoid ads with IPs associated with both GIVT and SIVT Data Center Traffic. (Exceptions: This segment does not apply to incidents where the Auction IP is spoofed.)
- If monitoring only, enabling **filtering** prevents all ad evaluations with IPs associated with SIVT Data Center Traffic.
  - **Note:** DV currently does not filter on GIVT Data Center Traffic.
- If monitoring only, enabling **blocking** prevents all ad requests with IPs associated with both GIVT and SIVT Data Center Traffic.
- DV can segment performance data, identify infected supply source line items, and perform supply optimizations to eliminate IVT inventory.
- DV provides insight into IPs and Internet Service Providers (ISPs) with the highest Data Center Traffic rates. Optimizing away from them is essential to minimize wasted spend.

### High Blocks/Filters and Incidents Due to Injected Ads

**What happens:** Ads are identified as injected ads. Injected ads are those that do not originate from a publisher's web page, mobile application, or inventory monetization partners. Injected Ads are inserted into the user's web or app experience via browser toolbars or extensions, network-level insertion, or adware/malware by third parties not associated with the content publisher.

**DV recommendations:**

- Ad Injection is a session-based IVT and is **mostly unavoidable**. However, once a device is identified to contain adware/malware, those devices can be avoided with **device-based IVT pre-bid avoidance segments**. (Exceptions: Emulators where the Auction IP or User-Agent is spoofed.)
- If monitoring only, enabling filtering and blocking can prevent and block ad injection on Desktop and Mobile-Web Traffic.
  - **Note:** In-App and CTV are usually not susceptible to injected ads.
- DV can segment performance data, identify infected supply source line items, and perform supply optimizations to eliminate IVT inventory.
- DV's **Fraud Lab** can identify specific bot fraud schemes impacting the inventory and provide a POV.

### High Incidents Due to Emulators

**What happens:** The Emulator IVT type is an impression-level detector for situations where the device on which the ad was served has been misrepresented; this typically happens when a seller misrepresents a lower-priced environment like mobile or desktop for a higher-priced environment like CTV. This traffic may also be the result of testing flows, when users (or nonhuman users) use software in one environment to test ads in a different environment.

**DV recommendations:**

- Emulators are session-based fraud and are **generally unavoidable**. However, once emulator devices are identified, those devices can be avoided with **device-based IVT avoidance segments**.
- DV can segment performance data, identify infected supply source line items, and perform supply optimizations to eliminate IVT inventory. This is a primary form of prevention.
- DV's **Fraud Lab** can identify specifics of the emulator that is impacting the client's inventory and provide a POV.

### High Blocks/Filters and Incidents Due to Hijacked Devices

**What happens:** Ads get served on browsers infected with adware/malware, both a mix of Injected Ads and events originating from the publisher.

**DV recommendations:**

- Implement **device-based IVT avoidance segments** which will avoid ADIDs associated with Hijacked Device traffic. (Exceptions: If avoiding an ADID that is being manipulated would result in a high volume of false positives, DV will not avoid this traffic and it will be considered Unavoidable IVT.)
- If monitoring only, enabling filtering and blocking can prevent and block Hijacked Devices.
- DV can segment performance data, identify infected supply source line items, and perform supply optimizations to eliminate IVT inventory.
- DV's **Fraud Lab** can identify specific hijacked device schemes impacting the inventory and provide a POV.
