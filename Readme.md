# 🎾 Tennis Match Outcome Prediction with Machine Learning
The aim of this project is to determine the outcome (the winner) of a Tennis Match by using machine learning algorithms.
## 📚 Project Overview
The predictive model is based on: 
- Historical performance of each player
- Match context: surface, court
- Official ranking 
- Odds from different bookmarkers. 
The metric score of the final model is **76% accuracy**, based on data processing and tree-based model classifier.
---
## 📁 Dataset
The initial dataset includes historical ATP tennis match results. Each match entry includes:
- Date
- Players involved (winner, loser)
- Tournament details
- Match conditions (surface, court type)
- Player rankings and statistics at the time
---
## ⚙️ Steps and Methodology
As the objective of this project is to determine which player is the winner, and the current dataset indicated directly the winner and the loser in their respective columns, data transformation is requested. 
### 1. 🧼 Data Preprocessing
- Convert categorical variables (e.g., surface) using one-hot encoding
- The winner and loser column are deleted, replaced by Player1 and Player 2 column, winner and loser in half of the dataset
### 2.  📊 Temporal Feature Engineering
New features are created, based on the two players’ history, such as: 
- **Rank ratio/ different **
- **Current Win percentage difference / ratio based on the previous matches**
- **Rolling averages and streaks** (last 5 matches)
- **Current Win/loss form by surface**
- **Head-to-head record**
> after each match, those temporal features are updated.

### 4. 🤖 Model Training and Evaluation
The following models are tested:
- **Random Forest Classifier**
- **Gradient Boosting (sklearn)**
- **XGBoost**
- **LightGBM** (best performance)
- Optional: `GridSearchCV` used to optimize hyperparameters

### 5. 🧠 Feature Importance
Feature importance is visualized to understand what drives predictions. The most relevant features include: 
- Rank and win percentage ratios
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
