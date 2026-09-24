# Indiakart-sales-performance-analysis
1. Project Overview

Welcome to the IndiaKart E-Commerce Analytics project. You have been hired as a Junior Data Analyst at IndiaKart, a fast-growing Indian online marketplace. The company's management team needs data-driven insights to make better business decisions — and that is where you come in.

You will work with a real-world dataset covering 24 months of business operations, containing over 216,000 records across 8 interconnected tables. Your job is to clean, explore, analyse, and present the data in a way that helps non-technical managers understand what is happening in the business.

1.1  Business Context
IndiaKart operates as an e-commerce marketplace serving customers across India. It sells across 10 categories — Electronics, Fashion, Home & Kitchen, Books, Beauty & Health, Sports & Fitness, Toys & Baby, Grocery, Automotive, and Office Supplies. The platform accepts multiple payment methods including UPI, Credit Card, COD, and EMI, and uses 7 logistics partners for delivery.

Management has the following pressing questions they need answered this quarter:

•	Which product categories are driving the most revenue and which are underperforming?
•	Are we losing too many orders to cancellations, and why?
•	Which customer segments are the most valuable to the business?
•	Are there clear seasonal patterns we should plan our inventory around?
•	Which states and cities are our biggest markets?
•	Is our return rate healthy, or are certain products causing repeat returns?
 
2. Dataset Description

You are provided 8 CSV files and 1 SQL schema file. All files together form the IndiaKart database. Together they contain approximately 216,200 records spanning June 2023 to June 2025.

2.1  Files Provided
File	Records	Size	Description
orders.csv	50,000	7.7 MB	Every order placed on the platform
order_items.csv	1,00,000	9.4 MB	Individual products within each order
customers.csv	10,000	1.4 MB	Customer profiles and lifetime stats
products.csv	1,000	133 KB	Product catalogue with pricing and GST
payments.csv	50,000	5.3 MB	Payment transactions and gateway details
returns.csv	10,000	~1.4 MB	Return requests with reasons and refund status
inventory.csv	1,000	72 KB	Warehouse stock levels and reorder alerts
suppliers.csv	200	29 KB	Supplier details and ratings
schema_and_sql.sql	—	12 KB	SQL CREATE TABLE + 12 analytical queries

2.2  Key Columns Reference
Below are the most important columns you will use throughout this project. Refer to the full Data Dictionary file for all column definitions.

orders.csv — The Central Table
Column	Type	Example	Description
order_id	VARCHAR	ORD000001	Unique identifier for each order
customer_id	VARCHAR	CUST00001	Links to customers.csv
order_date	DATE (DD-MM-YYYY)	15-10-2024	Date the order was placed
status	VARCHAR	Delivered	Delivered / Shipped / Processing / Cancelled / Returned
final_amount	DECIMAL	16,500.00	Amount paid by customer in INR (incl. GST)
gst_amount	DECIMAL	2,700.00	GST component of the order in INR
payment_method	VARCHAR	UPI	UPI / Credit Card / COD / EMI etc.
channel	VARCHAR	App	App / Website / Mobile Web
state	VARCHAR	Maharashtra	Indian state of delivery address

customers.csv — Customer Profiles
Column	Type	Example	Description
customer_id	VARCHAR	CUST00001	Unique customer ID
segment	VARCHAR	Premium	Premium / Regular / Budget / New / Inactive
city / state	VARCHAR	Bengaluru / Karnataka	Geographic location
total_orders	INT	12	Lifetime order count (pre-calculated)
total_spent	DECIMAL	85,000.00	Lifetime spend in INR (pre-calculated)
registration_date	DATE	15-06-2023	When they joined IndiaKart

order_items.csv — Line Items
Column	Type	Example	Description
item_id	VARCHAR	ITM0000001	Unique line item ID
order_id	VARCHAR	ORD000001	Links to orders.csv
product_id	VARCHAR	PRD0042	Links to products.csv
category	VARCHAR	Electronics	Product category
quantity	INT	1	Units purchased
unit_price	DECIMAL	45,000.00	Price per unit in INR at time of order
total_price	DECIMAL	50,850.00	Net price paid after GST minus discount
 
3. Project Tasks & Deliverables

The project is divided into 4 phases. Complete them in order — each phase builds on the last. The estimated time per phase is shown below.

Phase	Deliverable	Skills Used	Difficulty
Phase 1 (Week 1)	Data Loading, Cleaning & Quality Report	Python/Excel, Pandas	Beginner-Intermediate
Phase 2 (Week 2)	Exploratory Data Analysis (EDA) with Charts	Pandas, Matplotlib / Seaborn	Intermediate
Phase 3 (Week 2-3)	Business KPI Calculations & Insights	Python / SQL / Excel	Intermediate
Phase 4 (Week 3-4)	Dashboard + Management Summary Report	Power BI / Excel / Python	Intermediate

