## Data-Visualization-Power-BI
Data visualization in Power BI transforms cleaned and modeled datasets into interactive visuals that highlight business performance. By combining charts, maps, and KPIs, the dashboard provides actionable insights for decision‑making.

## 🎯 Project Overview
Business Problem:
  Organizations often struggle to derive meaningful insights from fragmented sales data spread across multiple Excel files. Raw data alone does not support strategic decision-making.

Objective:
  To develop an end-to-end Business Intelligence solution in Power BI that transforms raw sales data into actionable insights. The key objectives were to clean and model the datasets, create dynamic DAX KPIs for Sales, Profit, and Target Achievement, and build an interactive dashboard to visualize trends, category performance, and regional distribution.

Target Audience:

 Executive Leadership: For a high-level strategic overview of business performance.
 Sales Operations Team: For category and region-wise deep-dive analysis.
 Finance Team: For profitability and margin tracking.
 
Provide insights to support 
* Target Audience: Executive Leadership → Strategic overview of performance.
* Sales Operations → Category and region‑wise analysis.
* Finance Teams → Profitability and margin tracking.

  ## 🗃️ Data Sources & Architecture
* Source Systems: Local Excel/CSV files - List of Orders, Order Details, and Sales Target.
* Data Volume: 5,000+ records covering Jan-Nov 2026.
* Storage Mode: Import Mode for optimized query performance and faster DAX calculations.
* Model Type: Star Schema

## ⚙️ Data Transformation (ETL) - Power Query

All data cleaning and shaping was performed in Power Query Editor:

* Tool Used:Power Query Editor.

* Merged Orders and Order Details using Order ID as the primary key.
* Converted text-formatted dates into proper Date data type and created a dedicated Date Table.
* Removed duplicates, null values, and handled missing data.
* Applied TRIM & CLEAN to standardize text fields (Category, City, State).
* Unpivoted monthly sales target columns to create a normalized fact table for Actual vs. Target comparison.

  
# Custom Functions:
* Profit Margin calculation (Profit ÷ Sales) × 100.
* Automated Target Achievement logic.
* Dynamic Date formatting.

  ## 🧠 Data Model & DAX
* Model Type: State your schema design
 * Fact Tables: Order Details (Transactional Data) & Sales Target (Target Data)
 * Dimension Tables: List of Orders (Customer, Region, Date) & Product Hierarchy (Category, Sub-Category)


* Key Measures:
Total Sales = SUM('Order Details'[Amount])
Total Profit = SUM('Order Details'[Profit])
Target Achievement % = DIVIDE([Total Sales], SUM('Sales Target'[Target]))
Revenue per Order = DIVIDE([Total Sales], DISTINCTCOUNT('Orders'[Order ID]))
YoY Growth % = DIVIDE([Total Sales] - [Prior Year Sales], [Prior Year Sales])

  
## 🖥️ Dashboard Features
*  Executive Overview: High-level KPI cards (Total Sales, Profit, Orders), Actual vs. Target gauge, and overall sales trend.
*  Sales Deep Dive: Category & Sub-Category matrix, regional map analysis, and top-performing cities/states.
*  Performance & Profitability: Profit margin analysis, variance chart, and sub-category wise profitability insights.

## 💡 Key Insights
* Furniture generated the highest total sales but consistently lagged behind monthly targets.
* Clothing was the most consistent performer, regularly exceeding targets and delivering the highest profit margin.
* Electronics showed fluctuating performance with high growth potential during promotional periods.
* Madhya Pradesh, Maharashtra, and Rajasthan emerged as the top 3 states by order volume and revenue.

## Tools Used: Power BI | Power Query | DAX | Excel
Thank You
Entri Elevate
