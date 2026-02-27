# Exploratory Data Analysis -- Internship Case Study

## Project Overview

This project involves performing Exploratory Data Analysis (EDA) on the
provided internship case study dataset to uncover operational insights
and ensure data quality before analysis.

------------------------------------------------------------------------

## Dataset Information

-   Total Records: 500
-   File Name: Internship Casestudy.xlsx

------------------------------------------------------------------------

## Data Cleaning & Assumptions

### Handling Missing Values in `Refunds to customer` And `Basket Size`

The dataset contained 105 null values (21%) in the `Refunds to customer`
column.
While `Basket Size` contained 2 null values

### Investigation Findings:

-   Refunds only occurred when operational issues were recorded.
-   All rows without issues had null refund values.
-   Some rows with issues also had null refund values.
-   No cases were found where a refund was issued without an issue.
-   On Basket Size there was 0 Number of delivered orders which resulted to these 2 null values.

This indicates that null values do NOT represent missing or unknown
data.

Instead, null values represent cases where **no refund was issued
(refund amount = 0). And 0 Number of delivered orders for Basket Size**

### Final Treatment:

Null values were replaced with 0 to preserve business logic and maintain
accurate financial calculations.

``` python
df['Refunds to customer'] = df['Refunds to customer'].fillna(0)
df['Basket size'] = df['Basket size'].fillna(0)
```

### Rationale:

This approach: - Prevents loss of 21% of the dataset - Avoids distortion
of financial metrics - Preserves structured business logic - Ensures
accurate revenue and refund calculations

------------------------------------------------------------------------

## Conclusion

The missingness in `Refunds to customer` and `Basket size` was determined to be systematic
rather than random. Therefore, replacing null values with 0 was the most
appropriate and business-aligned data cleaning strategy.

------------------------------------------------------------------------

## Author

EDA Internship Case Study Analysis
