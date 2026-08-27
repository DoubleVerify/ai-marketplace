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

### Meta (Facebook, Instagram)

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Meta viewability, Meta fraud, Meta general | 4 | Meta |
| Meta brand suitability for In Stream & MAN | 34 | Meta Brand Suitability - In Stream & MAN |
| Meta brand suitability for Feed, Reels, Threads | 48 | Meta Brand Suitability - Feed, Reels, Threads |

### TikTok

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| TikTok general, TikTok viewability, TikTok fraud | 35 | TikTok |
| TikTok video-level brand suitability incidents | 38 | TikTok Video Incident Reporting |
| TikTok profile-level analysis | 70 | TikTok Profile Incident Reporting |
| TikTok attention, TikTok engagement, TikTok exposure | 73 | TikTok Authentic Attention |

### X (Twitter)

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| X general, X viewability, X fraud, X brand suitability | 6 | X |
| X post-level brand suitability incidents | 46 | X Content Incident Reporting |

### Snapchat

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Snapchat general, Snapchat viewability, Snapchat fraud | 9 | Snapchat |
| Snapchat content-level brand suitability incidents | 67 | Snapchat Content Incident Reporting |
| Snapchat attention, Snapchat engagement | 71 | Snapchat Authentic Attention |

### Pinterest

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Pinterest general, Pinterest viewability, Pinterest fraud | 3 | Pinterest |
| Pinterest content-level brand suitability incidents | 62 | Pinterest Content Incident Reporting |

### Reddit

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Reddit general, Reddit viewability, Reddit fraud | 47 | Reddit |
| Reddit content-level brand suitability incidents | 61 | Reddit Content Incident Reporting |

### Single-Datamart Platforms

| User Asks About | Datamart ID | Datamart Name |
|----------------|-------------|---------------|
| Netflix | 39 | Netflix |
| Instacart | 58 | Instacart |
| LinkedIn | 63 | LinkedIn |
| Spotify | 65 | Spotify |
| Roblox | 68 | Roblox |

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
