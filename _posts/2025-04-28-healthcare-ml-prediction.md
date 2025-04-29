![image](https://github.com/user-attachments/assets/45a97e9c-ef3d-4cde-aeed-32b6765d76cb)


---
layout: post
title: "Can We Predict Medicare Scores Before They're Published? A Machine Learning Approach"
description: "A data science case study that predicts Medicare agency performance using open CMS data and interpretable machine learning models."
date: 2025-04-28
author: "gabriel luepke"
---
![image](https://github.com/user-attachments/assets/28e0c7ca-e6aa-410a-a0bd-c837148fcf96)

# Can We Predict Medicare Scores Before They're Published?  
### A Machine Learning Case Study

<figure>
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/87/US_CMS_Logo.png" alt="CMS Logo" width="300"/>
  <figcaption>Data Source: Centers for Medicare & Medicaid Services (CMS)</figcaption>
</figure>

## 🎯 Business Question

**Can home health agencies forecast their upcoming Medicare performance scores based on their current operational data?**

This blog post outlines how we used open data and machine learning to estimate Medicare’s **Total Performance Score (TPS)** for U.S. healthcare agencies — before formal evaluations are released.

---

## 🧠 Summary for Non-Technical Stakeholders

- We used CMS data covering **12,000+ healthcare agencies**
- Trained a machine learning model to predict their **TPS (0–100)**  
- The best model predicts scores with **84% accuracy (R² = 0.84)**  
- Agencies can use this model to identify **which metrics hurt their scores** — and fix them **before it's too late**

---

## 📊 Key Insights

### Q1: **What factors drive an agency’s Medicare score?**

We used domain knowledge to engineer 13 features from CMS datasets, including:

| Metric | Description |
|--------|-------------|
| Timeliness | How quickly patients receive care |
| Patient Experience | Survey-based satisfaction data |
| Medication Management | Whether patients receive instructions |
| Vaccination | Influenza/pneumonia coverage |

<figure>
  <img src="https://upload.wikimedia.org/wikipedia/commons/3/3f/Bar_chart_icon.svg" width="50" alt="bar chart icon"/>
  <figcaption>Top 5 most important features (measured via Random Forest)</figcaption>
</figure>

---

### Q2: **How accurate is the prediction model?**

We tested multiple models and selected **Random Forest Regressor** due to its balance of accuracy and interpretability.

| Model | R² Score | RMSE |
|-------|----------|------|
| Linear Regression | 0.64 | 6.1 |
| **Random Forest** | **0.84** | **3.9** |

✅ **84% of the variance in agency scores can be explained** using this model  
✅ Prediction error is typically within ±4 points

---

### Q3: **What does this mean for decision-makers?**

> “If I improve patient satisfaction or care timeliness, how much will my predicted score increase?”

By plugging in updated performance data, administrators can simulate their TPS ahead of time and **strategically improve low-performing metrics**.

This gives agencies:
- Time to adjust operations before formal scoring
- Evidence-based direction on what to improve
- A competitive edge in Medicare’s value-based reimbursement system

---

## 🔍 Visual Example (Sample Prediction)

<figure>
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/Line_chart_icon.svg/600px-Line_chart_icon.svg.png" alt="Prediction Chart" width="300"/>
  <figcaption>Example: Predicted vs. Actual TPS values (Random Forest Model)</figcaption>
</figure>

---

## ✅ Conclusion

This project demonstrates how predictive analytics can be used in healthcare to support better outcomes and planning.

By transforming raw CMS data into actionable insights, we empower agencies to improve their care — **before Medicare scores penalize them**.

---

📎 *Want to view the full notebook, data, or model code? [Visit the GitHub repository](#).*

