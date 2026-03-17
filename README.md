# 🏦 Automated Banking Risk & Stability Analytics Engine

## 📖 Project Overview

This project presents a **Python-based analytical engine** designed to evaluate the financial stability of banking institutions. It leverages the **CAMEL framework** along with advanced quantitative risk models to automate the assessment of:

* Credit Risk
* Market Risk
* Systemic Risk

The system is built as an **end-to-end data pipeline**, transforming raw financial data into actionable risk insights.

> 🎯 **Goal:** Convert complex financial and regulatory logic into a scalable, automated analytics architecture.

---

## 🚀 Key Features & Methodologies

### 1️⃣ CAMEL Scoring Engine

Automates scoring (0–100) across five regulatory pillars:

* **Capital Adequacy (C):**

  * CRAR
  * Tier 1 Ratio
  * CET1 Ratio

* **Asset Quality (A):**

  * Gross NPA
  * Net NPA
  * Provision Coverage Ratio

* **Management Efficiency (M):**

  * Cost-to-Income Ratio
  * Operational Efficiency

* **Earnings Quality (E):**

  * Return on Assets (ROA)
  * Return on Equity (ROE)
  * Net Interest Margin (NIM)

* **Liquidity (L):**

  * Liquidity coverage metrics
  * Funding stability indicators

---

### 2️⃣ Advanced Quantitative Risk Models

* **Probability of Default (PD):**

  * Based on Merton Model
  * Uses distance-to-default

* **Expected Loss (EL) & Economic Capital:**

  * EL = PD × LGD × Exposure
  * Capital estimation at **99.9% confidence level**

* **Value at Risk (VaR):**

  * Earnings volatility estimation
  * Confidence levels: **95% and 99%**

* **Bankruptcy Prediction:**

  * Altman Z-Score (adapted for banks)
  * Classification:

    * Safe Zone
    * Grey Zone
    * Distress Zone

* **Systemic Risk (CoVaR):**

  * Measures spillover risk
  * Based on correlation with system-wide performance

---

### 3️⃣ Machine Learning & Predictive Analytics

#### 🔍 Classification Models

* Logistic Regression
* Support Vector Machine (RBF Kernel)

#### 📈 Regression Model

* Random Forest Regressor
* Forecasts future CAMEL scores

#### ⚠️ Anomaly Detection

* Isolation Forest
* Identifies abnormal financial behavior

---

### 4️⃣ Multi-Scenario Stress Testing

Simulates bank performance under macroeconomic shocks:

| Scenario         | NPL Increase | ROE Drop | Capital Erosion |
| ---------------- | ------------ | -------- | --------------- |
| Mild Recession   | +30%         | -15%     | -2%             |
| Severe Recession | +100%        | -50%     | -10%            |
| Credit Crisis    | +150%        | -70%     | -15%            |

---

## ⚠️ Technical Note: Data Scale & Model Performance

This project is an **Architectural Proof of Concept (PoC)**.

* Dataset:

  * Only **20 records**
  * 4 banks:

    * HDFC Bank
    * ICICI Bank
    * Punjab National Bank
    * State Bank of India

### 🚨 Important Limitation

* Models show:

  * **100% Accuracy**
  * **AUC = 1.000**

➡️ This is **severe overfitting**, expected due to extremely small dataset size.

### 💡 Key Takeaway

The real value lies in:

* Scalable pipeline architecture
* Modular design
* Readiness for enterprise-scale data

---

## 🗂️ Project Structure

```bash
banking-stability-analysis/
│
├── data/                     # Raw & processed data
├── src/                      # Core source code
│   ├── data_processing.py        # Data ingestion & cleaning
│   ├── feature_engineering.py    # CAMEL + financial ratios
│   ├── risk_models.py            # PD, VaR, CoVaR, stress testing
│   ├── predictive_models.py      # ML models (SVM, Logistic, RF)
│   └── visualizations.py         # Charts (Plotly, Seaborn)
│
├── requirements.txt          # Dependencies
├── main.py                   # Pipeline execution script
└── README.md                 # Documentation
```

---

## ⚙️ How to Run

```bash
# Clone the repository
git clone https://github.com/your-username/banking-stability-analysis.git

# Navigate to project
cd banking-stability-analysis

# Install dependencies
pip install -r requirements.txt

# Run pipeline
python main.py
```

---

## 📌 Future Improvements

* Integration with real-time financial APIs
* Larger datasets for robust ML training
* Dashboard (Streamlit / Dash)
* Model explainability (SHAP / LIME)
* Cloud deployment (AWS / GCP)

---

## 📄 License

This project is intended for **educational and research purposes**.

---

