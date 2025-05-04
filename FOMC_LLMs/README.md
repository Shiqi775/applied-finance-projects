# LLM-Based Classification of FOMC Policy Stance and Trading Strategy

This project uses large language models (LLMs) to classify U.S. Federal Reserve (FOMC) meeting minutes into hawkish, dovish, or neutral stances. Based on the resulting hawkishness scores, a long-short equity trading strategy is constructed and evaluated.

## Overview

We explore zero-shot and few-shot inference using `Llama-3-70b-chat` (via Together API), compare its performance with a fine-tuned `RoBERTa` model, and use the predicted hawkishness scores to guide asset allocation and portfolio construction.

## Key Components

### 1. Inference with LLMs
- **Model**: `meta-llama/Llama-3-70b-chat-hf` via Together API
- **Approach**: Zero-shot vs. few-shot prompting (3–5 examples)
- **Task**: Classify FOMC sentences as Dovish, Hawkish, or Neutral
- **Best Performance**: Few-shot Llama-3 achieves F1 = 0.71 (vs. RoBERTa F1 = 0.69)

### 2. Hawkishness Measure
- Computed for each meeting as:

  \[
  \text{Hawkishness} = \frac{\# \text{Hawkish} - \# \text{Dovish}}{\# \text{Total Sentences}}
  \]

- Applied to full FOMC minutes dataset (1996–2024)

### 3. Trading Strategy Design
- Strategy uses the hawkishness score to select long/short positions by sector:
  - **Hawkish**: Long Financials/Public Admin; Short Construction/Retail
  - **Dovish**: Long Construction/Retail; Short Financials/Public Admin
  - **Neutral**: Balanced long/short across sectors

- Stock selection based on top/bottom rolling 12-month returns and sector alignment

### 4. Market Evaluation
- Backtest from 1996 to 2023 using CRSP monthly stock data
- Metrics:
  - Sharpe Ratio = 0.66 (vs. 0.49 S&P 500)
  - Sortino Ratio = 0.96 (vs. 0.68 S&P 500)
  - Max Drawdown = -33.4% (vs. -52.6% S&P 500)

## Files
- `FOMC_LLMs_Report.pdf`: Project report with model analysis and strategy results
- `FOMC_LLMs_Code.ipynb`: Full code for classification, measure construction, and backtest

## Tools & Libraries
- Python 3.8+, HuggingFace Transformers, Together API, pandas, scikit-learn, matplotlib

## Acknowledgment
Inference model powered by [Together AI](https://www.together.ai) and Llama-3-70B-chat.

