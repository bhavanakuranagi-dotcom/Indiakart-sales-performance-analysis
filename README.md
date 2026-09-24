# 🛒 IndiaKart E-Commerce Analytics
https://report-magic-maker-63.lovable.app

An end-to-end **E-Commerce Data Analytics project** focused on analyzing customer behavior, sales performance, revenue trends, product performance, payments, returns, and inventory operations.

The project demonstrates practical skills in **Python, SQL, Excel, Data Cleaning, Exploratory Data Analysis (EDA), KPI Analysis, Data Visualization, and Business Intelligence**.

---

## 📌 Project Overview

**IndiaKart** is a fictional e-commerce business dataset containing customer, order, product, payment, return, inventory, and supplier information.

The objective of this project is to transform raw business data into meaningful insights that can help management understand:

* Sales and revenue performance
* Customer purchasing behavior
* Product and category performance
* Order and cancellation patterns
* Payment performance
* Return behavior
* Inventory status
* Customer segments and value
* Geographic performance
* Monthly business trends

### 📅 Analysis Period

**24 June 2023 – 23 June 2025**

### 📊 Total Records

**222,200 records across 8 tables**

---

# 🎯 Business Objectives

The project answers important business questions such as:

1. How are monthly orders and GMV changing over time?
2. Which product categories generate the highest revenue?
3. Which products are the top performers?
4. Which states contribute the most orders and revenue?
5. What percentage of orders are cancelled or returned?
6. Which payment methods are most frequently used?
7. Which customer segments generate the highest value?
8. How does customer purchase behavior vary by age and segment?
9. What are the major reasons for product returns?
10. Which products require inventory replenishment?
11. How is inventory distributed across warehouses?
12. How does customer retention change across cohorts?

---

# 🗂️ Dataset

The project contains **8 main tables**:

| Table       | Records | Description                               |
| ----------- | ------: | ----------------------------------------- |
| Customers   |  10,000 | Customer profile and segmentation data    |
| Orders      |  50,000 | Order and transaction information         |
| Order Items | 100,000 | Products purchased in each order          |
| Products    |   1,000 | Product, pricing and category information |
| Payments    |  50,000 | Payment transactions and payment status   |
| Returns     |  10,000 | Product return and refund information     |
| Inventory   |   1,000 | Stock and warehouse information           |
| Suppliers   |     200 | Supplier information                      |

---

# 🛠️ Technologies & Tools

### Programming & Analysis

* Python
* Pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Database

* MySQL
* SQL

### Dashboard & Reporting

* Microsoft Excel
* Excel Charts
* Excel AutoFilter
* KPI Tables

### Documentation

* Jupyter Notebook
* Markdown
* PDF Reports

---

# 🔄 Project Workflow

```text
Raw Data
   ↓
Data Understanding
   ↓
Data Cleaning & Quality Checks
   ↓
Exploratory Data Analysis
   ↓
KPI Calculation
   ↓
SQL Business Analysis
   ↓
Data Visualization
   ↓
Excel Dashboard
   ↓
Business Insights & Recommendations
```

---

# 🧹 Phase 1 — Data Cleaning & Quality Analysis

The first phase focuses on understanding and validating the raw datasets.

### Activities performed

* Data profiling
* Missing-value analysis
* Duplicate detection
* Data-type validation
* Date-format conversion
* Numerical-column validation
* Outlier detection
* Primary-key validation
* Foreign-key validation
* Referential-integrity checks
* Business-rule validation

### Data Quality Results

* Duplicate order IDs: **0**
* Duplicate customer IDs: **0**
* Duplicate product IDs: **0**
* Duplicate payment IDs: **0**
* Duplicate return IDs: **0**
* Missing order-to-customer relationships: **0**
* Missing order-to-product relationships: **0**
* Missing payment-to-order relationships: **0**
* Missing return-to-order relationships: **0**

Some missing values were identified in fields where blanks are logically expected, such as delivery dates for orders that have not yet been delivered and refund dates for transactions without completed refunds.

---

# 📈 Phase 2 — Exploratory Data Analysis

The EDA phase analyzes business trends and customer behavior using Python.

### Visualizations Created

1. Monthly Order Volume
2. Monthly GMV
3. GMV Year-over-Year Growth
4. Revenue by Category
5. Order Status Distribution
6. Top Performing States
7. Customer Segment Distribution
8. Payment Method Distribution
9. Customer Age Distribution
10. Return Reasons
11. Average Order Value by Customer Segment
12. Customer Cohort Retention Heatmap

These visualizations help identify important patterns in sales, customers, payments, returns, and operations.

---

# 📊 Phase 3 — KPI Analysis

Important business KPIs were calculated using Python and SQL.

### Key KPIs

| KPI                            |        Result |
| ------------------------------ | ------------: |
| GMV                            | ₹314.74 Crore |
| Net Revenue — Delivered Orders | ₹205.39 Crore |
| Average Order Value            |       ₹63,198 |
| Cancellation Rate              |        11.99% |
| Return Rate                    |        30.77% |
| Payment Failure Rate           |         3.50% |
| Inventory Fill Rate            |         92.2% |
| Top Category Share             |         57.4% |
| Repeat Purchase Rate           |         88.4% |

> **Note:** KPI values are calculated from the project dataset and are intended for analytical and demonstration purposes.

