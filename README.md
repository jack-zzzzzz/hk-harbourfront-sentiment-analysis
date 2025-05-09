# Hong Kong Harbourfront Public Sentiment Dataset (2011-2024)

This repository contains the dataset used in the study: "Spatiotemporal Analysis of Public Feedback on Hong Kong's Waterfront (2011- April 2025): An LLM-Driven Approach with Engineered Confidence Metrics."

## Dataset Description

The dataset comprises 78019 user-generated reviews regarding various locations along the Hong Kong Harbourfront, collected from Google Maps between January 2011 and April 2025. Each review has been analyzed using a Large Language Model (gpt-4o-mini) to determine sentiment ('Positive'/'Negative') and categorize discussed urban issues into nine predefined types. Custom-engineered confidence scores and perplexity values are provided for each LLM classification.

**File:** `Hong Kong Harbourfront Dataset.csv`
**Format:** CSV (Comma Separated Values)

## Column Descriptions

*   `title`: (Text) Name of the specific Google Maps location reviewed.
*   `text`: (Text) The original user review text, after cleaning (removal of HTML, URLs, excessive whitespace).
*   `publishedAtDate`: (Timestamp, ISO 8601 format) Date and time the review was published.
*   `stars`: (Integer) Star rating given by the user (typically 1-5).
*   `location/lat`: (Numeric) Latitude of the location.
*   `location/lng`: (Numeric) Longitude of the location.
*   `placeId`: (Text) Google Maps Place ID for the location.
*   `zone`: (Text) The assigned harbourfront zone (1 of 17) for spatial analysis.
*   `sentiment_analysis`: (Text) LLM-assigned sentiment: 'p' for Positive, 'n' for Negative.
*   `sentiment_confidence`: (Numeric, 0.5-0.99) Engineered confidence score for the sentiment classification, derived from the average log probability of the initial 5 tokens of the LLM's JSON output.
*   `categories`: (Text) Comma-separated string listing up to three LLM-identified urban issue categories. "None (positive sentiment)" if no specific issues were identified for a positive review.
*   `categories_confidence`: (Numeric, 0.5-0.99) Average engineered confidence score for the identified issue categories.
*   `category_1`: (Text) First identified issue category.
*   `category_1_confidence`: (Numeric, 0.5-0.99) Engineered confidence for category_1.
*   `category_2`: (Text) Second identified issue category (if any).
*   `category_2_confidence`: (Numeric, 0.5-0.99) Engineered confidence for category_2.
*   `category_3`: (Text) Third identified issue category (if any).
*   `category_3_confidence`: (Numeric, 0.5-0.99) Engineered confidence for category_3.
*   `perplexity`: (Numeric) Perplexity of the LLM's entire generated JSON output for the review; lower values indicate higher model certainty.

## Anonymization

Usernames and direct links to user profiles have been excluded. The data consists of publicly available review text, timestamps, and location information.

## Data Collection and Processing

Reviews were collected via Google Maps. Text cleaning was performed, followed by analysis using the gpt-4o-mini model prompted for structured JSON output. Confidence and perplexity metrics were engineered from the LLM's token-level log probabilities. For full methodological details, please refer to our accompanying paper: [Link to your preprint/published paper when available].

## Citation

If you use this dataset, please cite our paper:
[Your Full Paper Citation When Available]

And this dataset:
[Your Name(s)/Group. (Year). Hong Kong Harbourfront Public Sentiment Dataset (2011-2024). GitHub. {URL of your GitHub repo} (if not using Zenodo for DOI)]
OR
[Your Name(s)/Group. (Year). Hong Kong Harbourfront Public Sentiment Dataset (2011-2024) [Data set]. Zenodo. {DOI from Zenodo}]

## License

This dataset is shared under the [Choose Your License, e.g., CC BY 4.0] license. See `LICENSE.md` for details.
