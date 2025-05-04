# Clustering Text Embeddings for Sector Classification and Portfolio Analysis

This project explores the use of Transformer-based language models to classify companies by industry and analyze market performance based on clustered business descriptions extracted from SEC 10-K filings.

## Overview

Using both encoder-only and decoder-only models, we:
- Fine-tuned BERT for 10-sector classification based on Item 1: Business Descriptions.
- Extracted embeddings from BERT, Sentence-BERT, Longformer, and GPT-2 models.
- Applied PCA for dimensionality reduction and K-Means for clustering.
- Formed sector-based portfolios and analyzed cumulative returns over time.

## Key Components

### 1. Fine-Tuning BERT for Sector Classification
- Dataset: Business descriptions from sampled companies (1996–2023).
- Training: 80/10/10 split for train/val/test.
- Metric: Best validation F1 score of **0.77**.

### 2. Embedding Inference and Clustering
- Models used: `bert-base-uncased`, `sbert`, `longformer`, `gpt2`.
- Dimensionality reduction with PCA.
- K-Means clustering (`k=3`) to uncover broad business groupings.
- GPT-2 embeddings provided clearest cluster separation under K-Means.

### 3. Portfolio Construction and Analysis
- Clusters mapped to 3 portfolios.
- Computed both equal-weighted and value-weighted cumulative returns (1996–2022).
- GPT-2-based Portfolio 0 showed the strongest value-weighted performance.
- Industry distribution and performance insights were provided per cluster.

## Files
- `Cluster_Text_Code.ipynb`: End-to-end implementation, from preprocessing to evaluation.
- `Cluster_Text_Report.pdf`: Detailed write-up including plots, metrics, and portfolio analysis.

## Notes
- Random seed fixed to 42 for reproducibility.
- All models from HuggingFace; refer to the notebook for tokenizer and checkpoint setup.

## Dependencies
- Python 3.8+
- HuggingFace Transformers
- scikit-learn
- pandas, matplotlib, seaborn