3.1  Phase 1 — Data Cleaning & Quality Check  (Est. 5-6 hours)
Before any analysis, you must understand and clean the data. A real analyst never trusts raw data blindly.

What to Do in Phase 1
1. Load all 8 CSV files into Python (pandas) or Excel.
2. For each table, run a basic profile: row count, column count, data types.
3. Check for missing values in every column — report which columns have nulls and what % of rows are affected.
4. Check for duplicate rows — especially duplicate order_id in orders.csv.
5. Validate data types — order_date should be a date, not a string; amounts should be numeric.
6. Check for outliers in final_amount — are there any orders above ₹5 lakh? Flag them.
7. Verify referential integrity — do all order_ids in order_items.csv exist in orders.csv?
8. Write a 1-page Data Quality Report summarising your findings.

Specific checks to run:
•	orders.csv: Check if delivered_date is always after order_date. Flag rows where it is not.
•	payments.csv: Count Failed vs. Success transactions. What is the failure rate?
•	returns.csv: Does every return have a matching order_id in orders.csv?
•	inventory.csv: How many products are in 'Out of Stock' status?
•	customers.csv: Are there customers with total_orders = 0? That is fine — just note it.

Deliverable: A Python notebook (or Excel sheet) with your cleaning code and a written summary of findings. Name it: Phase1_DataCleaning_[YourName].ipynb

3.2  Phase 2 — Exploratory Data Analysis  (Est. 6-8 hours)
EDA is about understanding patterns, distributions, and relationships in the data. Use charts to tell the story.

Create the following charts and write 2-3 sentences of observation for each:

1.	Monthly order volume — a bar or line chart showing number of orders per month for all 24 months. Highlight the Diwali months (Oct, Nov).
2.	Monthly revenue (GMV) — same as above but using final_amount. Compare year-over-year.
3.	Category-wise revenue share — a pie chart or horizontal bar chart. Which category earns the most?
4.	Order status distribution — a donut chart showing % of Delivered, Cancelled, Returned, Shipped, Processing.
5.	Top 10 states by number of orders — a horizontal bar chart.
6.	Customer segment distribution — a pie chart. How many Premium vs. Regular vs. Budget customers?
7.	Payment method usage — a bar chart showing which methods are most popular.
8.	Age distribution of customers — a histogram. What age group shops most?
9.	Return reasons — a bar chart of the most common return reasons from returns.csv.
10.	Average Order Value (AOV) by segment — a bar chart. Do Premium customers spend more per order?

Deliverable: A Python notebook with all 10 charts. Save charts as PNG images too. Name it: Phase2_EDA_[YourName].ipynb

3.3  Phase 3 — KPI Calculations  (Est. 6-8 hours)
Now calculate the business metrics that management actually asks about. These are the numbers that go into board reports.

KPI / Metric	Target / Benchmark	Why It Matters
Gross Merchandise Value (GMV)	Sum of all final_amount (all statuses)	Total business size including cancellations
Net Revenue	Sum of final_amount where status = Delivered	Actual money earned by the platform
Average Order Value (AOV)	Net Revenue / Count of Delivered Orders	Higher AOV = customers buying more per visit
Cancellation Rate	(Cancelled Orders / Total Orders) × 100	Target < 10%. Higher = lost revenue
Return Rate	(Return records / Delivered Orders) × 100	Target < 8%. Higher = product quality issues
Customer Lifetime Value (CLV)	Avg total_spent per customer segment	Premium segment should be 3x Regular
Month-over-Month Growth	((This Month GMV - Last Month GMV) / Last Month) × 100	Shows business trajectory
Top Category Revenue Share	Category Revenue / Total Revenue × 100	Concentration risk if one category > 60%
Payment Failure Rate	(Failed Payments / Total Payments) × 100	Target < 2%. Higher = revenue leakage
Inventory Fill Rate	(In Stock SKUs / Total SKUs) × 100	Target > 95%. Lower = lost sales

Intermediate Challenge: Cohort Analysis (Optional, Bonus)
Group customers by their registration month (cohort).
For each cohort, calculate: How many orders did they place in Month 1, Month 2, Month 3?
This shows customer retention — a key metric for any subscription or repeat-purchase business.
Hint: Use pandas pivot_table or groupby with registration_date and order_date together.

Deliverable: A Python notebook (or Excel workbook) with all KPI calculations clearly labelled. Name it: Phase3_KPIs_[YourName].ipynb

3.4  Phase 4 — Dashboard & Final Report  (Est. 8-10 hours)
The final phase brings everything together into a dashboard and a written report for management.

Dashboard Requirements (Power BI or Excel)
Build a dashboard with the following 5 pages / sections:

