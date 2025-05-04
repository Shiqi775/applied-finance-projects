# FOMC Policy Stance Classification with Fine-Tuned RoBERTa

This project fine-tunes a RoBERTa model to classify U.S. Federal Reserve (FOMC) meeting minutes as **Hawkish**, **Dovish**, or **Neutral**, and investigates the relationship between monetary stance and economic indicators such as CPI, PPI, and recessions.

## Overview

The project includes:
- Fine-tuning RoBERTa on labeled FOMC sentences using grid search over learning rate, batch size, and epoch.
- Sentence-level inference over full FOMC meeting minutes from 1996 to 2024.
- Construction of a document-level **hawkishness score**.
- Visualization and analysis of how hawkishness correlates with inflation and economic downturns.

## Key Components

### 1. Model Training
- **Base model**: `roberta-base` from HuggingFace
- **Best performance**: F1 score = 0.723 on test set
- **Label categories**:  
  - `LABEL_0`: Dovish  
  - `LABEL_1`: Hawkish  
  - `LABEL_2`: Neutral

### 2. Inference and Hawkishness Measure
- Filtered sentences by monetary policy keywords from FOMC raw text files
- Classified filtered sentences using the fine-tuned model
- Computed hawkishness score:
  
  \[
  \text{Hawkishness} = \frac{\# \text{Hawkish} - \# \text{Dovish}}{\# \text{Total Sentences}}
  \]

### 3. Economic Analysis
- Merged hawkishness scores with CPI, PPI, and NBER recession data
- Plotted annual inflation trends with shaded recession periods
- Overlaid hawkishness to show Fed behavior across time

## Files
- `FOMC_RoBERTa_Report.pdf`: Full project report, including training logs and macroeconomic visualizations.
- `FOMC_RoBERT_Code.ipynb`: Implementation for fine-tuning, inference, scoring, and visualization.

## Requirements
- Python 3.8+
- HuggingFace Transformers
- scikit-learn, matplotlib, pandas, seaborn

## Citation
Model inspired by [Trillion Dollar Words (ACL 2023)](https://aclanthology.org/2023.acl-long.368/)

