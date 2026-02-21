# 📱 Google Play Store Rating Prediction

## 📌 Project Overview
Google Play Store plans to introduce a feature that boosts the visibility of promising applications across recommendations and search results. Since app ratings are a strong indicator of app quality and user satisfaction, this project focuses on predicting app ratings using available metadata.

The goal is to build a machine learning model that can identify apps likely to receive high ratings, helping Google decide which apps to promote.

---

## 🎯 Objective
To build a **Linear Regression model** that predicts an app’s rating based on various attributes such as:

- Reviews  
- Size  
- Installs  
- Price  
- Category  
- Content Rating  

---

## 🧩 Problem Statement
Given historical Google Play Store app data, predict which apps will have higher ratings and are therefore good candidates for promotional boosts.

---

## 📂 Dataset
- **Source:** Google Play Store  
- **File:** `googleplaystore.csv`

### Dataset Features

| Column Name      | Description |
|------------------|------------|
| App              | Application name |
| Category         | App category |
| Rating           | Overall user rating |
| Reviews          | Number of user reviews |
| Size             | Size of the app |
| Installs         | Number of downloads |
| Type             | Free or Paid |
| Price            | App price |
| Content Rating   | Target age group |
| Genres           | App genres |
| Last Updated     | Last update date |
| Current Ver      | Current app version |
| Android Ver      | Minimum Android version required |

---

## 🔍 Project Workflow

### 1️⃣ Data Loading
- Loaded the dataset using **pandas**

### 2️⃣ Missing Value Handling
- Identified null values column-wise  
- Dropped records containing null values  

---

## 🧹 Data Cleaning & Type Fixes

### Size
- Extracted numeric values  
- Converted MB to KB  

### Reviews
- Converted from string to numeric  

### Installs
- Removed `+` and `,`  
- Converted to integer  

### Price
- Removed `$` symbol  
- Converted to numeric  

---

## ✅ Sanity Checks
- Ratings restricted between **1–5**  
- Reviews ≤ Installs  
- Free apps must have **Price = 0**  
- Invalid rows were dropped  

---

## 📊 Exploratory Data Analysis (EDA)

### Univariate Analysis
- Boxplots: Price, Reviews  
- Histograms: Rating, Size  

### Observations
- Price and Reviews contain significant outliers  
- Ratings are skewed toward higher values  
- App sizes vary widely  

---

## 🚨 Outlier Treatment

### Price
- Dropped apps priced above $200  

### Reviews
- Removed apps with more than 2 million reviews  

### Installs
- Analyzed percentiles (10, 25, 50, 70, 90, 95, 99)  
- Selected a cutoff threshold and removed extreme values  

---

## 🔗 Bivariate Analysis

- Rating vs Price → No strong positive correlation  
- Rating vs Size → Larger apps not necessarily better rated  
- Rating vs Reviews → More reviews ≠ better rating  
- Rating vs Content Rating → Some age groups perform better  
- Rating vs Category → Certain categories consistently rate higher  

---

## ⚙️ Data Preprocessing

### Feature Engineering
Applied **log transformation (log1p)** to:
- Reviews  
- Installs  

Dropped irrelevant columns:
- App  
- Last Updated  
- Current Ver  
- Android Ver  

### Encoding
Applied **One-Hot Encoding** to:
- Category  
- Genres  
- Content Rating  

---

## 🧪 Train-Test Split
- 70–30 split  
- Created:
  - `X_train`, `y_train`
  - `X_test`, `y_test`

---

## 🤖 Model Building
- Algorithm Used: **Linear Regression**
- Model trained on training data  

---

## 📈 Evaluation Metric
- **R² Score**

| Dataset        | R² Score |
|---------------|----------|
| Training Set  | Add Score Here |
| Test Set      | Add Score Here |

---

## 🏁 Conclusion
- App ratings can be reasonably predicted using metadata  
- Reviews, installs, and category significantly influence ratings  
- Linear Regression provides a strong baseline model  
- Results can help identify apps suitable for promotion  

---

## 🛠 Technologies Used
- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit-learn  
