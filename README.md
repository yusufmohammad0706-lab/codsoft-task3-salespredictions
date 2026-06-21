# 📈 Sales Prediction Using Python

A machine learning project that predicts product sales based on advertising expenditure across TV, Radio, and Newspaper channels using advanced regression techniques. Built as **Task 4** of the CodSoft Data Science Internship.

---

## 📌 Project Overview

Sales prediction involves forecasting the amount of a product that customers will purchase, taking into account various factors such as advertising expenditure and platform selection. This project analyzes historical advertising data, engineers new features, and builds regression models to accurately estimate sales based on ad spending across different media channels.

---

## 📁 Dataset

- **File:** `advertising.csv`
- **Shape:** 200 rows × 4 columns
- **No missing values** ✅
- **No duplicate rows** ✅

| Column | Description |
|---|---|
| `TV` | Money spent on TV advertising (in $000) |
| `Radio` | Money spent on Radio advertising (in $000) |
| `Newspaper` | Money spent on Newspaper advertising (in $000) |
| `Sales` | Product sales units ⭐ **(Target Variable)** |

### 📊 Dataset Statistics

| Feature | Min | Max | Mean | Std |
|---|---|---|---|---|
| TV | 0.7 | 296.4 | 147.04 | 85.85 |
| Radio | 0.0 | 49.6 | 23.26 | 14.85 |
| Newspaper | 0.3 | 114.0 | 30.55 | 21.78 |
| Sales | 1.6 | 27.0 | 15.13 | 5.28 |

---

## 🛠️ Technologies Used

- **Python 3**
- **Pandas** – Data manipulation
- **NumPy** – Numerical operations
- **Matplotlib & Seaborn** – Data visualization
- **Scikit-learn** – Machine learning models & evaluation

---

## ⚙️ Installation & Setup

1. **Clone the repository**
```bash
git clone https://github.com/yusufmohammad0706-lab/CodSoft-Task4-SalesPrediction.git
cd CodSoft-Task4-SalesPrediction
```

2. **Install required libraries**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. **Run the script**
```bash
python sales_prediction_v2.py
```

---

## 🔄 Project Workflow

```
SECTION 1 : Load & Inspect Dataset
          ↓
SECTION 2 : Data Validation
   → Check missing values & duplicates
   → Verify data types
          ↓
SECTION 3 : Feature Engineering
   → Total_Budget      : TV + Radio + Newspaper
   → TV_Ratio          : TV spend % of total budget
   → Radio_Ratio       : Radio spend % of total budget
   → TV_Radio_Combined : Weighted combo of TV & Radio
          ↓
SECTION 4 : EDA Visualization (9 plots)
          ↓
SECTION 5 : Model Training
   → StandardScaler for feature scaling
   → Train/Test Split (80% / 20%)
   → 4 Regression Models + 5-Fold Cross Validation
          ↓
SECTION 6 : Result Visualization (4 charts)
          ↓
SECTION 7 : Predict Sales for New Budgets
          ↓
SECTION 8 : Final Summary Report
```

---

## ✨ New Features Engineered

| Feature | Formula | Purpose |
|---|---|---|
| `Total_Budget` | TV + Radio + Newspaper | Overall ad spend |
| `TV_Ratio` | TV / Total_Budget | TV's share of budget |
| `Radio_Ratio` | Radio / Total_Budget | Radio's share of budget |
| `TV_Radio_Combined` | TV×0.7 + Radio×0.3 | Weighted impactful channels |

---

## 🤖 Models Used & Results

| Model | MAE | RMSE | R² Score | CV R² (5-fold) |
|---|---|---|---|---|
| Ridge Regression | 1.0959 | 1.3720 | 0.9358 | 0.9229 |
| **Lasso Regression** ✅ | **1.0416** | **1.3206** | **0.9405** | **0.9215** |
| KNN Regressor | 1.2420 | 1.4810 | 0.9252 | 0.9118 |
| Decision Tree | 1.0983 | 1.4066 | 0.9325 | 0.8906 |

> 🏆 **Lasso Regression** performed best with **R² Score of 0.9405** — meaning the model explains **94.05% of sales variation!**

### 📐 Metrics Explained

| Metric | Meaning |
|---|---|
| **MAE** | Mean Absolute Error — average prediction error, lower is better |
| **RMSE** | Root Mean Squared Error — penalizes large errors, lower is better |
| **R²** | How well model explains sales variance, higher is better (max = 1.0) |
| **CV R²** | Average R² across 5 folds — confirms model is stable & consistent |

---

## 📦 Sample Sales Predictions

| TV ($000) | Radio ($000) | Newspaper ($000) | Total Budget | Predicted Sales |
|---|---|---|---|---|
| 250 | 45 | 20 | 315 | **22.71** |
| 180 | 25 | 10 | 215 | **17.48** |
| 80 | 15 | 8 | 103 | **11.84** |
| 120 | 35 | 25 | 180 | **15.58** |
| 300 | 50 | 30 | 380 | **25.47** |

---

## 📊 Output Charts

### 1. EDA Analysis (`eda_sales_v2.png`) — 9 Plots
- TV vs Sales with correlation & trend line
- Radio vs Sales with correlation & trend line
- Newspaper vs Sales with correlation & trend line
- Total Budget vs Sales (colored by TV spend)
- Average budget share pie chart by channel
- Sales boxplot by TV budget category
- Feature correlation bar chart with Sales
- Sales trend line sorted by total budget
- Full correlation heatmap

### 2. Model Results (`model_results_v2.png`) — 4 Plots
- Actual vs Predicted sales scatter plot
- Residual plot (prediction errors)
- Test R² vs CV R² grouped bar comparison
- MAE comparison across all models

---

## 💡 Key Findings

- **TV advertising** has the strongest correlation with Sales (r = 0.78)
- **Total Budget** is a powerful combined predictor of sales
- **TV_Radio_Combined** feature boosted model accuracy
- **Lasso Regression** performed best by automatically selecting the most important features
- **5-Fold CV R²** closely matched Test R² — confirming the model is not overfitting

---

## 📂 Project Structure

```
CodSoft-Task4-SalesPrediction/
│
├── advertising.csv              # Dataset
├── sales_prediction_v2.py       # Main Python script
├── eda_sales_v2.png             # EDA visualization (9 plots)
├── model_results_v2.png         # Model evaluation charts (4 plots)
└── README.md                    # Project documentation
```

---

## 🙋‍♂️ Author

**Yusuf Mohammad**
- GitHub: [@yusufmohammad0706-lab](https://github.com/yusufmohammad0706-lab)
- LinkedIn: [Yusuf Mohammad](https://www.linkedin.com/in/yusuf-mohammad-50a142381/)

---

⭐ If you found this project helpful, please give it a star!