---

# 📊 Excel Dashboard

The project includes a multi-page Excel dashboard:

### 1️⃣ Revenue Overview

Includes:

* GMV trend
* Monthly order volume
* Cancellation-rate trend
* KPI cards
* Monthly performance table
* Filtering options

### 2️⃣ Category Performance

Includes:

* Revenue by category
* Top 10 products
* Category return rate
* Product performance analysis

### 3️⃣ Customer Insights

Includes:

* Customer segment distribution
* Top states
* New customers by month
* Customer lifetime value by segment

### 4️⃣ Operations

Includes:

* Order status analysis
* Payment method performance
* Payment success/failure
* Return reasons

### 5️⃣ Inventory Alert

Includes:

* Inventory status
* Warehouse inventory value
* Low-stock products
* Reorder information

---

# 🗃️ SQL Analysis

The project contains a SQL script:

```text
sql/schema_and_sql.sql
```

The SQL file includes:

* Database/table creation
* Table relationships
* Analytical queries
* Revenue analysis
* Customer analysis
* Product analysis
* Category analysis
* Payment analysis
* Return analysis
* Inventory analysis

SQL was used to demonstrate practical database querying and business-oriented analysis.

---

# 📁 Project Structure

```text
IndiaKart_Analytics_Project_Bhavana/
│
├── data/
│   ├── customers.csv
│   ├── orders.csv
│   ├── order_items.csv
│   ├── products.csv
│   ├── payments.csv
│   ├── returns.csv
│   ├── inventory.csv
│   ├── suppliers.csv
│   └── data_dictionary.md
│
├── notebooks/
│   ├── Phase1_DataCleaning_Bhavana.ipynb
│   ├── Phase2_EDA_Bhavana.ipynb
│   └── Phase3_KPIs_Bhavana.ipynb
│
├── outputs/
│   ├── charts/
│   ├── tables/
│   └── clean/
│
├── sql/
│   └── schema_and_sql.sql
│
├── dashboard/
│   └── Phase4_Dashboard_Bhavana.xlsx
│
├── reports/
│   ├── Phase1_DataQualityReport.md
│   └── Phase4_Report_Bhavana.pdf
│
└── README.md
```

---

# 📌 Key Business Insights

The analysis provides insights into several important areas:

### 💰 Revenue

The analysis tracks monthly GMV and delivered-order revenue to understand overall sales performance and changes over time.

### 🛍️ Category Performance

Category-level analysis identifies the major contributors to overall revenue and highlights categories requiring further investigation.

### 👥 Customer Analysis

Customers are divided into segments such as:

* Premium
* Regular
* Budget
* New
* Inactive

This helps understand differences in customer value and purchasing behavior.

### 📦 Inventory

Inventory analysis identifies:

* In-stock products
* Low-stock products
* Out-of-stock products
* Warehouse inventory value
* Products requiring replenishment

### 💳 Payments

Payment analysis compares different payment methods and identifies successful and failed transactions.

### 🔄 Returns

Return analysis identifies the most common return reasons and helps understand product and customer-related return patterns.

---

# 📚 Data Quality

The project includes a dedicated data-quality report:

```text
reports/Phase1_DataQualityReport.md
```

The report documents:

* Missing values
* Duplicate records
* Data types
* Outliers
* Referential integrity
* Business-rule checks
* Data-cleaning decisions

---

# 📄 Reports

The project contains a management-level PDF report:

```text
reports/Phase4_Report_Bhavana.pdf
```

The report summarizes the analytical findings and important business observations from the project.

---

# ▶️ How to Run the Project

## 1. Clone the repository

```bash
git clone <your-repository-url>
cd IndiaKart_Analytics_Project_Bhavana
```

## 2. Install required Python libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter xlsxwriter openpyxl
```

## 3. Start Jupyter Notebook

```bash
jupyter notebook
```

## 4. Run the notebooks in order

```text
Phase 1 → Data Cleaning
       ↓
Phase 2 → Exploratory Data Analysis
       ↓
Phase 3 → KPI Analysis
```

The notebooks read the datasets from the `data/` folder and save generated outputs in the `outputs/` folder.

---

# 💡 Skills Demonstrated

This project demonstrates practical experience in:

* Data Cleaning
* Data Preprocessing
* Exploratory Data Analysis
* Statistical Analysis
* KPI Development
* Business Analysis
* Customer Analytics
* Sales Analytics
* Product Analytics
* Inventory Analytics
* SQL Querying
* Data Visualization
* Excel Dashboard Development
* Business Reporting
* Data Quality Validation

---

# 🚀 Project Outcome

IndiaKart Analytics demonstrates an end-to-end approach to solving a business analytics problem — from **raw data collection and quality validation to analysis, KPI development, visualization, dashboard creation, and business reporting**.

The project helped strengthen practical skills in **Python, SQL, Excel, data visualization, and business-focused data analysis**.

---

## 👩‍💻 Author

**Bhavana Kuranagi**

**BCA Student | Aspiring Data Analyst**

### Core Skills

`Python` · `SQL` · `Excel` · `Power BI` · `Pandas` · `NumPy` · `Data Analysis` · `Data Visualization`

---

⭐ If you find this project useful, feel free to explore the notebooks, SQL queries, dashboard, and reports included in the repository.

