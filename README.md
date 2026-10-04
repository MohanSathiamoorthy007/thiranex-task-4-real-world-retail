# Step 20: Create README.md

readme_content = """
# Thiranex Task 4 — Real-World Retail Data Analytics

## Project Overview

This project analyzes a real-world online retail dataset to uncover
sales trends, product performance, customer behavior, geographic
patterns, and customer segments.

The project uses the UCI Online Retail dataset and follows an
end-to-end data analytics workflow:

**Data Collection → Data Cleaning → Feature Engineering → Exploratory
Analysis → Customer Segmentation → Visualization → Business Insights**

---

## Dataset

**Dataset:** Online Retail

**Source:** UCI Machine Learning Repository

The dataset contains transactions from a UK-based online retailer
between December 2010 and December 2011.

### Original Dataset

- Rows: 541,909
- Features provided through the UCI Python interface: 6
- Main variables analyzed:
  - Description
  - Quantity
  - InvoiceDate
  - UnitPrice
  - CustomerID
  - Country

---

## Data Cleaning

The original dataset was inspected for data-quality issues.

### Issues identified

- Missing product descriptions
- Missing customer IDs
- Duplicate records
- Negative quantities representing returns/cancellations
- Zero or negative unit prices

### Cleaning performed

- Removed duplicate records
- Removed rows with missing Description
- Removed rows with missing CustomerID
- Removed transactions with Quantity <= 0
- Removed transactions with UnitPrice <= 0
- Converted InvoiceDate to datetime
- Created Revenue = Quantity × UnitPrice

### Final Dataset

- Valid transactions: 392,617
- Missing values after cleaning: 0
- Duplicate rows after cleaning: 0

---

## Feature Engineering

The following time-based features were created:

- Year
- Month
- Month Name
- Day
- Day Name
- Hour
- Revenue

These features were used to analyze sales patterns across time.

---

## Business Analysis

### Overall Performance

- Total Revenue: £8,885,586.15
- Total Quantity Sold: 5,151,237
- Unique Customers: 4,338
- Unique Products: 3,877

### Monthly Performance

- Highest Revenue Month: November 2011
- Revenue: £1,156,148.36
- Lowest Revenue Month: February 2011
- Revenue: £446,082.42

### Product Performance

Top revenue-generating product:

**PAPER CRAFT, LITTLE BIRDIE**

Revenue: £168,469.60

### Geographic Performance

Top revenue country:

**United Kingdom**

Revenue: £7,283,438.30

### Time-Based Performance

- Highest Revenue Day: Thursday
- Revenue: £1,972,933.33
- Highest Revenue Hour: 12:00
- Revenue: £1,373,668.59

---

## Customer Segmentation

RFM analysis was performed using:

- **Recency:** How recently a customer purchased
- **Frequency:** How often a customer purchased
- **Monetary:** How much a customer spent

Because Frequency and Monetary values were highly skewed, logarithmic
transformation was applied before K-Means clustering.

Four customer segments were identified.

| Customer Segment | Customers | Avg Revenue | Total Revenue |
|---|---:|---:|---:|
| High-Value Loyal Customers | 946 | £6,901.69 | £6,529,001.05 |
| Regular Customers | 1,586 | £1,055.39 | £1,673,841.87 |
| At-Risk Customers | 878 | £458.95 | £402,961.80 |
| Low-Value Customers | 928 | £301.49 | £279,781.43 |

### Key Segmentation Insight

High-Value Loyal Customers generate the majority of total customer
revenue, making customer retention and loyalty strategies particularly
important.

At-Risk Customers have the highest average recency and therefore
represent an important group for targeted re-engagement campaigns.

---

## Key Findings

1. The business generated approximately £8.89 million in revenue after
   cleaning the transaction data.

2. The United Kingdom is the dominant market, generating approximately
   £7.28 million.

3. Revenue increased strongly during the final months of 2011, reaching
   its highest level in November.

4. PAPER CRAFT, LITTLE BIRDIE was the highest-revenue product.

5. High-Value Loyal Customers generated approximately £6.53 million,
   representing the largest revenue contribution among the customer
   segments.

6. Thursday recorded the highest revenue among days with transactions.

7. 12:00 was the strongest revenue hour, suggesting that late morning
   and midday are important sales periods.

---

## Visualizations

The project includes the following visualizations:

- Customer Segment Revenue
- Top 10 Countries by Revenue
- Monthly Revenue Trend
- Revenue by Day of Week
- Revenue by Hour
- Final Online Retail Business Analytics Dashboard

### Final Dashboard

`thiranex_task_4_retail_dashboard.png`

---

## Business Recommendations

### 1. Retain High-Value Customers

Develop loyalty programs, personalized offers, and targeted campaigns
for High-Value Loyal Customers because they contribute the largest
portion of revenue.

### 2. Re-engage At-Risk Customers

Use personalized promotions and reminder campaigns to encourage
customers with high recency values to return.

### 3. Focus on the UK Market

The United Kingdom contributes the majority of revenue, so maintaining
strong customer service, inventory availability, and marketing in this
market is important.

### 4. Optimize Sales Timing

The strong revenue concentration around midday suggests that inventory,
promotions, and operational resources can be aligned with high-demand
hours.

### 5. Monitor Seasonal Trends

The strong increase in revenue during September-November suggests that
seasonal demand should be considered when planning inventory and
marketing campaigns.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Google Colab
- UCI Machine Learning Repository
- K-Means Clustering
- RFM Analysis

---

## Project Files

- `Thiranex_Task_4_Real_World_Retail_Project.ipynb`
- `thiranex_task_4_retail_dashboard.png`
- `customer_segment_revenue.png`
- `top_10_countries_revenue.png`
- `monthly_revenue_trend.png`
- `revenue_by_day_of_week.png`
- `revenue_by_hour.png`
- `README.md`

---

## Conclusion

This project demonstrates an end-to-end real-world retail analytics
workflow. The analysis combines data cleaning, feature engineering,
exploratory analysis, business-level visualization, RFM analysis, and
K-Means customer segmentation to transform raw transaction data into
actionable business insights.
"""

with open("README.md", "w", encoding="utf-8") as f:
    f.write(readme_content)

print("README.md created successfully.")

# Preview
with open("README.md", "r", encoding="utf-8") as f:
    print(f.read())
