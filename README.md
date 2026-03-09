# LLM-Driven-SEC-Filing-Sentiment-Factor

## Goal

Built and evaluated an NLP-based equity sentiment signal using FinBERT vs. VADER, testing whether a financial-domain language model improves predictive power of corporate disclosure sentiment using 10-K filings and 21-day forward returns.

## Theoretical foundation
Financial text sentiment theory

Corporate filings contain forward-looking qualitative information about firm performance, risk, and management outlook.
NLP sentiment models can convert this narrative text into quantitative signals that may predict future equity returns.

Domain-specific language models

Traditional sentiment models rely on generic lexicons, which often misclassify financial terminology.
FinBERT, trained on financial corpora, aims to better capture contextual sentiment in financial disclosures.

## Define a directional signal
Sentiment signal

For each 10-K document:

- VADER score: lexicon-based sentiment polarity

- FinBERT score: transformer-based financial sentiment classification

- Ensemble signal: combined sentiment score from both models

### Forward returns

Each filing is aligned with 21-day forward stock returns to measure predictive performance.

Predictive signal evaluation

Sentiment signals are tested for their ability to predict:

- Return magnitude

- Return direction

- Cross-sectional predictive ranking

## Data Processing
### Universe

several large-cap U.S. equities

### Source

- SEC EDGAR – 10-K filings

- Extracted sections:

    - Management Discussion & Analysis (MD&A)

    - Risk Factors

### Dates

Sample aligned with filings and 21-day forward return window

### Cleaning

- Parsed and extracted text from filings

- Removed formatting artifacts

- Tokenized documents for NLP model input

## Implementation process

1. Scrape 10-K filings from SEC EDGAR

2. Extract MD&A and Risk Factors sections

3. Generate sentiment scores using:

    - VADER

    - FinBERT

4. Construct ensemble sentiment signal

5. Align filings with 21-day forward returns

6. Split dataset using 70/30 time-based train-test split

7. Evaluate predictive power using:

- Linear regression (return estimation)

- Logistic regression (direction classification)

8. Cross-sectional rank correlation (Information Coefficient proxy)

9. Run horse-race regression comparing FinBERT vs VADER signals

## Results

The FinBERT-based sentiment signal produced stronger and more stable out-of-sample predictive performance compared to the VADER benchmark.

## Assumptions

- Filing sentiment is assumed to immediately reflect new information

- Returns measured at 21-day horizon

- Small universe limits cross-sectional breadth

## Extensions

- Expand universe to S&P 500 filings

- Incorporate earnings call transcripts



