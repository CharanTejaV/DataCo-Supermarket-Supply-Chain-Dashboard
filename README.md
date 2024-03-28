# DataCo-Supermarket-Supply-Chain-Dashboard
The DataCo Supermarket Supply Chain Dashboard is a comprehensive Power BI project designed to illuminate the multifaceted performance of the superstore from various analytical dimensions. This project encapsulates the operational, customer-centric, and financial health of the business, providing stakeholders with a robust tool for strategic decision-making.

## Project Objective
The primary goal of this project is to showcase DataCo Supermarket’s performance over the years, delving into key aspects of the business, including an analysis of customer behavior, order patterns, and financial health, all enhanced with interactive elements like bookmarks, tooltips, and page navigation for a dynamic user experience. The dashboard is structured to grant a granular perspective on the day-to-day operations and long-term trends, facilitating a deep understanding of the business dynamics at play.

## Introduction
This repository contains a comprehensive Power BI dashboard project designed to provide a multifaceted analysis of the DataCo supermarket supply chain. The project is structured into four distinct pages, each offering unique insights:

## Dashboard Overview
- Business Overview
- Company Financials
- Customer-Centric Analysis
- Time Series Analysis

## Dashboard Pages
### Company Overview
- Financial Performance: A snapshot of Total Sales, Revenue, and Profit, coupled with insights into least sold items and overall order quantities.
- Market Spread: Analysis of discounts given, profits by city, highlighting areas with significant market penetration and potential growth opportunities.

### Business Overview
- Global Discounts: Identifies the top 5 countries receiving the highest discounts, providing a lens into strategic discount allocation.
- Order Fulfillment: Breakdown of order statuses, including completed, pending, and shipped, alongside products yielding the highest profit margins and delivery status.

### Time Series Analysis
- Temporal Trends: Exhibits a quarterly and yearly breakdown of Profit, Sales, and QoQ profit margins, as well as yearly discounts and total sales, including a comparative analysis with the previous year to determine YoY growth.

### Customer Centric Details
- Customer Behavior: Segmentation of customer base, identification of fraud percentage in orders, and a deep dive into the top 10 cities by sales.
- Engagement: Highlights which customers have ordered the most, offering a clear direction for targeted marketing campaigns and loyalty programs.

## Features and Measures
The dashboard leverages DAX (Data Analysis Expressions) to compute complex measures and calculated columns that drive the analytics. Key measures include:
```
Fraud percentage =
VAR A = CALCULATE(DISTINCTCOUNT('Order Dataset'[Order Id]), FILTER('Order Dataset', 'Order Dataset'[Order Status] = "SUSPECTED_FRAUD"))
VAR B = DISTINCTCOUNT('Order Dataset'[Order Id])
RETURN DIVIDE(A, B, 0)

Orders percentage = 
VAR S = SUM('Order Dataset'[Order Id])
VAR DIV = SUMX(ALL('Order Dataset'),'Order Dataset'[Order Id])
VAR SUMMARY = DIVIDE(S,DIV)*100
RETURN SUMMARY
```
### Model View
![Model View](https://github.com/CharanTejaV/DataCo-Supermarket-Supply-Chain-Dashboard/assets/143735053/17f64da3-8377-457b-9c28-f9105a7fad0b)

### Conclusion
This dashboard serves as a strategic tool for DataCo Supermarket, facilitating the optimization of marketing efforts, sales strategies, and overall business operations. Through careful analysis of each facet of the business, DataCo is empowered to make data-driven decisions for sustained growth and customer satisfaction.

## License
This project is for educational and demonstration purposes only. All data used is sourced from publicly available datasets on Kaggle and is governed by their respective licenses.
