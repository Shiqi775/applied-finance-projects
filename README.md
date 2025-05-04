# applied-finance-projects

A curated collection of applied finance and data science projects that explore real-world problems through quantitative modeling, machine learning, natural language processing, and large language models (LLMs). Each project includes code, reports, and data-driven insights.

## Projects

### `RAG_Financial_QA`
**Retrieval-Augmented Generation for Financial Statement Q&A**  
Built a RAG system using ChromaDB and Llama-3-70B (via Together API) to answer queries on 10-K filings from 10 companies over 10 years. Achieved ~90% precision through metadata-based retrieval, vector similarity, and LLM reranking.

---

### `Clustering_Text_Portfolio`
**Clustering Text Embeddings for Sector Classification & Portfolio Analysis**  
Fine-tuned BERT and extracted embeddings from BERT, SBERT, Longformer, and GPT-2. Applied PCA + KMeans to cluster firms by business descriptions, then analyzed cumulative returns of resulting clusters as portfolios.

---

### `FOMC_RoBERTa_Policy_Stance`
**Monetary Policy Classification using Fine-Tuned RoBERTa**  
Classified FOMC minutes (1996–2024) as hawkish/dovish/neutral using a fine-tuned RoBERTa model. Constructed document-level hawkishness scores and analyzed their relationship with CPI, PPI, and recession trends.

---

### `FOMC_LLMs`
**FOMC Policy Stance Classification with Llama-3**  
Applied Llama-3-70B (via Together API) for zero- and few-shot classification of FOMC sentences. Compared performance to RoBERTa, and constructed a macro-level hawkishness measure for monetary trend analysis.

---

### `NLP_Operational_Risk`
**Cybersecurity Risk Analysis from 10-K Risk Factor Sections**  
Used NLP to extract cybersecurity-related disclosures from Item 1A of 10-K filings. Built a Cyber Risk Ratio and explored sectoral trends and return spreads based on risk quintiles.

---

### `ML_Jump_Prediction`
**Stock Price Jump Prediction with Machine Learning**  
Predicted stock price jumps (monthly return > 10%) using firm-level and macroeconomic features. Compared Logistic Regression, LASSO, KNN, XGBoost, and ANN on classification accuracy and variable importance.

---

## Notes
- All reports are in PDF format and paired with executable `.ipynb` notebooks.
- Datasets include CRSP stock returns, SEC EDGAR filings, and FRED macroeconomic indicators.
- Projects were completed as part of academic and independent research from 2023–2024.

## License
For academic and research purposes only.  
