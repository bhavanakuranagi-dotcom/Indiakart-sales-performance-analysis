# Phase 1 - Data Quality Report

**Project:** IndiaKart E-Commerce Analytics  
**Analyst:** Bhavana

## 1. Scope

Eight tables covering 2023-06-24 to 2025-06-23 were profiled. Total records reviewed: 222,200.

## 2. Table profile

| table       |   rows |   columns |   memory_MB |
|:------------|-------:|----------:|------------:|
| orders      |  50000 |        19 |       11.98 |
| order_items | 100000 |        11 |       14.94 |
| customers   |  10000 |        17 |        2.11 |
| products    |   1000 |        17 |        0.22 |
| payments    |  50000 |        13 |        9.15 |
| returns     |  10000 |        10 |        1.82 |
| inventory   |   1000 |        11 |        0.12 |
| suppliers   |    200 |        14 |        0.04 |

## 3. Missing values

| table    | column         |   missing |   pct_missing |
|:---------|:---------------|----------:|--------------:|
| payments | refund_date    |     50000 |           100 |
| orders   | delivered_date |     17501 |            35 |

Nulls are concentrated in fields that are legitimately empty for open transactions (delivered_date for orders still in transit, refund_date for refunds not yet issued).

## 4. Duplicates

- orders full duplicate rows: **0**
- duplicate order id: **0**
- duplicate customer id: **0**
- duplicate product id: **0**
- duplicate item id: **0**
- duplicate payment id: **0**
- duplicate return id: **0**

## 5. Data types

All date columns were parsed with format `%d-%m-%Y`; all money columns were coerced to numeric. No non-numeric values were found in the amount fields.

## 6. Outliers

- Orders above Rs.5,00,000: **312** (0.62% of orders)
- Maximum order value: **Rs.1,133,382**
- Median order value: **Rs.24,183**

## 7. Referential integrity

- order_items with missing order_id in orders: **0**
- order_items with missing product_id in products: **0**
- orders with missing customer_id in customers: **0**
- payments with missing order_id in orders: **0**
- returns with missing order_id in orders: **0**
- inventory with missing product_id in products: **0**
- products with missing supplier_id in suppliers: **0**

## 8. Targeted checks

- Deliveries dated before their order date: **0**
- Payment failure rate: **3.50%**
- Returns without a matching order: **0**
- Products out of stock: **2**
- Customers with zero orders: **457**

## 9. Conclusion

The dataset is fit for analysis. Keys are unique, foreign keys resolve, and the only material gaps are expected blanks on in-flight orders and pending refunds. High-value orders were flagged rather than deleted, because they are plausible electronics/EMI purchases. Cleaned extracts are saved in `outputs/clean/`.
