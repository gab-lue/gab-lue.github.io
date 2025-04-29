---
layout: post
title: "Predicting Healthcare Agency Performance Using Machine Learning"
description: "A detailed walkthrough of a data science project to predict Medicare agency performance scores using real-world healthcare data."
date: 2025-04-28
author: "Your Name"

---

# Predicting Healthcare Agency Performance Using Machine Learning

## 0. Project Overview
In this project, we aim to predict the **Total Performance Score (TPS)** for home healthcare agencies. TPS determines how much a healthcare provider gets paid, depending on their quality of service, under the **Medicare** program.

Our task is to build a machine learning model that accurately predicts TPS, allowing agencies to anticipate their scores and improve their services.

We will:
- Analyze and clean the raw data
- Engineer useful features
- Train machine learning models
- Evaluate their performance using clear, understandable metrics
- Apply the model to a real-world business case

---

## 0.1 Methodology
We followed a structured data science approach:
1. **Exploratory Data Analysis**: Understand the raw data.
2. **Data Cleaning**: Handle missing values and irrelevant columns.
3. **Feature Engineering**: Create smarter inputs for the model.
4. **Model Building**: Train and compare different models.
5. **Evaluation**: Use metrics like **R²** and **RMSE** to judge model quality.
6. **Business Application**: Show how agencies can use predictions to improve performance.

---

## 1. Exploratory Data Analysis

The dataset contained:
- **11,969 rows** (healthcare agencies)
- **252 columns** (different measures of quality, achievements, improvements, and more)

⚠️ **Key Observations**:
- **4,809 rows** were **missing** the target value (**TPS**), meaning that for almost 40% of agencies, we didn’t know their final score.
- The dataset included performance indicators like:
  - **Care of patients**
  - **Willingness to recommend the agency**
  - **Timeliness of care**

We decided to **remove** rows with missing TPS when training the model.

---

## 2. Data Cleaning and Preparation

Before building models, we prepared the data carefully:
- **Removed irrelevant columns**: e.g., agency name, ID numbers.
- **Kept only columns related to performance**.
- **Filled missing feature values** with averages when appropriate.

After cleaning:
- Data was **consistent** and **ready for machine learning**.
- We ensured there were **no missing target values** in the training data.

🛑 **Challenge**:
- Some features had strange values (like 0s where they shouldn’t), which needed manual checking and corrections.

---

## 3. Feature Engineering

To make the model smarter:
- **Weighted Scores**: Instead of just looking at raw scores, we multiplied important scores by their assigned weights. This helps the model understand what matters most (e.g., medication adherence could be 1.5x more important than willingness to recommend).
- **New Features**: Combined related features to reduce noise.

This helped the model learn more meaningful patterns rather than getting distracted by less important metrics.

---

## 4. Model Building

We trained two models and compared their performance:

### 4.1 Linear Regression
- A simple model that tries to draw a straight line through the data.
- **Result**:
  - **R² Score**: **0.64**
    - Meaning: 64% of the variability in TPS was explained by the model.
  - **Root Mean Squared Error (RMSE)**: **6.1**
    - Meaning: On average, the model’s prediction was about 6 points off.

### 4.2 Random Forest
- A more advanced model that builds **many decision trees** and averages their results.
- **Result**:
  - **R² Score**: **0.84**
    - Meaning: 84% of TPS variability explained — much better!
  - **Root Mean Squared Error (RMSE)**: **3.9**
    - Meaning: Predictions were on average only 4 points off.

📈 **Comparison**:
- Random Forest outperformed Linear Regression by a large margin.
- It was better at handling complex relationships between features.

🛑 **Challenge**:
- Random Forest models can sometimes "memorize" the training data (**overfitting**).  
  Careful tuning of parameters like **tree depth** and **number of trees** helped control this.

---

## 5. Business Application

With a trained model ready, we moved to a real-world case:

### Use Case:
- Agencies can input their current performance metrics into our model.
- The model predicts their future **Total Performance Score (TPS)**.
- Agencies can identify **weak areas** (like patient satisfaction or timeliness of care) before official reviews.
- By improving targeted areas early, agencies can achieve **better TPS** — leading to **higher Medicare payments**.

✅ **Benefits**:
- **Proactive improvements**.
- **Financial optimization**.
- **Better patient outcomes**.

---

## 6. Challenges and Lessons Learned

Throughout this project, we faced and overcame several challenges:
- **Missing Data**: Required careful filtering and imputation.
- **Choosing Features**: Focused only on meaningful variables to avoid noise.
- **Avoiding Overfitting**: Especially important with powerful models like Random Forest.

🎯 **Key Lessons**:
- Good data is more important than fancy algorithms.
- Simpler models can work, but complex models like Random Forest deliver better results if tuned correctly.
- Explaining results clearly helps non-technical stakeholders appreciate data science.

---

# Final Thoughts

This project shows that **machine learning** can play a crucial role in healthcare quality improvement.

By predicting performance scores, agencies can:
- Improve their service
- Increase patient satisfaction
- Optimize their financial outcomes

And most importantly: they can deliver **better care to patients**.  
This project proves that with the right approach, **data science can make a real-world difference**.

---
