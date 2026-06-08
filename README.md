Vendor Performance Analysis is a retail analytics project where sales, inventory, purchase, and vendor data were analyzed to identify the most profitable vendors, optimize inventory levels, reduce supplier dependency, and improve purchasing strategies. The project uses SQL for ETL, Python for analysis, and Power BI for dashboarding.

Business Problem

Imagine a retail company buying products from hundreds of vendors.

Management wants to know:

Which vendors generate the most sales?
Which vendors generate the most profit?
Which products are not selling?
Are we over-dependent on a few vendors?
Does bulk purchasing save money?
Which vendors have poor inventory turnover?

These are the questions this project answers.

Project Workflow
Step 1: Data Ingestion

Multiple CSV files are loaded into a SQLite database.

Files include:

Sales Data
Purchase Data
Vendor Invoice Data
Purchase Price Data
Inventory Data

The script automatically reads every CSV and stores it as a database table.

Interview Answer

First, I created an ETL pipeline where all raw CSV files were ingested into a SQLite database using Python and SQLAlchemy. This centralized the data and made querying more efficient.

Step 2: Data Integration

The project combines multiple tables using SQL.

The script creates:

Freight Summary

Calculates total freight cost per vendor.

Purchase Summary

Calculates:

Purchase Quantity
Purchase Dollars
Purchase Price
Sales Summary

Calculates:

Sales Quantity
Sales Revenue
Sales Price
Excise Tax

All summaries are joined together into one master table called:

Vendor Sales Summary

Step 3: Feature Engineering

New business KPIs are created.

Gross Profit

Profit earned by the company.

Formula:

GrossProfit=TotalSalesDollars−TotalPurchaseDollars

Profit Margin

Measures profitability percentage.

ProfitMargin=
TotalSalesDollars
GrossProfit
	​

×100

Stock Turnover

Shows how fast inventory is sold.

StockTurnover=
TotalPurchaseQuantity
TotalSalesQuantity
	​


Sales-to-Purchase Ratio

Shows efficiency of purchases.

SalesToPurchaseRatio=
TotalPurchaseDollars
TotalSalesDollars
	​


These KPIs are generated in Python.

Step 4: Data Cleaning

The project:

Removes missing values
Fixes data types
Removes extra spaces
Filters invalid records

Specifically removed:

Negative Profit
Negative Profit Margin
Products with Zero Sales

This improves analysis quality.

Step 5: Exploratory Data Analysis

The analysis discovered:

Problem 1: Loss-Making Products

Some products had:

Gross Profit = -$52,002

Meaning products were sold below cost.

Problem 2: Unsold Inventory

Many products had:

Purchase Quantity > 0
Sales Quantity = 0

Meaning inventory was sitting in warehouses.

Problem 3: High Freight Cost Variability

Freight costs ranged from:

$0.09
to $257,032

Suggesting logistics inefficiencies.

Step 6: Correlation Analysis

The project examined relationships between variables.

Key finding:

Purchase Quantity vs Sales Quantity

Correlation = 0.999

Meaning products purchased in larger quantities generally sold more.

Major Business Findings
Finding 1
198 Brands Need Promotion

These brands:

Have high profit margins
Have low sales

Meaning they are profitable but customers aren't buying enough.

Recommendation:

Marketing campaigns
Discounts
Product promotions

Finding 2
Vendor Dependency Risk

Top 10 vendors contribute:

65.69% of total purchases

Risk:

If one major supplier fails, business operations may be affected.

Recommendation:

Diversify suppliers.

Finding 3
Bulk Purchasing Saves Money

Large orders cost:

$10.78 per unit

Compared to much higher costs in small orders.

Result:

Approximately 72% cost savings.

Recommendation:

Negotiate bulk-purchase contracts.

Finding 4
Unsold Inventory Worth $2.71 Million

Huge amount of money is locked in inventory.

Problems:

Higher storage costs
Lower cash flow
Inventory risk

Recommendation:

Clearance sales
Better demand forecasting
Reduce future purchase quantities

Finding 5
Profitability Comparison

Top Vendors:

Average Margin = 31.17%

Low Performing Vendors:

Average Margin = 41.55%

Interesting insight:

Low-performing vendors earn higher margins but sell less.

This suggests pricing or marketing issues.

Statistical Testing

The project also performs hypothesis testing.

Null Hypothesis (H₀)

No difference in profit margins between vendor groups.

Alternative Hypothesis (H₁)

Profit margins differ.

Result:

H₀ rejected.

Meaning:

Vendor groups follow different profitability strategies.

This is an advanced analytics component that recruiters like.

Power BI Dashboard

The dashboard visualizes:

Vendor Sales
Vendor Profitability
Inventory Turnover
Bulk Purchase Savings
Vendor Contribution %
Unsold Inventory Analysis

allowing management to make decisions quickly.
