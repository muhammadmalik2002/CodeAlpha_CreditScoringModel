# CodeAlpha_CreditScoringModel

## 📌 Task
**Task 1 — Credit Scoring Model**
Predict an individual's creditworthiness (Good vs. Bad credit risk) using past financial data, as part of the CodeAlpha Machine Learning Internship.

## 📊 Dataset
[UCI Statlog (German Credit Data)](https://archive.ics.uci.edu/ml/machine-learning-databases/statlog/german/german.data)
- 1000 records, 20 features + target
- Target distribution: 700 Good credit / 300 Bad credit (imbalanced ~70/30)
- Features include checking account status, credit history, purpose, credit amount, savings, employment history, age, housing, and more.

## 🛠 Approach
1. **Data Loading & Preprocessing**
   - Loaded raw space-separated data, assigned column names
   - No missing values found
   - Label-encoded 13 categorical columns
   - Target mapped to binary (0 = Good, 1 = Bad)

2. **Train/Test Split**
   - 80/20 split, stratified on target to preserve class ratio

3. **Modeling**
   - Logistic Regression (with feature scaling)
   - Decision Tree
   - Random Forest
   - All models trained with `class_weight='balanced'` to address class imbalance

4. **Evaluation**
   - Metrics: Precision, Recall, F1-Score, ROC-AUC (accuracy alone is misleading on imbalanced data)
   - Confusion matrices for visual comparison

## 📈 Results

| Model | ROC-AUC | Accuracy | Bad Credit Recall |
|---|---|---|---|
| Logistic Regression | 0.7908 | 0.71 | 0.73 |
| Decision Tree | 0.6610 | 0.68 | 0.65 |
| **Random Forest** | **0.8114** | **0.80** | 0.63 |

**Random Forest** was selected as the final model based on the highest ROC-AUC and best overall balance across precision/recall. Logistic Regression showed a stronger Bad Credit recall, a relevant trade-off if minimizing missed high-risk applicants is the priority.

### Top Features (Random Forest)
1. Checking account status
2. Credit amount
3. Duration (months)
4. Age
5. Savings account

## 🧰 Tech Stack
- Python, Pandas, NumPy
- Scikit-learn (Logistic Regression, Decision Tree, Random Forest)
- Matplotlib, Seaborn
- Google Colab

## 🚀 How to Run
1. Download the dataset from the UCI link above
2. Open `Credit_Scoring_Model.ipynb` in Google Colab
3. Update the dataset file path if needed
4. Run all cells sequentially

## 👤 Author
Muhammad Ahmad
CodeAlpha Machine Learning Intern — August 2026

## 🔗 Internship
This project was completed as part of the [CodeAlpha](https://www.codealpha.tech) Machine Learning Internship.
