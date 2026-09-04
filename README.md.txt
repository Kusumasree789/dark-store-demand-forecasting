# Dark Store Demand Forecasting

An end-to-end machine learning project for forecasting daily order volume across multiple fulfillment hubs.

Developed as part of the **Celebal Technologies × NIT Rourkela Kaggle Competition**.

## 🏆 Competition Result

* **Final RMSLE Score:** 0.07843
* **Final Leaderboard Rank:** 35
* **Total Hubs:** 1,115
* **Training Records:** ~970,000
* **Test Records:** 46,830

## 📌 Problem Statement

The objective was to predict daily `OrderVolume` for a network of fulfillment hubs using historical demand data, operational information, calendar variables, and hub metadata.

The competition was evaluated using the **Root Mean Squared Logarithmic Error (RMSLE)** metric.

## 📊 Dataset

### Training Period

January 2013 – June 2015

### Test Period

June 2015 – July 2015

### Available Information

* Hub ID
* Date
* Weekday
* Operational status
* Promotional activity
* Regional holidays
* School closure indicators
* Hub format
* Assortment tier
* Competitor information
* Loyalty program information

## 🔧 Feature Engineering

The following features were engineered to improve forecasting performance.

### Calendar Features

* Year
* Month
* Day
* Day of Year
* Week of Year
* Weekend indicator
* Month start/end indicators

### Cyclical Features

* Month sine and cosine encoding
* Weekday sine and cosine encoding

### Temporal Features

* Historical lag features
* Weekly lag intervals
* Rolling mean statistics
* Rolling standard deviation statistics

### Hub-Level Features

* Hub-specific historical demand statistics
* Demand patterns by hub and weekday

### Metadata Features

* Hub format
* Assortment tier
* Competitor distance
* Competitor age
* Loyalty program information

## 🤖 Models

Several forecasting approaches were evaluated during the competition.

| Model                      | RMSLE Score |
| -------------------------- | ----------: |
| Baseline Model             |     0.15433 |
| Lag-Based Model            |     0.10842 |
| Direct CatBoost Model      |     0.08832 |
| Enhanced CatBoost V5       |     0.07946 |
| Model Blend                |     0.07939 |
| **Final Calibrated Model** | **0.07843** |

## 🚀 Final Model

The final solution used:

* CatBoost Regressor
* Temporal feature engineering
* Hub-level statistical features
* Calendar features
* Operational features
* Hub metadata
* Prediction calibration

A final prediction calibration factor of **0.982** produced the best leaderboard result.

## 📈 Performance Improvement

The project improved significantly through iterative experimentation:

```text
Baseline        → 0.15433
Lag Features    → 0.10842
Direct CatBoost → 0.08832
Enhanced Model  → 0.07946
Final Model     → 0.07843
```

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* CatBoost
* Matplotlib
* Seaborn
* Jupyter Notebook
* Kaggle

## 📂 Repository Structure

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
└── .gitignore
```

## ▶️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/dark-store-demand-forecasting.git
cd dark-store-demand-forecasting
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

## 🧠 Key Learnings

This project involved practical experience with:

* Time-series forecasting
* Time-based validation
* Feature engineering
* Lag features
* Rolling window statistics
* Categorical feature handling
* Gradient boosting
* CatBoost regression
* RMSLE optimization
* Model ensembling
* Prediction calibration
* Kaggle competition workflow

## 👤 Author

**Nimmagadda Kusuma Sree**

Final Year Computer Science Engineering Student

[GitHub](https://github.com/) | [Kaggle](https://www.kaggle.com/nimmagaddakusumasree)
