# Amazon Sales Report


## Executive Summary

This report provides an in-depth analysis of Amazon sales data from April 30, 2022, to May 31, 2022. The dataset comprises 128,976 entries across 21 attributes, detailing order information, fulfillment channels, shipping details, and item categories. Following data cleaning and preprocessing, the final dataset consists of 37,514 entries.

---

## Data Overview

- **Total Orders Analyzed:** 37,514
- **Time Period:** April 30, 2022 - May 31, 2022
- **Attributes:** 19

---

## Data Cleaning and Preprocessing

1. **Missing Values:** Removed attributes with high null values ('New', 'PendingS').
2. **Data Types:** Converted 'ship-postal-code' to integer for consistency.
3. **Null Handling:** Dropped rows with null values in key columns, reducing the dataset to 37,514 rows from the initial 128,976.

---

## Key Metrics

### Descriptive Statistics

| Metric         | Value            |
|----------------|------------------|
| **Total Entries**    | 37,514         |
| **Average Order Amount (INR)**  | 646.55          |
| **Total Quantity Sold**  | 37,514          |

### Order Status Distribution

- **Shipped:** 84.8%
- **Cancelled:** 15.2%



---

## Category and Size Analysis

### Category Distribution

- **Top Categories:** T-shirt, Shirt, Trousers
- **Most Popular Category:** T-shirt (37.5% of total orders)

### Size Distribution

- **Most Ordered Sizes:** M, L, XL
- **Least Ordered Sizes:** 4XL, 5XL, 6XL

### Quantity Sold by Size

| Size | Total Quantity |
|------|----------------|
| M    | 5,905          |
| L    | 5,795          |
| XL   | 5,481          |

---

## Shipping Analysis

### Top Shipping States

- **Maharashtra:** 6,236 orders
- **Karnataka:** 5,842 orders
- **Tamil Nadu:** 4,721 orders

### Courier Status

- **Shipped:** 84.8%
- **On the Way:** 15.2%

### B2B Distribution

- **B2B Orders:** 0% (All orders are B2C)


---

## Insights and Recommendations

1. **Inventory Management:** Focus on stocking sizes M, L, and XL as they account for the majority of sales.
2. **Marketing Strategies:** Increase promotional efforts in Maharashtra, Karnataka, and Tamil Nadu, the top shipping states.
3. **Fulfillment Efficiency:** Maintain the high performance of the "Shipped" status to ensure customer satisfaction.
4. **Category Focus:** Expand the variety within the T-shirt category, given its high demand.

---

## Conclusion

The analysis highlights significant trends in order sizes, categories, and regional demand. By leveraging these insights, Amazon can optimize inventory management, enhance marketing strategies, and improve overall customer satisfaction.

---

## Appendix

### Data Cleaning Steps
- Dropped columns 'New' and 'PendingS' due to 100% null values.
- Converted 'ship-postal-code' to integer for data consistency.
- Removed rows with null values in key columns, reducing dataset size to 37,514.

### Code Snippets

```python
# Load Data
import pandas as pd
df = pd.read_csv('Amazon Sale Report.csv')

# Data Cleaning
df.drop(['New', 'PendingS'], axis=1, inplace=True)
df.dropna(inplace=True)
df['ship-postal-code'] = df['ship-postal-code'].astype(int)

# Descriptive Statistics
print(df.describe())

# Size Distribution Plot
import seaborn as sns
import matplotlib.pyplot as plt
sns.countplot(x='Size', data=df)
plt.show()

# Category Distribution Plot
sns.countplot(x='Category', data=df)
plt.show()
