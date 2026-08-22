# Sample Superstore — Advanced Data Analysis & BI Dashboard
### AnalystLab Africa Data Analytics Internship — Week 3

## Overview

This project extends the Week 2 exploratory analysis of the Sample Superstore Sales Dataset into an advanced, business-focused Power BI dashboard. It includes deeper profitability analysis, discount impact investigation, root-cause analysis of a post-2016 sales decline, and evidence-based business recommendations.

## Business Objective

As a Junior Data Analyst at AnalystLab Africa Consulting, the goal was to help company leadership understand:
- Why the company's overall profit margin (8.11%) is thin
- Which products and categories are underperforming
- Whether discounting is hurting profitability
- Why sales appeared to decline after 2016

## Dataset

**Sample Superstore Sales Dataset** — 9,994 order-level transaction records (2014–2017), including order/shipping details, customer segment, product category/sub-category, sales, profit, discount, quantity, and geographic fields.

## Dashboard Structure (3 Pages)

**Page 1 — Executive Overview**
6 KPI cards (Total Sales, Total Profit, Total Orders, Average Sale, Profit Margin, Total Customers), Region and Category slicers (synced across all pages), Profit by Category, Sales by Sub-Category, Sales by Region, Sales by State.

**Page 2 — Profitability Deep Dive**
Total Customers, Loss-Making Orders, Total Discount, Discount % of Sales, Profit Growth %, and Average Profit per Order cards; Monthly Profit Trend line chart; Loss-Making Products table (sorted by biggest losses); Discount vs. Profit scatter chart by product.

**Page 3 — Yearly Trends**
Sales by Year and Category clustered column chart, isolating which category drove the post-2016 decline.

## Key DAX Measures

| Measure | Formula Summary | Result |
|---|---|---|
| Total Customers | DISTINCTCOUNT of Customer ID | 644 |
| Total Orders | DISTINCTCOUNT of Order ID | 1,334 |
| Average Profit per Order | Total Profit ÷ Total Orders | $18.71 |
| Profit Growth % | Current year profit vs. prior year profit (via OrderYear column) | -47.18% |
| Loss-Making Orders | Count of orders with negative profit | 243 (18.2%) |
| Total Discount | Sum of Discount column | 204.49 |
| Discount % of Sales | Total Discount ÷ Total Sales | 0.07% |

Full formulas and explanations are in `DAX_Measures_Documentation.docx`.

## Key Findings

1. Profit fell 47.18% from 2016 to 2017 — steeper than the sales decline alone suggested
2. The decline was concentrated in Furniture, not company-wide — Technology grew over the same period
3. 18.2% of all orders lose money
4. A small number of products account for most losses (12 of the top 17 loss-makers are Furniture)
5. Discounting is minimal (0.07% of sales) and does not explain the losses
6. Profit follows a seasonal pattern, peaking around June–July

Full insights and evidence-based recommendations are in `Business_Insights_Recommendations_Report.docx`.

## Tools Used

- Microsoft Power BI Desktop (dashboard, DAX measures, data modeling)
- Microsoft Word (supporting documentation)

## Files in This Repository

- `Sample_Superstore_Dashboard.pbix` — Power BI dashboard file
- `Dashboard_Export.pdf` — PDF export of all dashboard pages
- `Advanced_Data_Analysis_and_Continuity_Summary.docx` — Project continuity summary and advanced analysis
- `Business_Insights_Recommendations_Report.docx` — Business insights and recommendations
- `DAX_Measures_Documentation.docx` — DAX measure formulas and explanations
- `README.md` — This file

## Author

**Omolade**
AnalystLab Africa — Data Analytics Internship Programme
Week 3: Advanced Data Analysis, KPI Development & Business Intelligence Dashboard

#AnalystLabAfrica
