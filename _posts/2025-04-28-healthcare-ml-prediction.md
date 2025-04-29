---
layout: post
title: "Predicting Healthcare Agency Performance Using Machine Learning"
description: "A concise overview of using machine learning to predict Medicare agency performance scores with real-world data."
date: 2025-04-28
author: "Your Name"
---

# Predicting Healthcare Agency Performance Using Machine Learning

## Introduction

How well will a Medicare-certified home health agency perform in its next government evaluation?

We tackled this question by developing a machine learning (ML) model using real-world performance data. The goal: help agencies **anticipate their Total Performance Score (TPS)** and take action before financial penalties hit.

---

## 1. Problem & Data

We worked with publicly available data from the Centers for Medicare & Medicaid Services (CMS), covering over **12,000 agencies**. The key output we aimed to predict was the **TPS**, a composite score calculated from factors like:

- Timeliness of care
- Medication adherence
- Patient satisfaction
- Vaccination rates

Only ~10,000 agencies had full TPS scores, so we filtered out incomplete data and focused on meaningful predictors.

---

## 2. Data Cleaning & Feature Engineering

We engineered features by grouping related metrics and applying weights based on CMS’s scoring logic (e.g., the *Quality of Patient Care* and *HHCAHPS* components). We removed variables with too many missing values and normalized the rest.

Final dataset:  
- ~10,000 rows  
- 13 engineered features  
- Target: continuous TPS score (0–100 scale)

---

## 3. Model Building & Results

We compared two regression models:

### 🔹 Linear Regression
- **R²**: 0.64  
- **RMSE**: 6.1

### 🔹 Random Forest Regressor
- **R²**: 0.84  
- **RMSE**: 3.9

✅ **Random Forest significantly outperformed Linear Regression**, capturing non-linear patterns in the data without overfitting.

We validated with cross-validation (10-fold) and checked for generalization on a holdout set.

---

## 4. Why It Matters

This model allows agency administrators to:

- Simulate performance scores based on current metrics
- Prioritize improvements in low-scoring areas
- Justify resource allocation using predictive insights

A simple interface (or script) could even let them “plug in” their current performance data and receive an estimated TPS score instantly.

---

## Conclusion

With thoughtful feature engineering and robust modeling, we showed that Medicare agency performance can be accurately predicted using existing data.

While this is just a proof of concept, it demonstrates how **data science can empower healthcare organizations** to improve quality proactively — not just reactively.

---

*Want the full notebook or data source? [View the project on GitHub](#).*
