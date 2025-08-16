# 🩺 Breast Cancer Tumor Size Regression

This project builds and evaluates regression models to predict **tumor size** from the [Breast Cancer Wisconsin (Diagnostic) Dataset](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic)).

## 📌 Project Objective
The goal is to **predict tumor size** (mean area of the tumor) based on various morphological features of cell nuclei measured from breast tissue biopsies.

This serves as a regression-based approach to understand the relationship between tumor morphology and tumor size, rather than a classification of malignancy.

---
## ⚙️ Features & Workflow

### **1. Data Preprocessing**
- Removes non-predictive columns (`id`, empty columns)
- Encodes `diagnosis` (B = 0, M = 1) if present
- Clips outliers on selected geometric features using IQR method
- Scales features with `StandardScaler` (fit only on training set)
- Provides **train-only fitting** and **test transformation** to avoid data leakage

### **2. Model Training**
- Supports both:
  - **Raw target regression**
  - **Log-transformed target regression** (`log1p` / `expm1`)
- Models included:
  - Linear Regression
  - Ridge Regression
  - Lasso Regression
  - Random Forest Regressor (100 and 200 trees)
- Uses **KFold cross-validation** for robust performance evaluation
- Outputs metrics:
  - Mean Squared Error (MSE)
  - Coefficient of Determination (R²)
