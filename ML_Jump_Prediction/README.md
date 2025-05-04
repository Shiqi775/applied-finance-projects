# Predicting Stock Price Jumps using Machine Learning

This project explores the use of machine learning techniques to predict stock price "jumps," defined as absolute returns exceeding 10%, using historical firm-level and macroeconomic data from 1996 to 2023.

## Objective

To evaluate and compare various classification algorithms—Logistic Regression, LASSO, Ridge, K-Nearest Neighbors, XGBoost, and ANN—for their ability to forecast future stock return jumps, and to analyze which covariates most contribute to predictive accuracy.

## Key Components

### 1. Outcome Construction
- Defined binary jump indicator:
  - 1 if |monthly return| > 10%
  - 0 otherwise
- Used CRSP monthly stock data and macro indicators: VIX, CPI, Fed Funds Rate, Unemployment Rate

### 2. Feature Engineering
- Firm-specific: Beta, volatility, past 12-month return, market cap, volume
- Macroeconomic: USREC (recession indicator), VIX, CPI, Unemployment Rate
- Industry: One-hot encoded SIC-based sectors

### 3. Model Evaluation
#### Logistic, LASSO, Ridge
- **Post-LASSO AUC**: 0.6977 | **KS**: 0.3047
- Ridge improved generalization slightly over standard logistic

#### K-Nearest Neighbors (KNN)
- **Best K**: 30
- **Lowest misclassification rate**: 0.3697

#### XGBoost
- Tuned with learning rate = 0.01, depth = 3
- Misclassification rate: 0.3792

#### ANN (Multilayer Perceptron)
- 3-class classification: large positive jump, stable, large negative jump
- Moderate performance: Misclassification rate = 0.4203

### 4. Findings
- VIX strongly correlates with jump probability (ρ ≈ 0.72)
- KNN outperformed other models in accuracy
- LASSO and Ridge improved over baseline logistic regression
- ANN shows potential for multi-class modeling but requires further tuning

## Files
- `ML_Jump_Prediction.ipynb`: Full code, including data prep, modeling, and evaluation
- `ML_Jump_Prediction_Report.pdf`: Summary report with plots and comparative analysis

## Requirements
- Python 3.8+
- `scikit-learn`, `xgboost`, `torch`, `pandas`, `matplotlib`, `seaborn`, `nltk`

## Acknowledgments
- Data from CRSP and FRED (Federal Reserve Economic Data)
- This project was developed as part of a course assignment in Applied Machine Learning in Finance.
