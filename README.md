# 🛒  Engage2Value - Predictive Modeling for Purchase Value (Kaggle Competition — IIT Madras)

This repository contains my solution for a **Kaggle regression competition hosted by IIT Madras**, focused on predicting the **purchaseValue** of users based on their session-level clickstream data.  
The dataset consisted of **116,532 records** with **51 initial features**, capturing user behavior such as page views, clicks, and session metadata.

---

## 🚀 Project Overview
- **Organizer**: IIT Madras (via Kaggle)  
- **Task**: Regression (predicting numerical target: purchaseValue)  
- **Dataset**: Tabular (116K rows × 51 features)  
- **Evaluation Metric**: R² Score  
- **Final Score**: **0.51290** (improved from baseline 0.02)  

The main challenge was **high-dimensional, noisy, and sparse clickstream data**.  
I systematically tackled this using **EDA, feature reduction, advanced models, and stacking**.

---

## 🔍 Workflow

### 1. Data Exploration & Preprocessing
- Cleaned missing values (median for numeric, mode for categorical).
- Removed 32+ low-impact or highly missing columns.  
- Handled skewness with **log-transformation** of target.  
- Detected correlations and multicollinearity to reduce redundancy.  

### 2. Feature Engineering
- Session length features and interaction variables.  
- Encoding categorical columns via **Label Encoding** & **One-Hot Encoding**.  
- Dimensionality reduction based on importance scores.  

### 3. Modeling Approach
- **Baseline**: Linear Regression, Ridge, ElasticNet.  
- **Advanced Models**: XGBoost, LightGBM, Gradient Boosting.  
- **Final Approach**:  
  - **Stacked Ensemble** combining XGBoost + LightGBM + ElasticNet.  
  - Meta-model: Linear Regression on out-of-fold predictions.  

### 4. Validation
- **5-Fold Cross-Validation** with shuffling.  
- Stratification applied by binning target into quantiles.  

---

## 📊 Results
| Model                 | R² Score (CV) |
|------------------------|---------------|
| Linear Regression      | -0.02         |
| ElasticNet             | 0.18          |
| XGBoost                | 0.41          |
| LightGBM               | 0.44          |
| Stacked Ensemble       | **0.51290**   |

---

## ⚡ Key Learnings
- Importance of **data cleaning & dimensionality reduction** in sparse behavioral datasets.  
- **Stacking multiple models** improved performance over any single model.  
- Handling **outliers & skewness** in the target significantly boosted generalization.  

---

## 🛠️ Tech Stack
- **Python**  
- Libraries: `NumPy`, `Pandas`, `Matplotlib`, `Seaborn`, `Scikit-learn`, `XGBoost`, `LightGBM`  

---

## 📂 Repository Structure
├── data/ # (not included) raw dataset
├── notebooks/ # Jupyter notebooks (EDA, Modeling, Stacking)
├── src/ # Python scripts for preprocessing, training
├── results/ # Model outputs, plots
├── requirements.txt # Dependencies
└── README.md # Project documentation


---

## 🎯 Future Improvements
- Hyperparameter tuning with **Bayesian Optimization**.  
- Use **SHAP values** for interpretability.  
- Add **domain-specific features** from user behavior patterns.  

---

## 🏆 Competition Details
- Platform: **Kaggle**  
- Problem Type: **Regression (purchase value prediction)**  
- Leaderboard Rank: Improved from **baseline 0.02 → 0.51290**  

---

👤 **Author**: Garvit Man Singh

📧 **Contact**: mansinghgarvit@gmail.com 

⭐ If you find this useful, give it a **star**!
