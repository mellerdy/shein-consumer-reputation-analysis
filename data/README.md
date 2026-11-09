# Data

This project combines three data sources to analyze SHEIN's media visibility, public attention, and consumer response over time.

## Data Sources

| Source | Study Period | Final Observations | Purpose |
|---|---|---:|---|
| Google News RSS | Jan. 2019–Dec. 2025 | 3,584 headlines | Media volume and ethics-related coverage |
| Google Trends | Jan. 2019–Dec. 2025 | 84 monthly observations | Relative public search interest |
| Google Play Reviews | Jan. 2019–Aug. 2024 | 39,797 reviews | Consumer ratings, sentiment, and review themes |

## Google News

SHEIN-related headlines were collected using the Google News RSS search endpoint with Python.

The collection process divided the full study period into weekly intervals to improve historical coverage.

The raw results included:

- Headline title
- Publication date
- News source
- Article URL

Cleaning included:

- Standardizing dates
- Removing duplicate headlines
- Removing irrelevant results
- Removing source names appended to titles
- Filtering results where "SHEIN" did not refer to the fashion company
- Manual quality checks

The final cleaned dataset contained **3,584 unique SHEIN-related headlines**.

## Google Trends

Monthly Google Trends search-interest data for the term **SHEIN** were collected from January 2019 through December 2025.

The final dataset contains **84 monthly observations**.

Google Trends reports relative search interest on a normalized scale from 0 to 100, so these values represent relative attention rather than absolute search volume.

## Google Play Reviews

Historical Google Play reviews were sourced from:

**ShoppingAppReviews Dataset, Version 2**  
Mendeley Data  
https://data.mendeley.com/datasets/chr5b94c6y/2

Only SHEIN reviews were retained.

After cleaning, the dataset contained **39,797 English-language reviews** spanning January 2019 through August 2024.

The review data were used for:

- Star-rating analysis
- VADER sentiment analysis
- Positive and negative review classification
- Word-frequency analysis
- Consumer-theme analysis

## Data Availability

Large raw datasets are not stored directly in this repository.

The Google News dataset was collected from a live RSS search source, meaning historical results may change over time. The cleaned dataset used for the final analysis was frozen after collection to maintain consistency.

The Google Play review dataset should be obtained directly from the original Mendeley Data source rather than redistributed through this repository.

Processed summaries and analysis outputs may be included where appropriate.
