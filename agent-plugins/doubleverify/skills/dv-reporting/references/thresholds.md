# Metric Thresholds

Normal ranges and investigation triggers for DV measurement domains. Use these to flag anomalies during result interpretation and to set volume floors during query construction.

## Quality Metric Thresholds

| Metric | Normal Range | Investigate If |
|--------|-------------|----------------|
| Viewability Rate | 60-80% | < 50% or > 95% |
| Brand Suitability Rate | 95-99% | < 90% |
| SIVT Rate | 1-5% | > 10% |
| Video Completion Rate | 40-70% | < 20% |
| Block Rate | 5-20% | > 40% |
| Authentic Rate | 70-90% | < 60% |
| Measurement Rate | 80-95% | < 70% |
| Geo Compliance Rate | 90-98% | < 85% |
| GIVT Rate | 0.5-3% | > 5% |

## Attention Metric Thresholds

| Metric | Normal Range | Investigate If |
|--------|-------------|----------------|
| Attention Index | 80-120 | < 50 or > 150 |
| Exposure Index | 80-120 | < 50 or > 150 |
| Engagement Index | 80-120 | < 50 or > 150 |

## Geo Variance

A geo-targeting variance of approximately 7% is normal due to different geo methodologies utilized by each partner. Only flag geo performance if it consistently exceeds this expected variance.

## Volume Floors

The base volume floor is **100,000 Monitored Ads per day**. Scale the floor by the number of days in the query's date range:

**Formula:** `floor = 100,000 × number_of_days`

| Date Range | Floor |
|------------|-------|
| 1 day | 100,000 |
| 7 days (default) | 700,000 |
| 14 days | 1,400,000 |
| 30 days | 3,000,000 |

Apply this scaled floor at all levels (campaign, site/app, placement) when ranking by rate metrics to prevent low-traffic entities from dominating results.
