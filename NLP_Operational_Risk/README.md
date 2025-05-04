# Cybersecurity Risk Analysis Using NLP on 10-K Filings

This project applies Natural Language Processing (NLP) techniques to extract and quantify cybersecurity-related disclosures in SEC 10-K filings, constructing a risk measure and evaluating its financial implications through portfolio analysis.

## Overview

Using Item 1A (“Risk Factors”) sections from 10-K filings across industries from 1996–2022, we:
- Extract cybersecurity-relevant sentences using rule-based NLP filters.
- Construct a **cyber risk ratio** for each firm-year.
- Analyze sectoral and temporal trends in cyber risk disclosure.
- Evaluate how cybersecurity risk correlates with equity returns using equal- and value-weighted quintile portfolios.

## Key Steps

### 1. Text Extraction
- Tokenized sentences using `nltk`.
- Applied keyword filtering with inclusive and exclusive rules to identify cybersecurity-relevant sentences.
- Used JSON-based 10-K data and merged with CRSP monthly return data by `(PERMNO, year)`.

### 2. Risk Measure

- Defined **Cyber Risk Ratio** as:

  $$
  \text{Cyber Risk Ratio} = \frac{\text{\No. of Cybersecurity Sentences}}{\text{\No. of Total Risk Sentences in Item 1A}}
  $$

- Used a relative measure to ensure comparability across firms of different sizes or verbosity levels.


### 3. Descriptive Analysis
- Computed mean, standard deviation, skewness, and kurtosis of cyber risk across industries and over time.
- Found that the Finance and Wholesale Trade sectors exhibit the highest risk levels and volatility.

### 4. Portfolio Return Analysis
- Constructed quintile portfolios based on firms’ cybersecurity risk.
- Calculated and plotted **equal-weighted** and **value-weighted** return spreads between high-risk and low-risk portfolios.
- Observed that return differentials were more pronounced before 2010, and flattened in recent years, reflecting possible market efficiency improvements.

## Files
- `NLP_Operational_Risk_Code.ipynb`: Full implementation of extraction, risk calculation, and return analysis.
- `NLP_Operational_Risk_Report.pdf`: Report summarizing methodology, results, and insights.

## Requirements
- Python 3.8+
- `nltk`, `pandas`, `numpy`, `matplotlib`, `glob`, `json`, `scipy`

## Notes
- This project focuses solely on **cybersecurity risk** within the broader operational risk landscape.
- Portfolio results suggest that markets may have matured in pricing cyber risk over time.

