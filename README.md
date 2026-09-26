# Commerce Sales & Customer Analysis

## 📌 Project Overview

This project analyzes sales, customer behavior, product performance, and revenue trends for an e-commerce company using MySQL.
The analysis focuses on generating business insights that can support marketing, sales, product, and inventory-related decisions.

---

## 🎯 Business Objective

The objective of this project is to use SQL to:

- Understand customer purchasing behavior
- Identify high-value and repeat customers
- Analyze product and category performance
- Track sales and revenue trends
- Identify top-performing products and sales periods
- Apply advanced SQL techniques to answer business questions

---

## 🗂️ Dataset

The project contains four relational tables:

### Customers
Contains customer information.

| Column | Description |
|---|---|
| customer_id | Unique customer identifier |
| name | Customer name |
| location | Customer location |

### Products
Contains product information.

| Column | Description |
|---|---|
| product_id | Unique product identifier |
| name | Product name |
| category | Product category |
| price | Product price |

### Orders
Contains order-level information.

| Column | Description |
|---|---|
| order_id | Unique order identifier |
| order_date | Date of order |
| customer_id | Customer who placed the order |
| total_amount | Total order value |

### OrderDetails
Contains individual products included in each order.

| Column | Description |
|---|---|
| order_id | Order identifier |
| product_id | Product identifier |
| quantity | Quantity purchased |
| price_per_unit | Selling price per unit |

---

## 🛠️ Tools & Technologies

- MySQL
- MySQL Workbench
- SQL
- GitHub

---

## 🔍 Data Quality Checks

Before performing the analysis, the dataset was validated for:

- Duplicate customer IDs
- Duplicate product IDs
- Duplicate order IDs
- Missing values
- Foreign-key consistency
- Order-level financial reconciliation

The `OrderDetails` table was also examined for repeated `(order_id, product_id)` combinations. These were retained because repeated product entries can represent separate line items within the same order.

Order totals were reconciled against the corresponding order-detail quantities and unit prices.

---

## 📊 Business Analysis

### Customer Analysis

The analysis answers questions such as:

- How many customers placed orders?
- Who are the highest-spending customers?
- How many customers are repeat customers?
- What is the average spending per customer?
- Which customers contribute the most to total revenue?
- Which customers spend above the average?

### Product Analysis

The analysis examines:

- Products generating the highest revenue
- Products with the highest sales volume
- Revenue by product category
- Lowest-revenue products
- Average selling price by category
- Product ranking within each category
- Relationship between sales volume and revenue

### Sales Analysis

The analysis includes:

- Total company revenue
- Total number of orders
- Average Order Value (AOV)
- Monthly order trends
- Monthly revenue trends
- Highest-revenue months

---

## 📈 Key Findings

- Total revenue generated: **₹19,783,000**
- Total orders: **200**
- Average Order Value: **₹98,915**
- **84 customers** placed at least one order.
- **58 customers** were repeat customers among customers who placed orders.
- **Laptop 15" Pro** generated the highest product revenue.
- **Digital SLR Camera** recorded the highest number of units sold.
- **Electronics** generated the highest category revenue.
- **September** recorded the highest monthly revenue.
- Product ranking within categories was performed using SQL window functions.

---

## 💡 Business Insights

### Customer Insights

The analysis identifies high-value customers and repeat customers who contribute significantly to the company's revenue.

Customer revenue contribution was calculated using SQL window functions, allowing individual customer spending to be compared with total company revenue.

### Product Insights

The Laptop 15" Pro generated the highest revenue despite selling fewer units than the Digital SLR Camera.

This demonstrates that **sales volume and revenue performance are not always directly proportional**.

### Category Insights

Electronics generated the highest revenue among the three product categories.

Photography had a high average selling price, while Wearable Tech had a substantially lower average selling price.

### Sales Trend Insights

Monthly analysis revealed variation in both order volume and revenue throughout the year, allowing higher-performing sales periods to be identified.

---

## 🧠 SQL Concepts Demonstrated

This project demonstrates practical use of:

- `SELECT`
- `WHERE`
- `JOIN`
- `GROUP BY`
- `ORDER BY`
- `HAVING`
- Aggregate functions
- `CASE WHEN`
- Subqueries
- Common Table Expressions (CTEs)
- Window functions
- `RANK()`
- `PARTITION BY`
- Date conversion using `STR_TO_DATE()`

---

## 📁 Project Structure

```text
Commerce-Sales-Customer-Analysis/
│
├── data/
│   ├── Customers.csv
│   ├── Products.csv
│   ├── Orders.csv
│   └── OrderDetails.csv
│
├── sql/
│   └── commerce_sales_analysis.sql
│
├── images/
│
└── README.md