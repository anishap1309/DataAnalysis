# 🅿️ Parking Utilization EDA

This project performs **Exploratory Data Analysis (EDA)** on parking meter transaction data to uncover trends, patterns, anomalies, and data quality issues related to parking usage behavior.

---

## 📊 Objective

To analyze and visualize historical parking transaction data, with the goal of:

- Understanding usage patterns across locations and payment methods.
- Identifying data quality issues (missing values, outliers, inconsistencies).
- Exploring distributions of key variables such as duration, amount, and source.
- Deriving time-based insights (peak usage periods, duration trends).


---

## 📁 Dataset Features

The dataset contains the following columns:

| Column Name       | Description                              |
|-------------------|------------------------------------------|
| ID                | Unique identifier of the transaction     |
| Source            | System/source that recorded the data     |
| Start Time        | Parking session start timestamp          |
| End Time          | Parking session end timestamp            |
| Amount            | Amount charged for the session           |
| Kiosk ID          | ID of the physical kiosk (if applicable) |
| App Zone ID       | Zone identifier used in the app          |
| Payment Method    | Payment type (e.g., CARD, Wallet)        |
| Location Group    | Parking level or zone                    |
| Last Updated      | Last modified timestamp of the record    |

# 🧾 Payment Type Normalization Script

This repository provides a simple Python script to standardize values in the `payment_type` column of a parking dataset using pandas. It maps various raw payment method descriptions into grouped, cleaner categories for downstream analysis.

## 📌 Overview

The raw `payment_type` values include a mix of app-based and traditional payment methods, often labeled inconsistently. This script ensures consistent labeling under broader categories such as:

- `CREDIT/DEBIT`
- `MOBILE APP`
- `DIGITAL WALLET`
- `CASH`

## 🔄 Mapping Logic

The `payment_type` column is updated based on the following mapping:

| Original Value       | Normalized Value |
|----------------------|------------------|
| App - Credit Card    | CREDIT/DEBIT     |
| App - Free           | MOBILE APP       |
| App - Validation     | MOBILE APP       |
| App - Wallet         | MOBILE APP       |
| App - Apple Pay      | DIGITAL WALLET   |
| CARD                 | CREDIT/DEBIT     |
| COINS                | CASH             |
| Google Pay           | DIGITAL WALLET   |

---

## 🧪 EDA Steps Performed

1. **Initial Data Exploration**
   - Data type inspection
   - Basic statistics
   - Null value analysis

2. **Data Quality Checks**
   - Missing values and duplicates
   - Datetime parsing
   - Invalid duration calculations

3. **Univariate & Bivariate Analysis**
   - Distribution of duration and amount
   - Count plots for payment method, source, location
   - Outlier detection using IQR method

4. **Time Series Trends**
   - Record counts per day
   - Duration trends over time

---
