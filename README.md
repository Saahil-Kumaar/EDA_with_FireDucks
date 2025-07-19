# EDA_with_FireDucks
# 🛒 Online Retail Customer Analytics

This project performs data cleaning, feature engineering, exploratory data analysis, RFM segmentation, and customer churn analysis on the **UCI Online Retail Dataset**. It provides deep insights into customer behavior and purchasing patterns using Python and pandas.

## 📊 Objective

Analyze customer purchase data from an online retail store to:
- Clean and preprocess raw transactional data
- Discover product and country-wise sales trends
- Perform **RFM (Recency, Frequency, Monetary)** analysis
- Identify **churned customers**
- Visualize monthly, country-wise, and product-wise sales

---

## 📁 Dataset

The dataset is downloaded from the UCI Machine Learning Repository:
- **Name**: Online Retail Dataset
- **URL**: https://archive.ics.uci.edu/dataset/352/online+retail
- **File**: `Online Retail.xlsx`

It contains transactions from a UK-based online retailer over the course of 1 year.

---

## 📦 Libraries Used

```bash
!pip install openpyxl
!pip install fireducks
````

```python
import fireducks.pandas as pd
from matplotlib import pyplot as plt
```

---

## ⚙️ Data Preprocessing Steps

* Handled missing descriptions using most frequent description per `StockCode`
* Removed entries with:

  * Negative `Quantity`
  * Zero or negative `UnitPrice`
* Created `TotalSales = Quantity * UnitPrice`
* Extracted month from `InvoiceDate`

---

## 📈 Exploratory Data Analysis

### 1. 📅 Monthly Sales Trend

Shows how total sales vary across months using a line chart.

### 2. 🌍 Country-wise Sales Distribution

Displays top 5 countries contributing to sales using a horizontal bar chart.

### 3. 🛍️ Product-wise Sales Distribution

Highlights top 5 selling products by revenue and their percentages.

---

## 🧠 RFM (Recency, Frequency, Monetary) Analysis

Each customer is scored based on:

* **Recency**: Days since last purchase
* **Frequency**: Number of transactions
* **Monetary**: Total amount spent

RFM scores are segmented using **quartile binning (qcut)** to assign a score from 1–4.

The final **`RFM_Score = R + F + M`**, and customers are ranked accordingly.

---

## ❌ Customer Churn Analysis

* Defines churned customers as those **inactive for over 90 days**
* Visualizes recency distribution with a histogram
* Prints total number of churned customers

---

## 📊 Sample Visuals

* Line plot of monthly sales
* Horizontal bar charts of top countries and products by revenue
* Histogram showing churned customers' recency

---

## 🧹 Project Flow Summary

```text
📥 Load Data → 🧽 Clean + Impute → 🧮 Calculate TotalSales →
📆 Extract Month → 📊 Visualize Sales →
📌 RFM Segmentation → 🔍 Churn Analysis → 📉 Visual Insights
```

---

## ✅ Future Improvements

* Cluster customers using k-means on RFM scores
* Predict churn using classification models
* Segment markets based on region and product category

---

## 📚 References

* [UCI Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)
* Concepts: RFM Segmentation, Churn Analysis, EDA
