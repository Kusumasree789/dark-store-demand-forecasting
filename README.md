# 📦 Dark Store Demand Forecasting

### End-to-End Time Series Demand Forecasting using CatBoost

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![CatBoost](https://img.shields.io/badge/Model-CatBoost-orange.svg)](https://catboost.ai/)
[![Kaggle](https://img.shields.io/badge/Platform-Kaggle-20BEFF.svg)](https://www.kaggle.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

An end-to-end machine learning project for forecasting daily order volumes across fulfillment hubs using time-series feature engineering and CatBoost regression.

Developed for the **Celebal Technologies × NIT Rourkela Kaggle Competition**.

---

# 🏆 Competition Performance

| Metric              |      Result |
| ------------------- | ----------: |
| 🥇 Best RMSLE Score | **0.07843** |
| 📊 Leaderboard Rank |      **35** |
| 🏢 Fulfillment Hubs |   **1,115** |
| 📚 Training Records |   **~970K** |
| 🔮 Test Records     |  **46,830** |

### Model Improvement Journey

```text
Baseline
0.15433
   ↓
Lag Features
0.10842
   ↓
Direct CatBoost
0.08832
   ↓
Enhanced Feature Engineering
0.07946
   ↓
Final Calibrated Model
0.07843
```

The final model achieved approximately **49% improvement over the initial baseline**.

---

# 📌 Problem Statement

The objective was to predict daily `OrderVolume` for a network of fulfillment hubs.

The challenge involved forecasting demand using:

* Historical order patterns
* Hub information
* Operational conditions
* Promotional activity
* Calendar effects
* Holiday information
* Competitor information
* Loyalty program data

The competition metric was:

> **Root Mean Squared Logarithmic Error (RMSLE)**

---

# 📊 Dataset Overview

### Training Data

| Feature          | Details                  |
| ---------------- | ------------------------ |
| Period           | January 2013 – June 2015 |
| Records          | ~970,000                 |
| Fulfillment Hubs | 1,115                    |

### Test Data

| Feature         | Details           |
| --------------- | ----------------- |
| Forecast Period | June 2015 onwards |
| Records         | 46,830            |

### Available Features

```text
HubID
Date
Weekday
IsOpen
PromoActive
RegionalHoliday
SchoolClosureFlag
HubFormat
AssortmentTier
CompetitorDistance
LoyaltyProgram
```

---

# 🔧 Feature Engineering

Feature engineering played a major role in improving forecasting performance.

## 📅 Calendar Features

* Year
* Month
* Day
* Day of Year
* Week of Year
* Weekend indicator
* Month start indicator
* Month end indicator

---

## 🔄 Cyclical Features

To capture periodic patterns:

* Month sine encoding
* Month cosine encoding
* Weekday sine encoding
* Weekday cosine encoding

---

## ⏳ Temporal Features

Historical demand information was captured using:

* Lag features
* Weekly lag intervals
* Rolling averages
* Rolling standard deviations

Examples:

```text
lag_1
lag_7
lag_14
lag_21
lag_28
lag_35
lag_42
```

---

## 📈 Rolling Statistics

Rolling demand statistics were calculated using multiple windows:

```text
7 days
14 days
28 days
56 days
```

Including:

* Rolling Mean
* Rolling Standard Deviation

---

## 🏢 Hub-Level Features

Hub-specific features were engineered to capture different demand behaviors across locations.

These included:

* Hub historical demand statistics
* Hub-level averages
* Hub-weekday demand patterns
* Recent demand trends

---

## 🗂️ Metadata Features

Additional business information included:

* Hub Format
* Assortment Tier
* Competitor Distance
* Competitor Age
* Loyalty Program
* Loyalty Program Age

---

# 🤖 Modeling Approach

The primary model used was:

## CatBoost Regressor

CatBoost was selected because it provides:

* Native categorical feature handling
* Strong gradient boosting performance
* Robust handling of missing values
* Effective performance on tabular datasets

The target variable was modeled in log space to optimize for RMSLE.

---

# 📈 Model Experiments

Several models and feature combinations were evaluated.

| Version  | Approach                                    |       RMSLE |
| -------- | ------------------------------------------- | ----------: |
| Baseline | Initial forecasting model                   |     0.15433 |
| V1       | Lag-based CatBoost                          |     0.10842 |
| V2       | Direct CatBoost                             |     0.08832 |
| V5       | Enhanced temporal features + hub statistics |     0.07946 |
| Blend    | Model ensemble                              |     0.07939 |
| 🏆 Final | Prediction calibration                      | **0.07843** |

---

# 🚀 Final Model

The best-performing solution combined:

* CatBoost Regression
* Time-series feature engineering
* Calendar features
* Hub-level statistics
* Operational features
* Metadata features
* Categorical feature handling
* Prediction calibration

### Final Calibration

A small multiplicative calibration was applied:

```text
Calibration Factor = 0.982
```

This improved the final leaderboard score.

---

# 🛠️ Tech Stack

| Category             | Technology             |
| -------------------- | ---------------------- |
| Programming Language | Python                 |
| Data Processing      | Pandas, NumPy          |
| Machine Learning     | CatBoost, Scikit-learn |
| Visualization        | Matplotlib, Seaborn    |
| Development          | Jupyter Notebook       |
| Competition Platform | Kaggle                 |

---

# 📂 Repository Structure

```text
dark-store-demand-forecasting/
│
├── notebooks/
│   └── demand_forecasting.ipynb
│
├── results/
│   └── results.md
│
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
```

---

# ⚙️ Installation

## Clone the Repository

```bash
git clone https://github.com/Kusumasree789/dark-store-demand-forecasting.git
cd dark-store-demand-forecasting
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Launch Jupyter Notebook

```bash
jupyter notebook
```

---

# 🧠 Key Learnings

Through this project, I gained practical experience in:

* Time-series forecasting
* Time-based validation
* Feature engineering
* Lag feature creation
* Rolling window statistics
* Categorical feature handling
* CatBoost regression
* Gradient boosting
* RMSLE optimization
* Model experimentation
* Model blending
* Prediction calibration
* Kaggle competition workflows

---

# 📈 Future Improvements

Potential future improvements include:

* Hyperparameter optimization using Optuna
* Advanced ensemble models
* LightGBM and XGBoost comparison
* Cross-validation across multiple time windows
* SHAP-based feature importance analysis
* Automated feature engineering pipeline

---

# 👤 Author

**Nimmagadda Kusuma Sree**

Final Year B.Tech Computer Science Engineering Student

* GitHub: https://github.com/Kusumasree789
* Kaggle: https://www.kaggle.com/nimmagaddakusumasree

---

⭐ If you found this project interesting, consider giving the repository a star!
