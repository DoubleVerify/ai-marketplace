# Datamart Routing

Maps user intent to the correct `datamart_id` for `get-datapoint-catalog` and `run-query` calls.

## Routing Table

### Open Web / Standard (Tag-Based)

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Open web, tag-based, standard campaigns, general DV metrics | 1 | Standard |
| Open web geo, geo-targeting, out-of-geo | 99001 | Standard Geo |

### YouTube

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| YouTube general, YouTube viewability, YouTube fraud | 2 | YouTube |
| YouTube video-level incidents, YouTube channel-level brand suitability | 32 | YouTube Video Incident Reporting |

> **Cross-channel note:** The general YouTube datamart (2) includes `Brand Suitability Incident Rate`. However, for video-level or channel-level suitability drill-downs, datamart 32 is required.

### Meta (Facebook, Instagram)

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Meta viewability, Meta fraud, Meta general | 4 | Meta |
| Meta brand suitability for In Stream & MAN | 34 | Meta Brand Suitability - In Stream & MAN |
| Meta brand suitability for Feed, Reels, Threads | 48 | Meta Brand Suitability - Feed, Reels, Threads |

> **Cross-channel note:** The general Meta datamart (4) does **not** contain brand suitability metrics. When running a cross-channel report that includes brand suitability, or a topline performance summary, also query datamarts 34 and 48 to ensure Meta suitability data is included. Both datamarts must be queried to cover the full Meta inventory — 34 covers In Stream & MAN placements, 48 covers Feed, Reels, and Threads.

### TikTok

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| TikTok general, TikTok viewability, TikTok fraud | 35 | TikTok |
| TikTok video-level brand suitability incidents | 38 | TikTok Video Incident Reporting |
| TikTok profile-level analysis | 70 | TikTok Profile Incident Reporting |
| TikTok attention, TikTok engagement, TikTok exposure | 73 | TikTok Authentic Attention |

> **Cross-channel note:** The general TikTok datamart (35) includes `Brand Suitable Rate`. For video-level suitability incident drill-downs, datamart 38 is required.

### X (Twitter)

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| X general, X viewability, X fraud, X brand suitability | 6 | X |
| X post-level brand suitability incidents | 46 | X Content Incident Reporting |

> **Cross-channel note:** The general X datamart (6) includes `Brand Suitability Incident Rate`. For post-level suitability incident drill-downs, datamart 46 is required.

### Snapchat

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Snapchat general, Snapchat viewability, Snapchat fraud | 9 | Snapchat |
| Snapchat content-level brand suitability incidents | 67 | Snapchat Content Incident Reporting |
| Snapchat attention, Snapchat engagement | 71 | Snapchat Authentic Attention |

> **Cross-channel note:** The general Snapchat datamart (9) includes `Brand Suitability Incident Rate`. For content-level suitability incident drill-downs, datamart 67 is required.

### Pinterest

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Pinterest general, Pinterest viewability, Pinterest fraud | 3 | Pinterest |
| Pinterest content-level brand suitability incidents | 62 | Pinterest Content Incident Reporting |

> **Cross-channel note:** The general Pinterest datamart (3) includes `Brand Suitability Incident Rate`. For content-level suitability incident drill-downs, datamart 62 is required.

### Reddit

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Reddit general, Reddit viewability, Reddit fraud | 47 | Reddit |
| Reddit content-level brand suitability incidents | 61 | Reddit Content Incident Reporting |

> **Cross-channel note:** The general Reddit datamart (47) includes `Brand Suitability Incident Rate`. For content-level suitability incident drill-downs, datamart 61 is required.

### Single-Datamart Platforms

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Netflix | 39 | Netflix |
| Instacart | 58 | Instacart |
| LinkedIn | 63 | LinkedIn |
| Spotify | 65 | Spotify |
| Roblox | 68 | Roblox |

> **Cross-channel note:** These platforms have a single datamart each. Brand suitability metrics may not be available on all of them — check the catalog. No additional datamarts are needed.

### Authentic Attention (Cross-Platform)

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Attention, engagement, exposure (non-CTV) | 10 | Authentic Attention |
| Attention, engagement, exposure (CTV only) | 49 | Authentic Attention CTV |

## Routing Rules

1. **Default to the general datamart** for each platform unless the user specifically asks about brand suitability incidents, video/content-level detail, or attention metrics.
2. **If unsure between multiple datamarts**, prefer the general one (lower ID) and mention the specialized option.
3. **Cross-platform questions** that don't name a specific platform default to Standard (ID 1).
4. **Attention questions** route to the Authentic Attention datamarts (10 or 49), not to platform-specific datamarts — unless it's Snapchat (71) or TikTok (73) attention which have dedicated datamarts.
5. **Cross-channel metric completeness.** When the user asks for a cross-channel, topline, or full performance summary — or asks about a specific measurement domain (brand suitability, fraud, viewability) across platforms — query every datamart needed to fully cover that domain for each platform. Do not default to the general datamart alone if it is missing metrics relevant to the user's question. Specifically: if brand suitability is part of the question, query Meta datamarts 34 and 48 in addition to datamart 4, since the general Meta datamart does not include suitability metrics. Do not ask the user whether to check additional datamarts — the cross-channel intent already implies full coverage.
