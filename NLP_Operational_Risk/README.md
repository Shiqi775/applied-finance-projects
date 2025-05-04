# Predicting Cybersecurity Operational Risk from 10-K Filings Using NLP

This project applies natural language processing (NLP) techniques to extract and quantify cybersecurity-related operational risk from the "Item 1A: Risk Factors" section of SEC 10-K filings. It then evaluates how these risks vary across industries and time, and investigates their relationship with equity returns through portfolio analysis.

## Overview

- **Data**: 10-K Item 1A text for selected firms (1996–2023), matched with CRSP stock data.
- **Goal**: Create a measure of cybersecurity risk and analyze its cross-sectional and temporal implications on financial performance.

## Methodology

### 1. Risk Extraction via NLP
- Tokenized 10-K risk factor sections into sentences using `nltk`.
- Matched sentences against curated keyword lists to identify relevant vs. irrelevant mentions of cybersecurity threats.
- Constructed a **Cybersecurity Risk Ratio**:  
  \[
  \text{Cyber Risk Ratio} = \frac{\# \text{Cyber-Relevant Sentences}}{\# \text{Total Sentences in Item 1A}}
  \]

### 2. Descriptive Statistics
- Computed distributional statistics (mean, std, skewness, kurtosis) of risk scores by sector.
- Visualized trends in cybersecurity risk across sectors and over time.
- Found highest average risk in **Finance, Insurance & Real Estate**, with increasing emphasis post-2015.

### 3. Portfolio Construction
- Formed **equal-weighted** and **value-weighted** portfolios by risk quintiles.
- Compared returns of high vs. low cyber-risk firms.
- Noted higher volatility in high-risk portfolios in early 2000s, with convergence post-2015.

## Key Insights
- Finance and Wholesale Trade show the highest and most volatile cybersecurity risk.
- High cyber-risk portfolios tend to exhibit greater return variability.
- Market perception and pricing of cybersecurity risk appear to have matured in recent years.

## Files
- `NLP_Operational_Risk_Code.ipynb`: Full implementation of text processing, risk metric creation, and portfolio analysis.
- `NLP_Operational_Risk_Report.pdf`: Report with plots, commentary, and interpretations.

## Tools & Libraries
- Python 3.8+, `nltk`, `pandas`, `matplotlib`, `numpy`, `re`, `glob`

## Author
Shiqi Hu | Georgia Tech QCF | December 2024
