# 🎾 Tennis Match Outcome Prediction with Machine Learning

This project aims to predict the winner of professional tennis matches using historical data and advanced machine learning techniques.

## 📚 Project Overview

The goal is to build a robust predictive model by combining:
- Player statistics and rankings
- Historical performance
- Match context (e.g., surface type, court conditions)
- Temporal features such as win streaks and recent form

The final model achieves over **76% accuracy** using a combination of engineered features and tree-based classifiers.

---

## 📁 Dataset

The dataset includes historical ATP tennis match results. Each match entry includes:
- Date
- Players involved (winner, loser)
- Tournament details
- Match conditions (surface, court type)
- Player rankings and statistics at the time

---

## ⚙️ Steps and Methodology

### 1. 🧼 Data Preprocessing
- Filter and clean the raw ATP dataset
- Convert categorical variables (e.g., surface) using one-hot encoding
- Handle missing data where necessary

### 2. 🔧 Feature Engineering
A wide range of custom features are created, including:
- **Rank difference / ratio**
- **Win percentage difference / ratio**
- **Rolling averages and streaks** (last 5 matches)
- **Win/loss form by surface**
- **Head-to-head record**

> These were calculated dynamically using rolling windows and player history.

### 3. 📊 Temporal Feature Engineering
- Recent player form and momentum (e.g., last 5 matches winrate)
- Player streaks (current number of consecutive wins/losses)
- Surface-specific performance
- Rolling win rate difference and ratio

### 4. 🤖 Model Training and Evaluation
The following models are tested:
- **Random Forest Classifier**
- **Gradient Boosting (sklearn)**
- **XGBoost**
- **LightGBM** (best performance)
- Optional: `GridSearchCV` used to optimize hyperparameters

### 5. 🧠 Feature Importance
Model-based feature importance is evaluated to understand what drives predictions. Most relevant features include:
- Rolling stats and recent form
- Rank and win percentage differences
- Surface-specific streaks and head-to-head stats

---

## 🧪 Results

| Model        | Accuracy |
|--------------|----------|
| RandomForest | ~74.0%   |
| XGBoost      | ~76.2%   |
| LightGBM     | **~76.4%** ✅ |

The model shows strong predictive performance across surfaces and players, thanks to rich feature engineering.

---

## 🚀 Future Work
- Integration of live odds or ELO ratings
- Real-time prediction API
- More advanced AutoML pipelines
- Deep learning models for sequential data

---

## 📬 File Summary

- `Tennis_Match_Prediction.ipynb` — Jupyter notebook with the full data pipeline, feature engineering, and model training steps.

---

## 🛠 Requirements

- Python 3.7+
- pandas, numpy
- scikit-learn
- xgboost
- lightgbm
- matplotlib / seaborn (optional for visualizations)

Install dependencies:

```bash
pip install -r requirements.txt
```
---

## 🤝 Credits

Data: [http://tennis-data.co.uk/](http://tennis-data.co.uk/)

Author: Matthieu Hanania

Tools: Python, scikit-learn, LightGBM, pandas