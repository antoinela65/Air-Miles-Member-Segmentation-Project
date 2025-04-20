# 🧠 Air Miles Loyalty Program Segmentation – Marketing Analytics Project

## 📌 Project Overview

This project aims to analyze **member engagement** within the **Air Miles loyalty program**, using transaction, rewards, and member demographic data to **identify behavior-based segments** and propose **targeted marketing strategies**.

The segmentation is based on how members **earn and redeem points**, their **spending behavior**, and their **engagement over time**. The final goal is to help Loyalty improve **program profitability**, **reactivate disengaged members**, and **increase member satisfaction** through **personalized offers**.

---

## 🎯 Business Objective

Rather than relying on a broad demographic segmentation, the analysis focuses on:
- Evaluating member engagement through **points accumulation and redemption behavior**
- Identifying profiles such as **frequent savers** vs. **impulsive redeemers**
- Understanding member preferences by **purchase category** (gas, grocery, credit, etc.)

This segmentation enables Loyalty to:
- Improve **retention and reactivation efforts**
- Optimize **reward offerings** by member type
- Increase **program usage and long-term member value**

---

## 🛠️ Data Sources

Three primary datasets were used:

| Dataset     | Description                                     |
|-------------|-------------------------------------------------|
| `Members`   | Demographics, tenure, contact preferences       |
| `Reward`    | Redemption type, amount of points used, year    |
| `Transaction` | Category of purchases, amount spent, points earned |

A **data dictionary** (`Data Dictionary_H25.xlsx`) was provided to define all variables used.

## 📥 Access to Full Dataset

You can access the full datasets here:  
👉 [Google Drive – Data_Segmentation_Air-Miles](https://drive.google.com/drive/folders/1N7IDbjHU0w0Kc2M2HSKoEpwR0CW4vCPU)

---

## 🧹 Data Cleaning & Processing

- **Outliers and missing values** were handled through filtering and capping at the 99th percentile.
- **Variables were standardized** where necessary.
- Aggregation was done per `Member_ID` to create one row per individual for segmentation.
- Redundant or highly correlated variables were removed (e.g., `Total_Number_Items_Redeemed`).

---

## ✨ Feature Engineering

- Annual accumulation and redemption behavior (2022–2024)
- Redemption types (Cash Back vs. Rewards)
- Spending and transaction volumes by **Retailer category**
- Bonus points ratio (to evaluate responsiveness to promotions)
- Normalized ratios and totals to ensure comparability

---

## 🔎 Dimensionality Reduction

An **ACP (PCA)** was applied to reduce the feature set from 28 variables to **6 principal components**, preserving 78.5% of the data variance and ensuring interpretability and model robustness.

---

## 🔍 Segmentation Methods

Two segmentation approaches were tested:

1. **Manual Rule-Based Segmentation**
   - Based on business logic (e.g., transaction thresholds, bonus usage)
   - 4 initial groups: High Spenders, Bonus Hunters, Active Users, Inactive Members
   - Resulted in unbalanced clusters → Not ideal for marketing application

2. **Unsupervised Learning with CLARA (K-Medoids)**
   - Applied on PCA-reduced data
   - Optimal number of clusters: **4**
   - Segments are balanced, interpretable, and actionable

---

## 📊 Segments Overview

| Segment                     | Key Traits                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| **1 – Seniors Cashback**   | High tenure, moderate spending, prefer Cash Back, older demographic         |
| **2 – Occasionals**        | Low engagement, few redemptions, potential to reactivate                   |
| **3 – High-Spenders (Rewards)** | Highest spending, save for Rewards, highly strategic usage                 |
| **4 – Low-Spenders**       | Minimal activity, younger, under-engaged segment                           |

Each segment was profiled using both behavioral and socio-demographic characteristics to recommend **personalized marketing strategies**.

---

## 📈 Strategic Recommendations

- **Segment 1:** Retain via print campaigns and cashback incentives.
- **Segment 2:** Educate on point usage and launch targeted reactivation promos.
- **Segment 3:** Offer VIP experiences and exclusive reward tiers.
- **Segment 4:** Onboarding-focused comms and simplified redemption paths.

---

## 📦 Technologies Used

- **R / RStudio**
- Packages: `tidyverse`, `data.table`, `cluster`, `factoextra`, `ggplot2`
- Data handling: `.csv`, `.xlsx`, `.Rmd`
- Data visualization: Custom plots, cluster graphs, scree plots

---

## 📄 Language Note

Please note that the accompanying report and documentation (`.Rmd`, `.docx`) are written in **French**, as this project was completed as part of a graduate-level course at **HEC Montréal**, where French is the primary language of instruction.
