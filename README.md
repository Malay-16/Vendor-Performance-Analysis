# 🧾 Vendor Performance Analysis

## 📌 Project Overview

Vendor Performance Analysis is an end-to-end retail analytics project designed to evaluate vendor efficiency, inventory performance, purchasing effectiveness, and profitability. The project integrates sales, purchase, inventory, and vendor data to generate actionable business insights that support strategic decision-making.

Using SQL for data integration, Python for data analysis and statistical validation, and Power BI for interactive visualization, this project helps identify high-performing vendors, optimize inventory levels, reduce supplier dependency risks, and improve purchasing strategies.

---

## 🎯 Business Problem

Retail organizations often work with hundreds of vendors and thousands of products, making it challenging to monitor profitability and inventory performance effectively.

This project addresses key business questions:

* Which vendors contribute the most to sales and profits?
* Which products have low sales despite high profit margins?
* Are there vendors with poor inventory turnover?
* Is the business overly dependent on a small group of suppliers?
* How much cost advantage does bulk purchasing provide?
* How can inventory and purchasing decisions be optimized?

The objective is to improve profitability, reduce operational inefficiencies, and support data-driven vendor management decisions.

---

## ⚙️ Project Workflow

### 1. Data Ingestion & ETL

* Imported multiple CSV datasets into a SQLite database using Python and SQLAlchemy.
* Built an automated ETL pipeline to centralize data and improve query performance.
* Loaded datasets including:

  * Sales Data
  * Purchase Data
  * Vendor Invoice Data
  * Purchase Price Data
  * Inventory Data

---

### 2. Data Integration

Created a consolidated Vendor Sales Summary table using SQL joins and aggregations.

The process involved:

#### Freight Summary

* Calculated total freight cost for each vendor.

#### Purchase Summary

* Total Purchase Quantity
* Total Purchase Cost
* Purchase Price Analysis

#### Sales Summary

* Total Sales Quantity
* Total Sales Revenue
* Total Sales Price
* Total Excise Tax

All datasets were merged into a single analytical table for further analysis.

---

### 3. Feature Engineering

Developed key business KPIs to evaluate vendor and inventory performance:

| KPI                     | Description                                      |
| ----------------------- | ------------------------------------------------ |
| Gross Profit            | Revenue generated after deducting purchase costs |
| Profit Margin (%)       | Percentage profitability of products/vendors     |
| Stock Turnover          | Measures inventory movement efficiency           |
| Sales-to-Purchase Ratio | Evaluates purchasing effectiveness               |

These metrics enabled deeper profitability and operational analysis.

---

### 4. Data Cleaning & Preparation

To ensure reliable analysis:

* Handled missing values
* Corrected data types
* Removed unwanted spaces and inconsistencies
* Filtered invalid records

Excluded:

* Loss-making transactions
* Negative profit margins
* Products with zero sales activity

---

### 5. Exploratory Data Analysis (EDA)

Key observations:

#### Loss-Making Products

* Identified products generating negative gross profit.
* Lowest observed gross profit: **-$52,002**

#### Unsold Inventory

* Products with purchases but no corresponding sales.
* Indicated slow-moving or obsolete inventory.

#### Freight Cost Variability

* Freight costs ranged from **$0.09 to $257,032**
* Suggested logistics and transportation inefficiencies.

#### Correlation Analysis

* Purchase Quantity vs Sales Quantity showed a correlation of **0.999**
* Demonstrated strong inventory demand alignment.

---

## 📊 Key Business Insights

### 1. High-Margin Brands with Low Sales

* Identified **198 brands** generating high profit margins but low sales volume.
* Opportunity to increase revenue through:

  * Targeted promotions
  * Marketing campaigns
  * Strategic pricing adjustments

---

### 2. Vendor Dependency Risk

* Top 10 vendors accounted for **65.69% of total purchases**.
* Heavy reliance on a limited supplier base creates supply-chain risks.

**Recommendation:** Diversify vendor partnerships to improve resilience.

---

### 3. Impact of Bulk Purchasing

* Large purchase orders achieved an average unit cost of **$10.78**.
* Approximately **72% lower cost per unit** compared to smaller orders.

**Recommendation:** Leverage bulk purchasing agreements to maximize savings.

---

### 4. Inventory Optimization Opportunity

* Identified **$2.71 Million** worth of unsold inventory.

Business impact:

* Increased storage costs
* Reduced cash flow efficiency
* Higher inventory holding risk

**Recommendation:** Implement clearance strategies and improve demand forecasting.

---

### 5. Vendor Profitability Analysis

| Vendor Category        | Average Profit Margin |
| ---------------------- | --------------------- |
| Top Vendors            | 31.17%                |
| Low-Performing Vendors | 41.55%                |

Observation:

* Low-performing vendors achieved higher margins but struggled with sales volume.
* Indicates potential pricing, visibility, or distribution challenges.

---

## 📈 Statistical Validation

Performed hypothesis testing to validate profitability differences between vendor groups.

### Hypotheses

**H₀ (Null Hypothesis):**
No significant difference exists in profit margins between vendor categories.

**H₁ (Alternative Hypothesis):**
A significant difference exists in profit margins between vendor categories.

### Result

The null hypothesis was rejected, confirming that vendor groups operate under significantly different profitability models.

---

## 📊 Power BI Dashboard

The interactive dashboard provides:

* Vendor Sales Analysis
* Vendor Profitability Tracking
* Inventory Turnover Monitoring
* Bulk Purchase Savings Analysis
* Vendor Contribution Breakdown
* Unsold Inventory Insights

The dashboard enables stakeholders to make faster and more informed purchasing and inventory decisions.

---

## 🛠️ Tools & Technologies

* Python (Pandas, NumPy, SciPy)
* SQL (SQLite)
* SQLAlchemy
* Power BI
* Matplotlib & Seaborn
* Jupyter Notebook
* Git & GitHub

---

## 🚀 Business Impact

This project demonstrates how data analytics can be used to:

* Improve vendor management strategies
* Reduce supplier concentration risk
* Optimize inventory investment
* Increase profitability
* Support data-driven purchasing decisions
* Enhance overall operational efficiency
