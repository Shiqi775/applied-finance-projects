# Retrieval-Augmented Generation (RAG) for Financial Statement Q&A

This project implements a Retrieval-Augmented Generation (RAG) system that answers natural language questions based on 10-K financial filings from 10 randomly sampled U.S. companies over a 10-year period. It combines classical information retrieval techniques with modern large language models to support accurate and explainable financial analysis.

## Overview

The system is designed to:
- Extract, clean, and structure financial filings from the SEC EDGAR database
- Construct a searchable vector database of financial content using sentence embeddings
- Answer user queries using a two-stage retrieval + generation pipeline

## Key Components

### 1. Data Collection and Processing
- **Source**: SEC 10-K filings (2010–2020) for 10 tickers
- **Tool**: `sec_edgar_downloader`
- **Processing**: HTML parsing, content filtering, metadata tagging
- **Output**: Cleaned `content.txt` files per company-year

### 2. Vector Store Construction
- **Embedding Model**: `sentence-transformers/all-mpnet-base-v2`
- **Database**: ChromaDB
- **Chunking**: Sentence-based with sliding window and overlap
- **Metadata**: Ticker and filing year added for filtered retrieval

### 3. RAG Pipeline
- **Retriever**: Filters based on metadata and top-K semantic similarity
- **Reranker**: Reorders results using an LLM-based relevance score
- **LLM**: `meta-llama/Llama-3-70b-chat-hf` via Together API
- **Response Format**: Concise one-sentence answers generated using context chunks

### 4. Evaluation
- **Queries**: 2 test questions per ticker
- **Metrics**: Precision of retrieval and answer quality
- **Results**: ~90% overall accuracy across 20 queries

## Files
- `RAG_Financial_QA_Report.pdf`: Full project report detailing methods, design, and evaluation
- `query_results.csv`: Final evaluation results for all queries
- `source_code_file.zip`: Implementation code for the complete system

## Notes
To run the system, update your API key in `system.py`:
```python
os.environ['TOGETHER_API_KEY'] = "Replace_with_Your_Own_TogetherAI_API_Key"
