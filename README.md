# SHEIN Consumer Reputation Analysis

## Overview

SHEIN has grown into one of the most visible fast fashion brands in the world while facing increasing scrutiny around labor practices, environmental sustainability, intellectual property, and supply chain transparency.

This project asks a broader business question:

**Can consumer appeal persist even as reputational and ethical scrutiny increases?**

To explore that question, I combined media coverage, public search behavior, and consumer review data to examine how SHEIN's visibility, reputation, and consumer response changed from 2019 through 2025.

The project focuses on the difference between three signals that do not always move together:

- **Media scrutiny**
- **Public attention**
- **Consumer evaluation**

## Business Questions

The analysis addresses five main questions:

1. How did SHEIN related media coverage change from 2019 to 2025?
2. How did ethics related coverage change as SHEIN became more visible?
3. Was greater ethical scrutiny associated with increased public search interest?
4. Did consumer ratings and sentiment decline during periods of greater controversy?
5. Did media scrutiny show any delayed relationship with consumer response?

## Data Sources

The project integrates three datasets:

| Data Source | Period | Observations | Purpose |
|---|---|---:|---|
| Google News RSS | 2019 to 2025 | 3,584 headlines | Media volume and ethics related coverage |
| Google Trends | 2019 to 2025 | 84 months | Relative public search interest |
| Google Play Reviews | 2019 to Aug. 2024 | 39,797 reviews | Ratings, sentiment, and consumer themes |

Google News headlines were collected using Python and the Google News RSS endpoint. Historical Google Play reviews were sourced from the ShoppingAppReviews dataset published through Mendeley Data.

## Methods

### Data Collection and Cleaning

Google News data were collected in weekly intervals to improve historical coverage. The resulting headlines were cleaned by:

- Standardizing publication dates
- Removing duplicate headlines
- Filtering irrelevant search results
- Removing source names from headline text
- Checking that SHEIN referred to the fashion company
- Freezing the cleaned dataset for consistent analysis

### Ethics Related Media Classification

Headlines were classified using a manually constructed keyword dictionary covering four areas:

- Labor and working conditions
- Environment and sustainability
- Intellectual property
- Supply chain and regulation

The classification used whole word and phrase matching and was refined through manual inspection.

### Consumer Sentiment Analysis

Google Play reviews were analyzed using **VADER sentiment analysis**.

Each review received a sentiment score and was categorized as positive, neutral, or negative. Star ratings were analyzed alongside sentiment scores to compare numerical ratings with the tone of written consumer feedback.

### Text Analysis

Positive and negative reviews were analyzed separately using word frequency analysis.

Common positive themes included:

- Quality
- Price
- Sizing
- Ease of use
- Shipping and delivery

Common negative themes included:

- Orders
- Customer service
- Refunds and returns
- Delivery problems
- Money and payment issues

### Integrated Analysis

All three datasets were aggregated to the monthly level and merged using a common year and month variable.

The analysis included:

- Descriptive statistics
- Pearson correlation analysis
- One month lag analysis
- Period comparisons
- Sentiment analysis
- Word frequency analysis
- Data visualization

## Key Findings

### 1. SHEIN's media visibility increased substantially

SHEIN related news coverage increased from only **10 cleaned headlines in 2019** to **1,356 headlines in 2025**.

Ethics related topics also became a larger part of SHEIN's media coverage over time.

### 2. Ethical scrutiny increased alongside public attention

Ethics related media share was positively associated with Google search interest:

**r = 0.450, p < .001**

This suggests that months with greater ethical scrutiny also tended to have greater public search attention.

Controversy therefore did not necessarily reduce visibility. Greater scrutiny often coincided with increased public interest.

### 3. Consumer response did not immediately decline

Ethics related media share showed almost no same month relationship with either:

- Average star ratings
- Average consumer sentiment

This suggests that increased controversy did not immediately translate into lower consumer evaluations.

### 4. Some effects appeared with a delay

Higher absolute ethics related media volume was modestly associated with:

- Lower next month star ratings
- Lower next month consumer sentiment

This suggests that reputational effects may develop gradually rather than appearing immediately.

### 5. Attention and consumer evaluation behaved differently

Average Google search interest increased substantially across SHEIN's major growth periods.

At the same time, consumer ratings and sentiment improved during the pandemic growth period before weakening during the post rise scrutiny period.

The results highlight an important business distinction:

**A brand can become more visible and more controversial at the same time while consumer evaluations change more slowly.**

## Business Implications

The analysis suggests that organizations should not use a single metric to evaluate reputational risk.

High search interest or media visibility does not necessarily indicate positive consumer perception, while negative press may not immediately appear in ratings or sentiment.

A stronger monitoring framework would combine:

- Media coverage
- Search behavior
- Consumer ratings
- Review sentiment
- Changes over time

Looking at these indicators together provides a more complete picture of brand health and consumer response.

## Tools

- Python
- Pandas
- NumPy
- Matplotlib
- SciPy
- VADER Sentiment Analysis
- scikit learn
- Google News RSS
- Google Trends

## Project Structure

```text
shein-consumer-reputation-analysis/
├── data/
│   └── README.md
├── notebooks/
│   ├── 01_data_collection_cleaning.ipynb
│   └── 02_analysis_consumer_sentiment.ipynb
├── outputs/
│   ├── media_trends/
│   ├── consumer_sentiment/
│   └── correlation_analysis/
├── README.md
├── requirements.txt
└── .gitignore
```

## Limitations

This project has several limitations:

- Google News RSS is a live search source and does not represent a complete historical news archive.
- Google Trends reports normalized relative search interest rather than raw search volume.
- Consumer review data end in August 2024 while media and search data extend through 2025.
- Ethics related headlines were identified using a manually constructed keyword dictionary.
- VADER sentiment may not capture sarcasm or complex context.
- Google Play reviews represent users who chose to leave reviews and do not directly measure purchasing behavior or customer retention.
- Correlations identify associations and should not be interpreted as causal relationships.

## Data Sources

- Google News RSS
- Google Trends
- ShoppingAppReviews Dataset, Mendeley Data

## About

This project was completed as part of **Web Data Scraping and Text Analysis** at Sogang University during Fall 2026.

The analysis was designed to apply Python, text analysis, statistical methods, and data visualization to a real business question involving consumer behavior, reputation, and retail strategy.
