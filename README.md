# ❤️ Heart Disease Classification using Ensemble and Linear Models

This project builds a classification pipeline to predict the presence of heart disease using the UCI Heart Disease dataset. It incorporates data cleaning, feature engineering, clustering for missing label imputation, and model evaluation across multiple machine learning classifiers.

---

## 📌 Project Overview

The goal of this project is to classify heart disease presence using a combination of medical and demographic features. We implement and compare several machine learning models and use **KMeans clustering** to impute missing target labels.

---

## ✅ Objectives

- Analyze and clean the training and test datasets.
- Detect and handle outliers using IQR-based filtering.
- Visualize feature distributions and relationships.
- Fill missing labels (`num` column) using KMeans clustering.
- Scale numeric features and one-hot encode categorical ones.
- Train and evaluate multiple classifiers using cross-validation.
- Perform hyperparameter tuning for the best model.
- Export predictions for final test data.

---

## 📊 Dataset Overview

- `Train_heart_disease_uci.csv`: Training data
- `Test_heart_disease_uci.csv`: Unlabeled test data

Features include:
- **Numerical**: `age`, `trestbps`, `chol`, `thalch`, `oldpeak`, `ca`
- **Categorical**: `sex`, `cp`, `fbs`, `restecg`, `exang`, `slope`, `thal`, `dataset`

---

## 🧼 Data Cleaning and Preprocessing

- Removed duplicate records.
- Outlier detection via IQR on numeric features.
- Checked and visualized missing values in the `num` column.
- Used **KMeans clustering** to impute missing `num` values based on similar feature groups.
- Applied **standardization** using `StandardScaler` on numerical features.
- Applied **OneHotEncoding** to all categorical columns (with drop-first logic).

---

## 📊 Exploratory Data Analysis

- Distribution plots for all numeric features.
- Pair plots and correlation heatmap for insight into feature relationships.
- Churn distribution analysis and per-category breakdown.

---

## 🧠 Models Used

Each model was evaluated using **Accuracy, Mean Squared Error (MSE), and Mean Absolute Error (MAE)**:

- **AdaBoost Classifier**
- **Gradient Boosting Classifier**
- **Random Forest Classifier**
- **XGBoost Classifier**
- **Support Vector Machine (SVM)**
- **Logistic Regression**

### 🔍 Model Selection & Tuning

- The best model was selected based on validation accuracy.
- **GridSearchCV** was used to tune hyperparameters of the best-performing model.
- Final tuned model retrained on the full dataset for test prediction.

---

## 🏆 Final Evaluation (Example)

| Model               | Accuracy | MSE    | MAE    |
|--------------------|----------|--------|--------|
| Random Forest       | 0.92     | 0.10   | 0.08   |
| Logistic Regression | 0.89     | 0.13   | 0.11   |
| XGBoost             | 0.91     | 0.11   | 0.09   |

> Replace with your actual results from `results_df`.

---

## 📁 Project Structure

```bash
├── Train_heart_disease_uci.csv      # Labeled training data
├── Test_heart_disease_uci.csv       # Test data without labels
├── submission.csv                   # Final predictions (id, prediction)
├── heart_disease_notebook.ipynb     # Jupyter notebook with full workflow
├── README.md                        # This file
