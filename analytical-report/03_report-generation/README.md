# Report Generation Summary 

This document provides a summary of the report generation phase of the project. The purpose of this folder is to create reusable SQL views that turn customer and product sales data into clean, report-ready outputs.

## Report Generation Workflow 

A structured reporting process was used to transform detailed sales records into summarized business reports. These reports are built from the gold layer and are designed to make customer and product analysis easier.

The report generation process included the following steps:

1. **Create Reusable Views:**
   Each script creates a SQL view in the `gold` schema. These views act like saved queries that can be reused for analysis, dashboards, or business reporting.

2. **Join Fact and Dimension Tables:**
   Sales data from `gold.fact_sales` is joined with customer and product dimension tables to bring together transaction details and descriptive information.

3. **Build Base Queries:**
   Each report begins with a base query that gathers the core fields needed for analysis, such as order numbers, dates, sales amounts, quantities, customer details, and product details.

4. **Aggregate Key Metrics:**
   The scripts summarize data at either the customer level or product level. This includes totals such as sales, quantity, orders, customers, and product activity.

5. **Create Segments:**
   Customers are grouped into segments such as **VIP**, **Regular**, and **New**. Products are grouped into performance categories such as **High-Performer**, **Mid-Range**, and **Low-Performer**.

6. **Calculate KPIs:**
   The reports calculate useful business metrics such as recency, average order value, average monthly spend, average selling price, and average monthly revenue.

## Final Reporting Views 

Two primary reporting views were created in this folder. These views summarize customer and product behavior into formats that are easier to query and analyze.

### 1. Customer Report (`gold.report_customers`)

This report provides a customer-level view of sales activity, customer behavior, and customer value.

**Key Information in the Report:**

* **Customer Details:** Includes customer number, customer name, age, and age group.
* **Purchasing Behavior:** Summarizes total orders, total sales, total quantity purchased, and total products purchased.
* **Customer Segments:** Categorizes customers as **VIP**, **Regular**, or **New** based on lifespan and total sales.
* **Calculated Metrics (KPIs):**

  * **Recency:** Measures how many months have passed since the customer's last order.
  * **Average Order Value (AOV):** Calculates the average amount spent per order.
  * **Average Monthly Spend:** Shows the customer's average spending over their active lifespan.

**Business Value:**
This report helps identify customer behavior patterns and customer value groups. It can support customer retention, targeted marketing, loyalty strategies, and deeper customer analysis.

### 2. Product Report (`gold.report_products`)

This report provides a product-level view of sales performance, product behavior, and revenue contribution.

**Key Information in the Report:**

* **Product Details:** Includes product name, category, subcategory, and cost.
* **Sales Performance:** Summarizes total orders, total sales, total quantity sold, and total unique customers.
* **Product Segments:** Categorizes products as **High-Performer**, **Mid-Range**, or **Low-Performer** based on total sales.
* **Calculated Metrics (KPIs):**

  * **Recency:** Measures how many months have passed since the product was last sold.
  * **Average Selling Price:** Calculates the average price per unit sold.
  * **Average Order Revenue (AOR):** Shows the average revenue generated per order.
  * **Average Monthly Revenue:** Measures the product’s average revenue across its active sales period.

**Business Value:**
This report helps compare product performance and identify which products drive the most revenue. It can support inventory planning, product strategy, marketing focus, and decisions around low-performing products.

## Key SQL Concepts Used 

* **Views:** `CREATE VIEW`, `DROP VIEW`
* **Common Table Expressions:** `WITH`
* **Joins:** `LEFT JOIN`
* **Aggregate Functions:** `SUM()`, `COUNT()`, `AVG()`, `MIN()`, `MAX()`
* **Date Functions:** `DATEDIFF()`, `GETDATE()`
* **Conditional Logic:** `CASE`
* **Grouping:** `GROUP BY`
* **Null Handling:** `NULLIF()`