•	Page 1 — Revenue Overview: Monthly GMV trend, total orders, AOV card, cancellation rate card.
•	Page 2 — Category Performance: Revenue by category, top 10 products by revenue, return rate by category.
•	Page 3 — Customer Insights: Segment breakdown, top 10 states map, new customers per month.
•	Page 4 — Operations: Order status funnel, payment method breakdown, return reason analysis.
•	Page 5 — Inventory Alert: Stock status summary, low stock products list, warehouse distribution.

Each page must have: a title, at least 2 charts, at least 1 filter/slicer (e.g. date range or category), and a text box with 1-2 key insights.

Management Summary Report
Write a 2-3 page report (in Word or PDF) addressed to the CEO of IndiaKart. The report should include:

•	Executive Summary (5-6 sentences): What is the overall business health?
•	Top 3 Findings: What are the most important things you discovered?
•	Risks Identified: What numbers are concerning?
•	Opportunities: Where should the business focus to grow?
•	Recommendations: At least 3 specific, actionable suggestions.

Important: Write in plain language. Avoid jargon. A manager who does not know Python should be able to read and understand your report.

Deliverable: Dashboard file (.pbix or .xlsx) + Management Report (.docx or .pdf). Name them: Phase4_Dashboard_[YourName] and Phase4_Report_[YourName].
 
4. Evaluation Rubric

Your submission will be evaluated on the following criteria. Total marks: 100.

Criteria	Marks	What We Look For
Phase 1: Data Cleaning & QC Report	15	Correctness of null/duplicate checks, clear documentation, logical conclusions.
Phase 2: EDA Charts (10 charts)	20	Charts are clearly labelled, correct chart type chosen, observations are meaningful.
Phase 3: KPI Calculations	25	All 10 KPIs calculated correctly, formulas are correct, values make business sense.
Phase 4: Dashboard Quality	20	Dashboard is clean, filters work, data is accurate, 5 pages are complete.
Phase 4: Management Report	15	Clear writing, correct numbers cited, actionable recommendations, no jargon.
Bonus: Cohort Analysis	+5	Correctly grouped by registration month, retention pattern is visible.

5. Submission Checklist

Before submitting, verify every item below is complete:

•	Phase1_DataCleaning_[YourName].ipynb — Notebook with cleaning code and QC report
•	Phase2_EDA_[YourName].ipynb — Notebook with all 10 charts (charts also saved as PNG)
•	Phase3_KPIs_[YourName].ipynb — Notebook or Excel with all 10 KPI calculations
•	Phase4_Dashboard_[YourName].pbix/.xlsx — Dashboard with 5 pages and slicers
•	Phase4_Report_[YourName].docx/.pdf — 2-3 page management summary report
•	All files named correctly with your name
•	No hardcoded numbers in your report — every figure should trace back to your analysis
•	Your report does NOT share any raw data files — only your analysis outputs

6. Tools & Resources

You may use any of the following tools. Python is recommended for data cleaning and KPI calculations.

Recommended Tool Stack
Python (pandas, matplotlib, seaborn) — Data cleaning, EDA, KPI calculations.
Jupyter Notebook — For running and documenting your Python code.
Power BI Desktop (free) — For the final dashboard. Download from microsoft.com/en-in/power-bi.
Excel (optional) — Acceptable alternative to Power BI for the dashboard.
SQL (optional) — The schema_and_sql.sql file has 12 ready-to-run queries you can study and modify.
VS Code or PyCharm — Recommended Python editors.

Helpful Python libraries to install:
pip install pandas matplotlib seaborn openpyxl numpy

Hints for Common Challenges
Date parsing: Use pd.to_datetime(df['order_date'], format='%d-%m-%Y') to parse Indian date format.
Joining tables: Use pd.merge(orders, customers, on='customer_id', how='left') to link tables.
Grouping by month: Use df['order_date'].dt.to_period('M').value_counts().sort_index().
Calculating return rate: Divide len(returns) by len(orders[orders.status=='Delivered']) * 100.
INR formatting: Use f'Rs.{value:,.0f}' for currency display in Python.

7. Important Notes


•	Academic integrity: All analysis must be your own. You may discuss approaches with peers but code and reports must be written independently.
•	If you get stuck, try to describe what you are trying to do in your notebook as a comment — partial work showing your thinking still earns partial marks.
•	You do NOT need to use all 8 tables for every phase. Focus on the most relevant tables for each task.
•	The schema_and_sql.sql file contains 12 SQL queries that perform exactly the kind of analysis required in Phase 3. Study them even if you are using Python.

Good luck, and happy analysing!
This is exactly the kind of work junior and mid-level data analysts do every day at Indian e-commerce companies like Flipkart, Meesho, Nykaa, and Swiggy. The skills you build here — data cleaning, KPI calculation, visualisation, and business communication — are directly applicable in the industry.

