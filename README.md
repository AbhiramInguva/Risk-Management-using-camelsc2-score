# Automated Banking Risk & Stability Analytics Engine

## 📖 Project Overview
[cite_start]This repository contains a comprehensive Python-based analytical engine designed to evaluate the financial stability of banking institutions[cite: 1444]. [cite_start]Utilizing the **CAMEL Framework** and advanced quantitative risk models, the system automates the assessment of credit, market, and systemic risk through an end-to-end data pipeline[cite: 453, 1846].



The primary objective of this project is to translate complex regulatory and financial logic into a scalable, automated architecture capable of processing institutional financial data and generating predictive risk insights.

## 🚀 Key Features & Methodologies

### 1. CAMEL Scoring Engine
[cite_start]The pipeline automates the extraction and calculation of standardized scores (0-100) across five core regulatory pillars [cite: 715-726, 1196-1207]:
* [cite_start]**Capital Adequacy (C):** Evaluates CRAR, Tier 1, and CET1 ratios [cite: 52-58, 697-701].
* [cite_start]**Asset Quality (A):** Analyzes Gross/Net NPA ratios and Provision Coverage [cite: 59-65, 702-706].
* [cite_start]**Management Efficiency (M):** Assesses Cost-to-Income and operational efficiency metrics [cite: 66-71, 707-708].
* [cite_start]**Earnings Quality (E):** Measures ROA, ROE, and Net Interest Margin (NIM) [cite: 73-81, 709-714].
* [cite_start]**Liquidity (L):** Benchmarks base liquidity ratios [cite: 83-85, 724].

### 2. Advanced Quantitative Risk Models
Beyond standard reporting, the engine implements advanced financial engineering metrics:
* [cite_start]**Probability of Default (PD):** Utilizes the Merton Model logic to calculate distance-to-default and PD percentages [cite: 1849-1858].
* [cite_start]**Expected Loss (EL) & Economic Capital:** Computes Expected Loss and Risk-Weighted Asset (RWA) proxies based on a 99.9% confidence interval [cite: 1880-1890, 1894-1907].
* [cite_start]**Value at Risk (VaR):** Assesses earnings volatility at 95% and 99% confidence intervals [cite: 1913-1932].
* [cite_start]**Bankruptcy Prediction:** Implementation of the Altman Z-Score (adapted for financial institutions) to categorize banks into Safe, Grey, or Distress zones [cite: 1489-1512].
* [cite_start]**Systemic Risk (CoVaR):** Quantifies systemic risk contribution based on the bank's correlation with system-wide averages [cite: 2005-2019].

### 3. Machine Learning & Predictive Analytics
[cite_start]The framework utilizes various machine learning techniques to predict bank stability ("Troubled" vs. "Healthy") and detect anomalies [cite: 95-101, 1208-1213]:
* [cite_start]**Classification Models:** Compares Logistic Regression and Support Vector Machines (SVM) with RBF kernels [cite: 196-223, 1288-1301].
* [cite_start]**Regression Modeling:** Uses Random Forest Regressors to forecast future CAMEL scores based on lagged historical features [cite: 1591-1617].
* [cite_start]**Anomaly Detection:** Implements Isolation Forests to identify outlier financial performance among institutions [cite: 1969-1980].

### 4. Multi-Scenario Stress Testing
[cite_start]The system simulates bank resilience and capital shortfalls under three distinct macroeconomic shocks [cite: 1632, 2024-2030, 2050]:
1. [cite_start]**Mild Recession:** 30% NPL increase, 15% ROE decrease, 2% capital erosion[cite: 2025].
2. [cite_start]**Severe Recession:** 100% NPL increase, 50% ROE decrease, 10% capital erosion [cite: 2026-2027].
3. [cite_start]**Credit Crisis:** 150% NPL increase, 70% ROE decrease, 15% capital erosion [cite: 2028-2029].

---

## ⚠️ Technical Note: Data Scale & Model Performance
This project was engineered as an **Architectural Proof of Concept (PoC)**. [cite_start]Due to the restricted nature of granular banking data, the models in this repository were trained and validated on a highly focused dataset consisting of 20 records across 4 major institutions (HDFC Bank Ltd., ICICI Bank Limited, Punjab National Bank, and State Bank of India) [cite: 1361-1366, 1370].

[cite_start]Because of the extremely small sample size, the predictive classification models (SVM, Logistic Regression) exhibit 100% Accuracy and a 1.0000 AUC [cite: 1418-1421]. *This indicates severe mathematical overfitting and is expected given the data constraints.*

[cite_start]The core value of this repository is not the predictive output of this specific small dataset, but rather the **scalable, automated pipeline architecture** [cite: 449-488, 1652]. The codebase is modularly designed to immediately ingest and accurately process large-scale, enterprise-level financial datasets.

---

## 🗂️ Project Structure

```text
banking-stability-analysis/
│
├── data/                   # Directory for raw and processed banking data
├── src/                    # Main source code directory
│   ├── data_processing.py  # Data loading, cleaning, and merging logic
│   ├── feature_engineering.py # CAMEL framework, Z-Score, and financial ratios
│   ├── risk_models.py      # Merton PD, VaR, CoVaR, and Stress Testing logic
│   ├── predictive_models.py# Scikit-learn ML models (SVM, Logit, Random Forest)
│   └── visualizations.py   # Plotly and Seaborn charting functions
│
├── requirements.txt        # Project dependencies
├── main.py                 # Execution script to run the end-to-end pipeline
└── README.md               # Project documentation
