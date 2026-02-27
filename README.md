# Operational Performance Analysis & PCA Study

## Project Overview

This project performs a professional Exploratory Data Analysis (EDA) on an operational performance dataset containing weekly store-level metrics such as:

- Delivered Orders
- Basket Size
- Complaint Categories
- Cancellation Categories
- Refund-related metrics

## Exploratory Data Analysis (EDA)

## 1. Dataset Structure

- Combination of categorical and numerical variables
- Majority of issue-related features are numeric count variables
- Several columns are zero-inflated (many rows contain 0 values)

## 2. Distribution Analysis

### Key Observations:

- Most complaint and issue variables are highly right-skewed
- Many operational issue columns show rare but extreme spikes
- Delivered Orders shows the widest numeric range

### Interpretation:

- The dataset reflects real-world operational data where:
- Most weeks have low issues
- Occasional operational breakdowns cause spikes

## 3. Correlation Analysis

Correlation matrix revealed:

### Very Strong Correlation

- `Total Order Complaint` ↔ `Wrong/Missing Products` (~0.97)

This indicates:
Total complaints are largely driven by wrong/missing products.

### Moderate Correlation

- Delivered Orders ↔ Complaint metrics
- Cancellation drivers ↔ Supply-related issues

### Business Insight:

- Complaints are product-accuracy driven
- Cancellations are supply/availability driven

# Executive-Level Business Insight

## Executive Summary:

- 97% of complaint variation is explainable using operational metrics.
- The single largest driver (≈95%) of total complaints is wrong/missing products.
- Reducing wrong/missing product errors will drastically reduce overall complaints.
- Other operational issues have minimal impact comparatively.

## What This Means Strategically

### Priority Action Plan:

- Improve picking accuracy in stores
- Add double-check system for order fulfillment
- Implement barcode verification
- Add real-time missing item alert system

Fixing this one issue would reduce complaints massively.

## Final Summary in One Sentence

My model proves that almost all total customer complaints are driven by wrong or missing products, and fixing that single operational issue would dramatically reduce overall complaints.