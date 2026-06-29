# 🚀 HR Promotion Prediction & Analytics Dashboard

---

## 📖 Project Overview

This project focuses on predicting employee promotions using machine learning while providing actionable insights through an interactive Power BI dashboard. By combining data preprocessing, exploratory analysis, predictive modeling, and visualization, the solution helps HR teams identify employees with high promotion potential and make more informed promotion decisions.

---

## 🎯 Business Problem

Promotion decisions are often influenced by multiple employee performance indicators, making the process time-consuming and prone to inconsistency. Organizations need a reliable way to:

* Identify employees with strong promotion potential
* Support promotion decisions with data-driven insights
* Detect high-performing employees who may have been overlooked

This project addresses these challenges by developing a predictive model and presenting the results through an intuitive dashboard.

---

## 📂 Dataset

The dataset contains employee demographic, performance, and training information, including:

* Department
* Education
* Gender
* Previous Year Rating
* KPI Achievement
* Training Score
* Awards Won
* Length of Service
* Promotion Status

---

## ⚙️ Project Workflow

### 1. Data Preparation

* Cleaned the dataset by removing unnecessary columns
* Treated missing values using appropriate statistical methods
* Standardized column names and checked for inconsistencies

---

### 2. Feature Engineering

Created additional business features to improve model performance.

## Fast Track Employee

Employees were categorized as **Fast Track** when they satisfied the following conditions:

* KPIs Achieved = Yes
* Previous Year Rating ≥ 4
* Training Score above the overall average

---

### 3. Addressing Class Imbalance

Since only a small percentage of employees were promoted, the dataset was highly imbalanced.

To improve model performance:

* Applied `class_weight='balanced'` in Logistic Regression
* Focused on maximizing **Recall** to reduce missed promotion opportunities
* Evaluated the model using a Confusion Matrix

**Confusion Matrix Format**

```
[[True Negative   False Positive]
 [False Negative  True Positive]]
```

---

### 4. Machine Learning Model

A Logistic Regression model was trained after feature scaling.

Model evaluation included:

* Precision
* Recall
* F1-Score

---

### 5. Threshold Optimization

Instead of using the default probability threshold, different thresholds were tested to achieve the desired business outcome.

### Performance Summary

| Threshold | Business Goal                            | Recall |
| --------- | ---------------------------------------- | ------ |
| 0.35      | Capture maximum high-potential employees | ~88%   |
| 0.50      | Balanced prediction                      | ~80%   |
| 0.68      | High-confidence recommendations          | ~63%   |

---

### 6. Employee Ranking

The trained model generated a promotion probability score for every employee.

Employees were then:

* Ranked by promotion probability
* Categorized into Low, Medium, and High promotion potential

---

## 📊 Key Findings

* Employees with strong KPI performance, higher ratings, and better training scores showed a significantly higher likelihood of promotion.
* Several high-performing employees were identified who had not yet been promoted, indicating possible promotion leakage.
* Previous Year Rating emerged as one of the strongest predictors in the model.

---

## 📈 Power BI Dashboard

The dashboard provides:

* Overall promotion statistics
* Promotion rate and Fast Track employee analysis
* Department-wise promotion insights
* Key promotion drivers
* High-potential employees ranked by promotion probability
* Identification of employees who may require HR attention

---

## 💼 Business Value

This solution enables organizations to:

* Support promotion decisions with objective data
* Reduce bias in the promotion process
* Identify high-potential employees proactively
* Improve employee retention by recognizing overlooked talent

---

## 🛠️ Technology Stack

* Python
* Pandas
* Scikit-learn
* Power BI
* Microsoft Excel

---

## 📁 Project Structure

* **promo.ipynb** – Data preprocessing, feature engineering, model development, and evaluation
* **hr_promotion_output.xlsx** – Final employee dataset with predicted promotion probabilities
* **Power BI Dashboard** – Interactive visualization of promotion insights

---

## 📚 Key Takeaway

This project demonstrates that selecting the right evaluation metric is just as important as choosing the right machine learning model. For promotion prediction, optimizing **Recall** helps identify more deserving employees, making the solution better aligned with business objectives.

---

## 🚀 Future Enhancements

* Experiment with advanced algorithms such as Random Forest and XGBoost
* Include additional employee behavioral and historical performance features
* Deploy the prediction model as a web application or API
* Automate data refresh and dashboard updates for real-time monitoring
